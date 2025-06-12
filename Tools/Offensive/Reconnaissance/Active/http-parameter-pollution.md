HTTP Parameter Pollution (HPP)
What is HPP?
 * Manipulating how a website processes parameters in HTTP requests.
 * Occurs when injected parameters are trusted by a vulnerable website, leading to unexpected behavior.
 * Can happen on the back-end (server-side) or client-side (browser).
Types of HPP:
 * Server-Side HPP:
   * Sending unexpected information to servers to make server-side code return unexpected results.
   * Requires identifying potentially vulnerable parameters and experimenting with them, as server-side code is not visible.
   * Example (Bank Transfer):
     * Initial URL: https://www.target.com/transfer?from=12345&to=67890&amount=6000
     * Polluted URL: https://www.target.com/transfer?from=12345&to=67890&amount=6000&from=ABCDE
     * If vulnerable, the server might trust the last from parameter (ABCDE), transferring money from that account instead of 12345.
 * Client-Side HPP:
   * Injecting parameters into a URL that are reflected back on the page to the user.
Main HPP Attack Scenarios:
A) Account Takeover Scenario (via Password Reset):
* Basic Requirement: Functionality to send a reset email.
* Steps:
1.  Enter your email in the password reset function and intercept the request.
2.  Pollute the email parameter:
* Add an extra email using & (e.g., &email=attacker@example.com).
* Replace the original email.
3.  Forward the request.
B) Parameter Tampering (e.g., Reducing Product Cost):
* Basic Requirement: E-commerce website.
* Steps:
1.  Turn on interception and click on a product to buy.
2.  Find the amount parameter and change its value.
3.  Forward the request and continue changing the amount.
4.  If the changed amount is reflected, the site is vulnerable.
Extra Resources:
 * Account Takeover POCs:
   * https://youtu.be/i8iGkc7BYiI
   * https://youtu.be/LO3f43cz794
 * Parameter Tampering Writeups:
   * https://suneets1ngh.medium.com/parameter-tampering-ddd9b3de0da8
   * https://medium.com/@novan.rmd/how-to-get-easy-from-bug-bounty-web-parameter-tampering-e6aad5a68658
 * Sample Report: https://hackerone.com/reports/682344
 * Concept Video: https://youtu.be/QVZBl8yxVX0
 * XSS Bypass: https://youtu.be/ldyK2AG9168
 * 
