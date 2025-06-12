# Broken Link Hijacking
### What is brocken link hijacking?
Broken Link Hijacking (BLH) exists whenever a target links to an expired domain or page.
### Imapct
When a company deletes their social media account they might forget to remove the link from their website. An attacker can create an account on the social media platform with that username and impersonate the company.
### Methodology to find this vuln
The attacker finds the broken link.
Creates a account in the same name Yokohama.
Now go to the vulnerable site and click for the hijacked social media logo.
It will redirect to your social media account.
### Tools to check
- www.brokenlinkcheck.com/
Broken Link Checker
- https://github.com/stevenvachon/broken-link-checker