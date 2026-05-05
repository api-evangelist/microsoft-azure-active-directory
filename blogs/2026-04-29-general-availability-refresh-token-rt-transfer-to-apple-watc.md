---
title: "General Availability: Refresh Token (RT) Transfer to Apple Watch in Microsoft Entra External ID Native Authentication"
url: "https://devblogs.microsoft.com/identity/native-auth-refresh-token-transfer-ga/"
date: "Wed, 29 Apr 2026 15:13:11 +0000"
author: "Sasha Mars"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>We’re excited to announce the General Availability (GA) of Single Sign-On (SSO) from Native Apps to Embedded Web Views for Microsoft Entra External ID (EEID) Native Authentication.</p>
<p>This release marks a major milestone in delivering end-to-end seamless authentication experiences for modern CIAM applications bridging the gap between native and web-based app surfaces.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-ios-macos-sign-in-sign-out?toc=/entra/external-id/toc.json&amp;bc=/entra/external-id/breadcrumb/toc.json#access-a-refresh-token" target="_blank">Get started with Native Authentication on iOS/macOS</a></div></p>
<h2>Why RT transfer matters for Native Auth</h2>
<p>Native Authentication enables developers to build fully in‑app, customizable sign-in experiences with secure token management.</p>
<p>However, modern applications increasingly extend beyond a single device.</p>
<p>Real-world scenarios include:</p>
<ul>
<li>Companion apps (e.g., Apple Watch)</li>
<li>Widgets and background experiences</li>
<li>Multi-surface mobile ecosystems</li>
</ul>
<p>In these cases, devices like Apple Watch must independently access APIs even when disconnected from the phone.</p>
<p>Without RT transfer:</p>
<ul>
<li>Watch apps cannot refresh expired access tokens</li>
<li>Users experience interruptions or forced re-authentication</li>
<li>Developers resort to unsupported or insecure workarounds</li>
</ul>
<p>As highlighted in customer scenarios (e.g., GM), this gap creates significant friction and can block adoption of native authentication in production environments. With GA of RT transfer, this problem is now solved.</p>
<h2>What’s now generally available</h2>
<p>With this release, developers can securely enable token continuity across devices, allowing companion apps like Apple Watch to maintain authenticated sessions independently.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Independent token refresh on Apple Watch</strong> Companion devices can refresh access tokens without relying on phone connectivity ensuring uninterrupted API access.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Seamless cross-device experience</strong> Users authenticate once on their mobile app and continue interacting on secondary devices without additional sign-in prompts.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Opt-in developer control</strong> RT access is explicitly enabled via configuration, ensuring developers consciously opt into advanced scenarios.</p>
<p><img alt="✅" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/2705.png" style="height: 1em;" /> <strong>Secure-by-design guidance</strong> Clear best practices for storage, transfer, and revocation are provided to maintain strong security posture when handling refresh tokens.</p>
<h2>How it works (high-level)</h2>
<p>The RT transfer model builds on top of EEID Native Authentication and extends it to companion devices:</p>
<ol>
<li>User signs in via native authentication on iOS</li>
<li>The app retrieves authentication tokens (including RT via opt-in API)</li>
<li>The RT is securely transmitted to the Apple Watch (e.g., via WatchConnectivity)</li>
<li>The watch independently uses the RT to renew access tokens when needed</li>
</ol>
<p>This enables a secure, long-lived authentication bridge across devices, even in offline or intermittent connectivity scenarios.</p>
<h2>Developer scenarios unlocked</h2>
<p>This capability is especially impactful for CIAM developers building multi-device ecosystems:</p>
<p><img alt="⌚" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/231a.png" style="height: 1em;" /> <strong>Companion device experiences (Apple Watch)</strong> Enable fully functional, authenticated watch apps without requiring constant phone connectivity.</p>
<p><img alt="📱" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f4f1.png" style="height: 1em;" /> <strong>Background and widget scenarios</strong> Support independent token refresh for widgets and background services running outside the primary app session.</p>
<p><img alt="🚗" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f697.png" style="height: 1em;" /> <strong>Connected experiences (e.g., automotive apps)</strong> Unblock real-world use cases where devices must operate autonomously while maintaining secure access.</p>
<p><img alt="🔒" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f512.png" style="height: 1em;" /> <strong>Consistent authentication across surfaces</strong> Avoid fragmented identity flows and deliver a cohesive, trusted user experience across devices.</p>
<h2>Behind the scenes: Why this matters</h2>
<p>By design, MSAL historically does not expose refresh tokens, prioritizing security by keeping long-lived credentials protected within the SDK. However, this creates limitations for multi-device scenarios where token state must extend beyond a single device.</p>
<p>In practice, customers have already implemented workarounds extracting tokens from secure storage and transferring them manually which introduces inconsistency and risk.</p>
<p>With this GA release:</p>
<ul>
<li>RT access is formally supported via a controlled, opt-in API</li>
<li>Developers receive clear security guidance (encryption, secure transport, revocation)</li>
<li>The platform enables companion device scenarios without requiring unsupported approaches</li>
</ul>
<p>This balances developer flexibility with enterprise-grade security expectations.</p>
<h2>This is just the beginning of cross-device authentication</h2>
<p>RT transfer represents a critical first step toward a broader vision of multi-device SSO and session continuity for Native Authentication.</p>
<p>We are actively investing in:</p>
<ul>
<li>Short-lived session transfer tokens for secure, brokered session handoff</li>
<li>SSO across multiple apps and devices</li>
<li>Advanced token lifecycle and rotation management</li>
<li>Deeper integration with identity security controls (Conditional Access, policy)</li>
</ul>
<p>Our goal is to deliver a modern, secure, multi-surface identity platform for CIAM.</p>
<h2>Ready to get started with Native Authentication?</h2>
<p>To enable refresh token transfer to Apple Watch:</p>
<ol>
<li>Configure Native Authentication in your Entra External ID tenant</li>
<li>Enable RT access via explicit application configuration</li>
<li>Implement secure token transfer (e.g., WatchConnectivity)</li>
<li>Ensure proper handling of token rotation, revocation, and secure storage</li>
</ol>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/concept-native-authentication?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Get Started with Native Authentication</a></div></p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out features in the Microsoft Entra suite of products, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/native-auth-refresh-token-transfer-ga/">General Availability: Refresh Token (RT) Transfer to Apple Watch in Microsoft Entra External ID Native Authentication</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
