# Subdomain enumeration

As a penetration tester or a bug bounty hunter, most of the times you are given a single domain or a set of domains when you start a security assessment. You’ll have to perform extensive reconnaissance to find interesting assets like servers, web applications, domains that belong to the target organization so that you can increase your chances of finding vulnerabilities.

Example: xyz.facebook.com

Here xyz is the subdomain of facebook.com

## Subscraper

- SubScraper is a subdomain enumeration tool that uses a variety of techniques to find potential subdomains of a given target. 
- This is especially helpful during penetration testing or bug bounty hunting to uncover additional attack surfaces.
- Link: https://github.com/m8r0wn/subscraper.git
- Command:
```shell
subscraper target.com --censys-api api-key --censys-secret secret-key -o subs.txt
```
## Subfinder

- Subfinder is a subdomain discovery tool that discovers valid subdomains for websites by using passive online sources.
- Link: https://github.com/projectdiscovery/subfinder.git
- Command:
```shell
subfinder -d example.com -t 100 -v -o sub.txt
```
## Github-Subdomains

- This tool is used to enumerate subdomains from GitHub
- Link: https://github.com/gwen001/github-subdomains.git
- Command:
```shell
github-subdomains -d target.com –t TOKENSFILE -o subs2.txt
```
## Findomain

- Findomain is the Premium subdomain enumerator which contains multiple tools in it.
- Link: https://github.com/Findomain/Findomain
- Command:
```shell
findomain -t example.com
```
## Amass

- The OWASP Amass Project performs network mapping of attack surfaces and external asset discovery using open source information gathering and active reconnaissance techniques.
- Link: https://github.com/OWASP/Amass
- Command:
```shell
amass enum -src -ip -brute -d example.com -o allsub.txt
```
## Assetfinder

-  Find domains and subdomains related to a given domain
-  Link: https://github.com/tomnomnom/assetfinder
-  Command:
```shell
assetfinder -subs-only <target.com> > allsub3.txt
```
