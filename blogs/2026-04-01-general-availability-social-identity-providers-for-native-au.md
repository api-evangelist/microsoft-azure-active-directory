---
title: "General Availability: Social Identity Providers for Native Authentication via Browser‑Delegated Flows (web-view) in Microsoft Entra External ID"
url: "https://devblogs.microsoft.com/identity/native-auth-social-idps-web-view-ga/"
date: "Wed, 01 Apr 2026 19:37:15 +0000"
author: "Sasha Mars"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>We’re excited to announce the General Availability of Social Identity Provider (IdP) support for Native Authentication in Microsoft Entra External ID. This release enables developers to integrate popular social sign‑in options such as Google, Facebook, and Apple — into native and single‑page applications that use Native Authentication. Importantly, social identity providers are supported through a browser‑delegated (web‑view) authentication flow. This approach ensures compatibility with social providers while maintaining the security posture expected of enterprise‑grade identity systems.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/concept-native-authentication?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Get Started with Native Authentication</a></div></p>
<h2>Clarifying native vs. browser‑delegated social authentication</h2>
<p>Native Authentication in Entra External ID supports integrating Social Identity Providers while maintaining application‑centric user experiences.</p>
<p>Social sign‑in is currently supported:</p>
<table>
<thead>
<tr>
<th>Authentication stage</th>
<th>What’s supported</th>
</tr>
</thead>
<tbody>
<tr>
<td>Native app UX</td>
<td>App‑owned native sign‑in or sign‑up screen</td>
</tr>
<tr>
<td>Social IdP authentication (GA)</td>
<td>Google, Facebook, Apple — via browser‑delegated (web‑view) flow</td>
</tr>
<tr>
<td>Post‑social authentication (GA)</td>
<td>Entra External ID authentication steps (for example, MFA via Conditional Access) — via browser‑delegated (web‑view) flow</td>
</tr>
<tr>
<td>Fully native post‑social UX (future)</td>
<td>Planned — Entra External ID authentication steps (for example, MFA) performed via native API‑driven experience instead of browser‑delegated flow</td>
</tr>
</tbody>
</table>
<p>After a user selects a Social Identity Provider, authentication continues in a browser‑delegated (web‑view) experience to comply with provider OAuth requirements. Subsequent authentication steps such as MFA when Conditional Access is enabled — are also completed within this delegated flow. This model enables Social IdP support in Native Authentication today. A future release will introduce native UX for post‑social authentication steps, replacing the current browser‑delegated experience where applicable.</p>
<h2>Why Social Identity Providers matter for native apps</h2>
<p>Consumer and external‑facing applications increasingly need to offer familiar sign‑in options such as Google, Facebook, or Apple without compromising security or standards compliance.</p>
<ul>
<li>When social sign‑in is required — for example, to streamline onboarding, improve conversion, or support bring‑your‑own‑identity scenarios.</li>
<li>While preserving app‑centric experiences — the initial sign‑in or sign‑up screens remain native within the application.</li>
<li>Without handling user credentials in application code — authentication with social providers is performed using a browser‑delegated (web‑view) flow that aligns with OAuth requirements.</li>
</ul>
<p>Native Authentication enables developers to integrate Social Identity Providers into native experiences while maintaining security boundaries enforced by the provider and Entra External ID. Subsequent authentication steps such as MFA when Conditional Access is enabled — continue within the same browser‑delegated flow.</p>
<h2>What’s now generally available</h2>
<p>With this GA release, developers can now:</p>
<ul>
<li>Enable Social Identity Providers (such as Google and Facebook) in native sign‑in and sign‑up experiences.</li>
<li>Allow users to authenticate with supported social providers using a browser‑delegated (web‑view) flow within the application.</li>
<li>Leverage standards‑compliant OAuth redirect flows required by social identity providers.</li>
<li>Rely on Entra External ID to issue ID and access tokens after successful social authentication—without handling user credentials in application code.</li>
<li>
<p>Present a native sign‑in or sign‑up screen within the app, after which authentication continues in a browser‑delegated (web‑view) experience for:</p>
<ul>
<li>The selected social identity provider (for example, Google, Facebook, or Apple), and</li>
<li>Any subsequent Entra External ID authentication steps (such as MFA when Conditional Access is enabled).</li>
</ul>
</li>
</ul>
<p>Native Authentication continues to issue tokens only after the selected social provider has successfully completed authentication through the browser‑delegated flow.</p>
<h2>Ready to get started?</h2>
<p>To begin using Social Identity Providers with Native Authentication, configure the provider in your Entra External ID tenant and integrate using the Native Authentication SDKs. Social sign‑in is supported through a browser‑delegated (web‑view) authentication flow.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-identity-provider-sign-in-sign-up?toc=/entra/external-id/toc.json&amp;bc=/entra/external-id/breadcrumb/toc.json" target="_blank">Tutorial: Add email one-time passcode MFA to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-email-strong-authentication-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add federated identity provider sign-in and sign-up web flow to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-react-social-sign-in" target="_blank">Tutorial: Support federated identity providers in a React single-page app by using native authentication JavaScript SDK</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-angular-social-sign-in" target="_blank">Tutorial: Support federated identity providers in an Angular single-page app by using native authentication JavaScript SDK</a></div></p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out features in the Microsoft Entra suite of products, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/native-auth-social-idps-web-view-ga/">General Availability: Social Identity Providers for Native Authentication via Browser‑Delegated Flows (web-view) in Microsoft Entra External ID</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
