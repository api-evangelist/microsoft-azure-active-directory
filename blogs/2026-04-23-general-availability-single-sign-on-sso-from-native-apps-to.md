---
title: "General Availability: Single Sign-On (SSO) from Native Apps to Embedded Web Views in Microsoft Entra External ID Native Authentication"
url: "https://devblogs.microsoft.com/identity/native-auth-sso-ga/"
date: "Thu, 23 Apr 2026 16:51:24 +0000"
author: "Sasha Mars"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>We’re excited to announce the General Availability (GA) of Single Sign-On (SSO) from Native Apps to Embedded Web Views for Microsoft Entra External ID (EEID) Native Authentication.</p>
<p>This release marks a major milestone in delivering end-to-end seamless authentication experiences for modern CIAM applications bridging the gap between native and web-based app surfaces.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/how-to-native-authentication-webview-sso?toc=/entra/external-id/toc.json&amp;bc=/entra/external-id/breadcrumb/toc.json" target="_blank">Implement Single Sign-On from Native Apps to Embedded Web Views</a></div></p>
<h2>Why SSO matters for Native Auth</h2>
<p>Native Authentication gives developers full control over the identity UX—enabling pixel-perfect, in-app sign-in and sign-up experiences without browser redirects.</p>
<p>However, real-world applications rarely stay fully native.</p>
<p>Most modern apps include embedded web experiences, such as:</p>
<ul>
<li>Profile management pages</li>
<li>Payment or checkout flows</li>
<li>Loyalty or rewards dashboards</li>
<li>Support or account portals</li>
</ul>
<p>Without SSO, users are forced to authenticate again when transitioning from native UI to web content—creating friction, drop-offs, and inconsistent experiences.</p>
<p>With GA of SSO for embedded web views, this problem is now solved.</p>
<h2>What’s now generally available</h2>
<p>With this release, developers can now enable seamless SSO between native and web experiences within the same app session.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Seamless user experience</strong> Users authenticate once via native UI—and are automatically signed into embedded web content without a second prompt.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Token-based session continuity</strong> The native app securely retrieves an access token and passes it to the web view, enabling immediate access to protected resources.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>No browser dependency</strong> SSO works entirely within embedded web views (e.g., WKWebView, Android WebView)—preserving full control over UX.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Developer-controlled integration</strong> Applications can inject authentication state into requests, ensuring flexibility across custom app architectures.</p>
<h2>How it works (high-level)</h2>
<p>The SSO flow builds on top of EEID Native Authentication:</p>
<ol>
<li>User signs in via native authentication (SDK or API) </li>
<li>App retrieves a valid access token </li>
<li>App loads the embedded web view with a request containing: <code>Authorization: Bearer &lt;access_token&gt;</code></li>
<li>The web resource validates the token and grants access immediately</li>
</ol>
<p>This enables a secure bridge between native token state and web session state—without reauthentication.</p>
<h2>Developer scenarios unlocked</h2>
<p>This capability is especially impactful for CIAM developers building hybrid apps:</p>
<p><img alt="📱" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f4f1.png" style="height: 1em;" /> <strong>Mobile + Web hybrid experiences</strong> Enable seamless transitions between native UI and web-based modules without re-login.</p>
<p><img alt="🛍" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f6cd.png" style="height: 1em;" /> <strong>Commerce and customer journeys</strong> Avoid authentication interruptions across checkout, billing, and account management flows.</p>
<p><img alt="🔒" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f512.png" style="height: 1em;" /> <strong>Secure embedded experiences</strong> Maintain token-based security while delivering fully embedded web experiences.</p>
<p><img alt="🎯" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f3af.png" style="height: 1em;" /> <strong>Consistent branding</strong> Keep users inside your app—no redirects, no context switching—while maintaining authentication continuity.</p>
<h2>Behind the scenes: Why this matters</h2>
<p>Embedded web views are isolated from browser session state, which means they don’t automatically inherit SSO cookies. This historically forced developers to either:</p>
<ul>
<li>Re-authenticate users in the web view, or</li>
<li>Use complex workarounds</li>
</ul>
<p>With this release, EEID Native Auth introduces a first-class, token-based SSO model—bridging native authentication and web sessions in a secure and scalable way.</p>
<h2>This is just the beginning of the SSO journey</h2>
<p>While this GA unlocks SSO within a single application (native → embedded web view), it represents only the first step in a broader SSO vision for EEID Native Authentication.</p>
<p>We are actively investing in:</p>
<ul>
<li>SSO across multiple apps (native-to-native)</li>
<li>SSO across devices and sessions</li>
<li>Integration with broader identity ecosystems</li>
<li>Advanced security scenarios (policy, conditional access, passkeys)</li>
</ul>
<p>Our goal is to deliver a comprehensive, modern SSO platform for CIAM, built on the flexibility of Native Authentication.</p>
<h2>Ready to get started with Native Authentication?</h2>
<p>To begin using single sign-on (SSO) from native apps to embedded web views, configure Native Authentication in your Microsoft Entra External ID tenant and integrate your mobile application using the Native Authentication SDKs or APIs. Once your app successfully signs in users via native authentication, retrieve a valid access token and use it to load your embedded web view with the user’s authenticated context enabling a seamless, no‑relogin experience across native and web surfaces.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/concept-native-authentication?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Get Started with Native Authentication</a></div></p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out features in the Microsoft Entra suite of products, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/native-auth-sso-ga/">General Availability: Single Sign-On (SSO) from Native Apps to Embedded Web Views in Microsoft Entra External ID Native Authentication</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
