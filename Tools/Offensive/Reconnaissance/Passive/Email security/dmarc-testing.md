What is DMARC record?

DMARC is an abbreviation for **Domain-based Message Authentication, Reporting & Conformance**. Basically, it is an email authentication protocol that builds on SPF and DKIM. It helps domain owners **specify how to handle emails that fail authentication** and provides **reports** about spoofed messages.

Only emails that pass SPF and/or DKIM (as defined by policy) are considered valid. It ensures better control over what happens when email spoofing is detected.

Tools to check DMARC records:

1) https://mxtoolbox.com/DMARC.aspx  
2) https://dmarcian.com/dmarc-inspector/

Tools to manually test/report DMARC issues:

1) https://emkei.cz/ (can be used to send spoofed emails and see how DMARC handles it)

No DMARC record is considered a vulnerability.  
**No DMARC record = domain owner has no control over spoofed email handling** → spoofed emails might get delivered normally or inconsistently depending on the recipient’s mail server policy.