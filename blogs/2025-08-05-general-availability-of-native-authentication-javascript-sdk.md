---
title: "General Availability of Native Authentication JavaScript SDK"
url: "https://devblogs.microsoft.com/identity/native-auth-javascript-sdk-ga/"
date: "Tue, 05 Aug 2025 16:45:38 +0000"
author: "Sasha Mars"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>Today we announce that Native Authentication JavaScript SDK for Microsoft Entra External ID is now Generally Available! Initially <a href="https://devblogs.microsoft.com/identity/native-auth-for-external-id-ga/" target="_blank">released in 2024</a>, Native Authentication empowers developers to build sign-in, sign-up and sign-out experiences for single page applications (SPAs) in Entra External ID.</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-native-authentication-single-page-app-sdk-sign-in?tabs=react" target="_blank">Get Started with Native Authentication JavaScript SDK</a></div></p>
<h2>How to use native authentication JavaScript SDK</h2>
<p>You can add native authentication to your single page applications (SPAs) by using the <a href="https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-native-authentication-single-page-app-sdk-sign-in?tabs=react" target="_blank">Microsoft Authentication Library (MSAL) for JavaScript</a> with the native authentication extensions. Whenever possible, use MSAL to integrate native authentication for SPA experiences. If you’re targeting platforms not supported by MSAL, use the underlying <a href="https://learn.microsoft.com/en-us/entra/identity-platform/reference-native-authentication-api?tabs=emailOtp" target="_blank">authentication APIs</a> directly.</p>
<h3>Install MSAL SDK and Import Native Authentication Extension</h3>
<pre lang="php"><code>npm i @azure/msal-browser</code></pre>
<p>MSAL abstracts the protocol and exposes simple, scenario-based APIs. For example, to sign a user in using an email one-time passcode (OTP) flow, your app starts the sign-in with the user’s email. MSAL drives the next step by returning a state indicating that a code is required; you then collect the OTP and submit it to complete sign-in.</p>
<p>Below is a JavaScript/TypeScript example that signs a user in using the email OTP flow. The signIn method returns a result that contains a state object. That state can represent different steps (for example, “code required”, “password required”, “complete”, or “failed”). Your code inspects the state and proceeds accordingly.</p>
<h3>Sign In with Email One-Time Passcode (OTP)</h3>
<pre lang="JavaScript"><code>import { 
 CustomAuthPublicClientApplication, 
 SignInCompletedState, 
 SignInCodeRequiredState, 
 SignInPasswordRequiredState, 
 AuthFlowStateBase, 
 ICustomAuthPublicClientApplication, 
} from "@azure/msal-browser/custom-auth"; 
// Create the client 
const authClient: ICustomAuthPublicClientApplication = 
await CustomAuthPublicClientApplication.create(customAuthConfig); 
// Start sign-in with the user's email (username) 
const actionResult = await authClient.signIn({ username: emailAddress }); 
// Inspect the result state and proceed 
if (actionResult.isCodeRequired()) { 
// Next step: prompt user for the OTP code (e.g., via a form) 
 const submitCodeResult = await actionResult.state.submitCode(code); 
 if (submitCodeResult.isCompleted()) { 
// Handle sign-in success 
 const accountData = submitCodeResult.data; // CustomAuthAccountData 
  } 
}</code>  </pre>
<h3>Handling Common Error Scenarios</h3>
<p>Map well-known errors to user-friendly messages and remediation steps:</p>
<pre lang="JavaScript"><code>const result = await authClient.signIn({ username: emailAddress }); 
if (result.isFailed()) { 
  const err = result.error; 
  if (err?.isUserNotFound()) { 
    // User not found 
  } else if (err?.isInvalidUsername()) { 
    // Invalid email/username 
  } else if (err?.isInvalidCode()) { 
    // Code incorrect (if code was required earlier) 
  } else if (err?.isRedirectRequired()) { 
    // Fallback to delegated (web-based) sign-in when native cannot proceed 
  } else { 
    // Generic error 
    // err?.errorData?.errorDescription 
  } 
}</code> </pre>
<p>Ready to get started?</p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-react-sdk-sign-in" target="_blank">Get Started with Code Samples in React</a></div></p>
<p><div class="d-flex justify-content-center"><a class="cta_button_link btn-primary mb-24" href="https://learn.microsoft.com/en-us/entra/identity-platform/tutorial-native-authentication-single-page-app-angular-sign-in" target="_blank">Get Started with Code Samples in AngularJS</a></div></p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out features in the Microsoft Entra suite of products, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/native-auth-javascript-sdk-ga/">General Availability of Native Authentication JavaScript SDK</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
