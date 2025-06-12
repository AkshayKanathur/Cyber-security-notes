# Open Redirection
### What is open redirect vuln?
An open redirect vulnerability occurs when a victim visits a particular URL for a given website and
that website instructs the victim's browser to visit a completely different URL, on a separate domain.


Severity: This is a P4 vulnerability under Bugcrowd VRT
### Impact of this vuln
- A user can easily be mislead to a phishing page
- Open redirect in a login or password reset might lead to account takeover
- Open redirect can be powerful when used to chain bugs
- When you find an open redirect, check if SSRF or XSS is possible
### How to find this bug..? 
Get based and post based:
When searching for these types of vulnerabilities you're looking for a GET request sent to the site you're testing with a parameter specifying a URL to redirect.
POST based:
In you can find this vuln while logging in to the web application.
### Parameters to look out for:
dest=			
out=
file=
host=
redirect=
to=
val/validate=
port=
uri=		
view=
domain=
open=
feed=
html=
next=
path=
dir=
callback=
data=
continue=
show=
return=
reference=
url=
navigation=	
page=
site=
window=
### Steps to find
1) Find out the above given parameters after spidering the page.
2) Change the parameter and forward the request.
3) If you get redirected to the URL which you added it is a vulnerability.

Example: 
https://www.example.com/login.html?RelayState=http%3A%2F%2Fevil.com%2Fnext

Here the “ReplyState” parameter needs to be checked for open redirect.

### Types of Exploitation:
1) Redirects the user to completely new domain without realising.
2) Redirects the user to subdomain of the target URL, which isn't a main target domain.
https://hackerone.com/reports/103772
3) Take a note of the services a site uses as they each represent a new attack vector.
https://hackerone.com/reports/111968

You can also search using Google Dorking techniques:

#### Allinurl:
Example: allinurl:ReturnUrl which searches for web pages that have "ReturnUrl" as part of their URL


#### Site:
Example: site:example.com which searches for web pages from example.com