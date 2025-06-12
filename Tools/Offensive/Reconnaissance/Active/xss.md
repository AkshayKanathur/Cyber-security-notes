Cross-Site Scripting (XSS)
What is XSS?
 * A client-side code injection vulnerability.
 * An attacker can inject malicious code (typically JavaScript) into a legitimate website or web application.
 * When a user visits the compromised site, their browser executes the malicious code.
Impact of XSS:
 * Steal cookies and session tokens.
 * Deface websites.
 * Redirect users to malicious sites.
 * Perform actions on behalf of the user (e.g., change passwords, make purchases).
Types of XSS:
 * Stored XSS (Persistent XSS):
   * The malicious script is permanently stored on the target server.
   * Example: Injected into a database via a comment field or forum post.
   * When other users retrieve this stored information, the script is executed in their browsers.
   * Attack Scenario:
     * Attacker posts a comment with XSS payload (<script>alert(document.cookie)</script>).
     * The comment is stored in the database.
     * When a victim views the comment, the script executes, sending their cookie to the attacker.
   * Impact: Can lead to account takeover, data theft, or website defacement.
 * Reflected XSS (Non-Persistent XSS):
   * The injected script is reflected off the web server, such as in an error message, search result, or any other response that includes data sent by the user as part of the request.
   * The attack requires the victim to click on a specially crafted link that includes the malicious script.
   * Attack Scenario:
     * Attacker crafts a URL with a malicious payload (e.g., www.example.com/search?q=<script>alert('XSS')</script>).
     * Attacker sends this URL to the victim.
     * Victim clicks the link; the server reflects the payload, executing it in the victim's browser.
   * Impact: Primarily used for phishing and session hijacking.
 * DOM-Based XSS (Type-0 XSS):
   * The vulnerability lies in the client-side code rather than the server-side code.
   * The malicious script is executed when the browser parses the DOM (Document Object Model) structure, without the server's involvement in reflecting the payload.
   * Attack Scenario:
     * Attacker crafts a URL like www.example.com#<script>alert('XSS')</script>.
     * Victim visits the URL.
     * Client-side JavaScript reads the fragment (#...) from the URL and dynamically writes it to the page, causing the script to execute.
   * Impact: Can bypass Content Security Policy (CSP) and lead to data theft.
Common XSS Payload/Test Cases:
 * Simple alert: <script>alert(1)</script>
 * Image error: <img src=x onerror=alert(1)>
 * SVG animation: <svg/onload=alert(1)>
 * Body onload: <body onload=alert(1)>
 * Iframe srcdoc: <iframe srcdoc='<script>alert(1)</script>'>
 * Input with XSS: <input onfocus=alert(1) autofocus>
 * Meta refresh: <meta http-equiv="refresh" content="0;url=javascript:alert(1);">
 * Using javascript: protocol: <a href="javascript:alert(1)">Click Me</a>
 * Data URI: <img src="data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAAE" onerror="alert(1)"> (This one is not a direct XSS, but demonstrates code execution on error)
 * Other tags: <details open ontoggle=alert(1)>, <marquee onstart=alert(1)>, <video poster onloadstart=alert(1)>
Finding XSS:
 * Manual Inspection:
   * Look for input fields, URL parameters, HTTP headers, and dynamic content.
   * Inject basic XSS payloads like <script>alert(1)</script>.
   * Check if the alert box appears or if the payload is reflected in the HTML source.
 * Using Tools:
   * OWASP ZAP: Web vulnerability scanner.
   * Burp Suite: Web penetration testing tool with an active scanner.
   * XSSer: Automated XSS testing tool.
   * Arachni: Open-source web application security scanner.
Mitigation Strategies:
 * Input Validation and Sanitization:
   * Validate and sanitize all user input before processing or displaying it.
   * Use a whitelist approach to allow only safe characters and patterns.
   * Encode output to prevent browser interpretation of malicious scripts.
 * Output Encoding:
   * Convert special characters into their entity equivalents before rendering user-supplied data in HTML, URL, or JavaScript contexts.
   * Example: < becomes &lt;, > becomes &gt;.
 * Content Security Policy (CSP):
   * A security mechanism that allows web administrators to control resources (scripts, stylesheets, etc.) that the user agent can load for a given page.
   * Helps prevent XSS by restricting the sources of executable scripts.
 * HTTP-only Cookies:
   * Set cookies with the HttpOnly flag to prevent client-side scripts from accessing them, mitigating cookie theft.
 * Secure Development Practices:
   * Follow secure coding guidelines and conduct regular security audits.
   * Implement a robust security development lifecycle (SDL).
   
