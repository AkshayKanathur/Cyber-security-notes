OTP Bypass
What is OTP?
 * One Time Password.
 * Used for authentication, replacing older "username:password" methods.
 * Developers may miss certain logic checks during implementation, leading to vulnerabilities.
Common OTP Flaws (Methods to find bugs):
 * OTP Reusability:
   * The OTP, once used, does not expire and can be used to log in again.
 * OTP Brute Force:
   * OTP can be brute-forced using automated tools (e.g., Burp Suite) or scripts.
   * While seemingly long, this can be achieved quickly with multithreading and licensed tools.
 * OTP Bypass Using Response Manipulation:
   * This is application-specific and can vary.
 * Using Default Code:
   * Trying common default codes like "00000".
Mitigations (Best Practices for OTP):
 * Implement OTP expiry.
 * Implement OTP client and server-side verification, not just response verification.
 * Discard the OTP after 3 or 5 wrong attempts and send a new OTP for subsequent attempts.
