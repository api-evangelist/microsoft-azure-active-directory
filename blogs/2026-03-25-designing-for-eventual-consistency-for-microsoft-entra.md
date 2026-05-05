---
title: "Designing for Eventual Consistency for Microsoft Entra"
url: "https://devblogs.microsoft.com/identity/designing-for-eventual-consistency-for-microsoft-entra/"
date: "Wed, 25 Mar 2026 02:30:05 +0000"
author: "Kyle Marsh"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>Microsoft Entra is a globally distributed service that provides identity and access management to millions of customers world-wide. To scale reliably and remain resilient during failures, Microsoft Entra uses an eventually consistent directory model.</p>
<h1>Key takeaway</h1>
<p>A successful write to Microsoft Entra does not guarantee that an immediate read will reflect that change. This article explains how eventual consistency appears in Microsoft Entra, why it exists, and the concrete patterns you should use when building applications that create, update, or manage directory objects. Eventual consistency applies regardless of the programmatic interface used. Applications built directly on Microsoft Graph or higher-level tools like PowerShell need to design for eventual consistency.</p>
<h1>What eventual consistency means in Microsoft Entra</h1>
<p>When you create or update a directory object such as a user, application, service principal, or group membership, the write is accepted first and replicated asynchronously across directory replicas. During this replication window, it is normal for:</p>
<ul>
<li>A read request to not return the latest data for entities that have been recently updated.</li>
<li>A newly created object to return a &#8220;Not Found&#8221;</li>
<li>A recently updated property to not yet be visible</li>
</ul>
<p>This behavior is expected and documented for Microsoft Entra and should be handled explicitly by client applications.</p>
<h1>Why Microsoft Entra behaves this way</h1>
<p>Microsoft Entra operates on top of a multi-region, multi-replica directory architecture designed for scale, availability, and fault tolerance. Reads are served from nearby replicas for performance, while writes are replicated asynchronously.</p>
<p><img alt="DataCenter Boundry" src="&quot;https://devblogs.microsoft.com/identity/wp-content/uploads/sites/74/2026/03/DataCenterBoundry.webp&quot;" /></p>
<h1>App-only vs delegated access</h1>
<h2>Delegated access (app + user):</h2>
<ul>
<li>Requests run on behalf of a signed-in user</li>
<li>Consistency across requests is often observed</li>
</ul>
<h2>Application-only access (app-only):</h2>
<ul>
<li>Requests run without a user context</li>
<li>Common for background jobs and automation</li>
<li>Consistency across requests is not guaranteed by design</li>
</ul>
<h1>Recommended design patterns</h1>
<ol>
<li><strong>Prefer delegated flows when consistency is required.</strong> If your scenario is interactive and user-driven, delegated access may provide more predictable consistency behavior.</li>
<li><strong>Trust successful write responses.</strong> If a write operation returns a success status, treat the operation as complete. Avoid immediate reads whose only purpose is confirmation.</li>
<li><strong>Cache identifiers and properties you just wrote.</strong> Use IDs and properties returned in the response body of create calls instead of re-reading the object immediately.</li>
<li><strong>Reduce multi-step workflows.</strong> Avoid create-read-update sequences when a single call or fewer operations can achieve the same outcome.</li>
<li><strong>Poll with exponential backoff when a read is required.</strong> When a read is unavoidable, treat not found responses as transient and retry with exponential backoff.</li>
<li><strong>Make retries idempotent.</strong> Design retries so repeated requests do not cause duplicate resources or unintended side effects.</li>
</ol>
<h2>What not to do</h2>
<ul>
<li>Assume immediate visibility after a write</li>
<li>Treat not found after creation as a permanent failure</li>
<li>Use fixed sleep delays without retry logic</li>
<li>Build workflows that depend on strict ordering across separate calls to Microsoft Entra</li>
</ul>
<h1>Final takeaway</h1>
<p>Microsoft Entra is eventually consistent by design, particularly for application-only scenarios. Applications that trust successful writes, minimize read-after-write dependencies, and implement safe retries are more resilient, scalable, and production-ready.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/designing-for-eventual-consistency-for-microsoft-entra/">Designing for Eventual Consistency for Microsoft Entra</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
