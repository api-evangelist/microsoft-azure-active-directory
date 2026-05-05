---
title: "General Availability: Email and SMS OTP as Second‑Factor MFA for Native Authentication in Entra External ID"
url: "https://devblogs.microsoft.com/identity/native-auth-mfa-ga/"
date: "Mon, 09 Mar 2026 14:42:45 +0000"
author: "Sasha Mars"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>Today we’re announcing the general availability of Email and SMS one‑time passcode (OTP) as second‑factor MFA for Native Authentication in Microsoft Entra External ID. This enables developers to add step‑up security to native sign‑in and sign‑up flows while keeping users fully inside their applications.</p>
<p>This release focuses exclusively on MFA as a second factor, evaluated after first‑factor authentication completes, and is enforced through Microsoft Entra Conditional Access.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/concept-native-authentication?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Get Started with Native Authentication</a></div></p>
<h2>Clarifying first factor vs. second factor</h2>
<p>Native Authentication in Entra External ID supports distinct authentication stages, allowing developers to layer security only when needed.</p>
<p>Second‑factor MFA is commonly required:</p>
<table>
<thead>
<tr>
<th>Authentication stage</th>
<th>What’s supported</th>
</tr>
</thead>
<tbody>
<tr>
<td>First factor</td>
<td>Email OTP; Email + password (with SSPR)</td>
</tr>
<tr>
<td>Second factor (GA)</td>
<td>Email OTP; SMS OTP</td>
</tr>
</tbody>
</table>
<p>Second‑factor MFA is evaluated only after first‑factor authentication succeeds, enabling step‑up security without adding friction to every sign‑in.</p>
<h2>Why second‑factor MFA matters for native apps</h2>
<p>Consumer and external‑facing applications increasingly require stronger assurance without sacrificing user experience.</p>
<ul>
<li>When higher assurance is needed — such as high‑risk sign‑ins, sensitive user actions, or regulated scenarios.</li>
<li>Without breaking native UX — keeping users fully inside the app while security policies are enforced server‑side.</li>
</ul>
<p>By supporting Email and SMS OTP as a second factor, Native Authentication enables developers to strengthen account security while maintaining fully branded, native authentication experiences.</p>
<h2>What’s now generally available</h2>
<p>With this GA release, developers can now:</p>
<ul>
<li>Enforce MFA after first‑factor authentication in native sign‑in and sign‑up flows.</li>
<li>Use Email OTP or SMS OTP as the second authentication factor.</li>
<li>Rely on Conditional Access to control when MFA is required.</li>
<li>Receive ID and access tokens only after MFA succeeds, with no client‑side enforcement logic.</li>
</ul>
<p>Native Authentication continues to issue tokens only after all required authentication factors have been successfully completed.</p>
<h2>Ready to get started?</h2>
<p>To begin using second‑factor MFA with Native Authentication, configure Conditional Access policies in your Entra External ID tenant and integrate using Native Authentication SDKs or APIs.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/concept-native-authentication-sms-mfa-third-party-fraud-protection?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Secure SMS MFA in native authentication with third‑party fraud protection</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/reference-native-authentication-api?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json&amp;tabs=emailOtp" target="_blank">Native authentication API</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-email-one-time-passcode-sign-in?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add email one-time passcode MFA to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-email-strong-authentication-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add email strong authentication method registration to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-sms-one-time-passcode-sign-in?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add SMS one-time passcode MFA to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-android-sms-strong-authentication-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add SMS strong authentication method registration to your Android app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-ios-swift-email-one-time-passcode-sign-in?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add email one-time passcode MFA to your iOS/macOS app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-ios-swift-email-strong-authentication-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add Email strong authentication method registration to your iOS/macOS app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-ios-swift-sms-one-time-passcode-sign-in?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add SMS one-time passcode MFA to your iOS/macOS app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-ios-swift-sms-strong-authentication-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json" target="_blank">Tutorial: Add Phone SMS strong authentication method registration to your iOS/macOS app</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-react-register-strong-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json&amp;tabs=external-tenant" target="_blank">Tutorial: Register strong authentication method in a React single-page app by using native authentication JavaScript SDK</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-react-enable-mfa?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json&amp;tabs=external-tenant" target="_blank">Tutorial: Enable multifactor authentication in a React single-page app by using native authentication JavaScript SDK</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-angular-register-strong-method?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json&amp;tabs=external-tenant" target="_blank">Tutorial: Register strong authentication method in an Angular single-page app by using native authentication JavaScript SDK</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-angular-enable-mfa?toc=%2Fentra%2Fexternal-id%2Ftoc.json&amp;bc=%2Fentra%2Fexternal-id%2Fbreadcrumb%2Ftoc.json&amp;tabs=external-tenant" target="_blank">Tutorial: Enable multifactor authentication in an Angular single-page app by using native authentication JavaScript SDK</a></div></p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out features in the Microsoft Entra suite of products, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/native-auth-mfa-ga/">General Availability: Email and SMS OTP as Second‑Factor MFA for Native Authentication in Entra External ID</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
