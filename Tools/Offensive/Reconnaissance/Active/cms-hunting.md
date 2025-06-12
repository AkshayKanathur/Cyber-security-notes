# CMS Vulnerability Hunting
### What is CMS?
1. A content management system (CMS) is a software application that enables users to create, edit, collaborate on, publish and store digital content. CMSes are typically used for enterprise content management (ECM) and web content management (WCM).
2. A CMS provides a graphical user interface with tools to create, edit and publish web content without the need to write code from scratch.
### Why CMS Hunting?
Many of the CMS available there have public CVEs for certain versions, if the CMS version being used by your target website has any CVE, this opens a way to find vulnerability.
### How to do CMS Hunting?
- Use the tool to get information about vulnerable plugins.
- Link: https://github.com/Moham3dRiahi/XAttacker
- Installation: 
  1) git clone https://github.com/Moham3dRiahi/XAttacker.git
  2) cd XAttacker
  3) perl XAttacker.pl
- Commad: perl XAttacker.pl -l probed.txt
- Once you get any vulnerable plugins name just google and look for public exploits of the same.
