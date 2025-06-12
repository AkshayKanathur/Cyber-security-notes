# CSRF - Cross-Site Request Forgery
### What is CSRF?
 * A type of attack that tricks an authenticated victim into performing malicious tasks on a web application on behalf of an attacker.
 * The severity of the attack depends on the victim's privilege level.
 * Attackers use the victim's current session authentication to execute malicious tasks.
 * Also known as "Session Riding."
 * Exploits the concept that all requests from an authenticated user are assumed to be originated by that user.
 * Attackers exploit this by identifying and using the session cookie to send their own payload to the application.
### How Does CSRF Work?
 * CSRF only works if the victim is authenticated.
 * It involves two main parts:
   * Tricking the victim: Using social engineering to make the victim perform an action (e.g., login, logout) on a page.
   * Sending a "forged" request: A legitimate-looking request is sent to the victim's browser, containing attacker-desired values and any associated cookies the victim has for that website.
 * The browser automatically sends relevant cookies with every request to remember user interactions (since HTTP is stateless).
 * If the session is valid, the web application considers these forged requests as original, allowing the attacker to perform actions based on the victim's authorization level.
### Flow of a General CSRF Attack:
 * Attacker captures a request for an action (e.g., password change, login, logout) by performing it themselves.
 * Attacker crafts a malicious request using tools like Burp Suite.
 * Attacker sends the crafted request (e.g., via a malicious link) to the victim.
 * When the victim opens the request/link, the intended action is executed without their knowledge.
### Requirements for a Valid CSRF (Nowadays):
 * Lack of Password Confirmation
 * Lack of anti-CSRF tokens
 * Impact Severity:
   * P3 if on email change.
   * P3-P2 if on insecure account deletion (depending on the program).
### Types of CSRF:
 * URL-based CSRF:
   * Easily exploited by crafting a specific URL.
   * Affects requests using the GET HTTP Method.
 * Form-based CSRF:
   * Requires forcing the end-user to submit data through a malicious form.
   * Can be used against requests accepting the POST HTTP Method.
 * Embedded CSRF:
   * Won't work against modern browsers unless Access-Control-Allow-Origin is set to "*".
   * Works for almost all CSRF-vulnerable requests, regardless of their allowed methods.
### Best Way to Hunt for CSRF:
 * Identify all endpoints where the application initiates and executes actions.
 * Apply tests for all three types of CSRF (URL-based, Form-based, Embedded).
### General Exploit Scenario:
 * Attacker creates a CSRF HTML link.
 * Attacker sends the link to the victim via email, chat, etc., using social engineering to increase the chances of the victim clicking it.
 * When the victim clicks the link, the attacker's desired request is executed, completing the exploit.
   * Example: If a CSRF vulnerability exists for transactions, clicking a malicious link could transfer funds from the victim's account to the attacker's account (hypothetical).
