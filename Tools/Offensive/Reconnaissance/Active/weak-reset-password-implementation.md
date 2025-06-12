Weak Reset Password Implementations & Lack of Password Confirmation
Topics Covered:
 * Lack of Password Confirmation
 * Cookie without missing secure flag
 * Weak Reset Password Implementations
 * Mitigations
Lack of Password Confirmation on Delete Account
 * Vulnerability Description: The account deletion process, a sensitive part of a web application, should validate the user's authenticity, but it fails to ask for the password to confirm the real user.
 * Exploit Scenario:
   * A user logs into a shared computer (office, library, cafe) and leaves their account open.
   * An intruder can easily delete the account because the system doesn't require password validation for deletion.
 * Severity: P4 vulnerability under Bugcrowd VRT.
Weak Reset Password Implementations
Cases of Weak Password Implementation:
 * Case 1: Token Not Invalidated After Use
   * Severity: P4
   * Replication Steps:
     * Request a password reset link for the target domain.
     * Open the reset password link in two separate tabs.
     * Reset the password using the first tab.
     * Attempt to reset the password again using the second tab.
     * If successful, the same token allowed multiple password resets.
 * Case 2: Token Not Invalidated After Email Change
   * Severity: P5
   * Replication Steps:
     * Request a password reset link for the target domain.
     * Log into the account and change the associated email address.
     * Open the original reset password link from the mail and attempt to reset the password.
     * If successful, the password can be reset even after the email address has been changed.
 * Case 3: Token Not Invalidated After Password Change
   * Severity: P5
   * Replication Steps:
     * Request a password reset link for the target domain.
     * Log into the account and change the password normally.
     * Open the original reset password link from the mail and attempt to reset the password.
     * If successful, the password can be reset even after it has already been changed.
 * Case 4: Token Has Long Timed Expiry
   * Severity: Informational
   * Description: The suitable time for token expiration is one hour. Report if it's greater than that.
 * Case 5: Token Not Invalidated After New Token Requested
   * Severity: P4-P5
   * Replication Steps:
     * Request a password reset link for the target domain.
     * Do not use this link; keep it in the email inbox.
     * After some time, repeat step 1 (request a new password reset link).
     * Use the second password reset link (from step 3) to change the password.
     * After changing the password, attempt to use the first password reset link (from step 1).
     * If successful, the first password reset link is not expired even after a new token was requested and used.
 * Case 6: Token Not Invalidated After Login
   * Severity: P5
   * Replication Steps:
     * Request a password reset link for the target domain.
     * Log into the account normally.
     * Go to the email and open the reset password link, then attempt to reset the password.
     * If successful, the password can be reset even after having logged into the account.
