# Clickjacking
### What is Clickjacking ?
Clickjacking is a method of tricking website user into clicking on a Harmful Link , By disguising the link as something else.
Clickjacking won’t affect your site directly, but it could potentially affect your users.
### Attackers may abuse clickjacking vulnerabilities for many different purposes:
- To gain followers on social media and then, possibly, sell the social media account/page for mass marketing.
- To gain subscribers for the same purpose as social media followers.
- To use the fact that the user is logged into their e-commerce account and have them buy products on behalf of the attacker.
- To have the user unknowingly transfer funds to the attacker.
- To have the user download malware (e.g. a trojan).
### Methods to check clickjacking 
1)
```shell
<html> 
  <head> 
    <title>Clickjack test page</title> 
  </head> 
  <body> 
    <p>Website is vulnerable to clickjacking!</p> 
    <iframe src="http://www.yoursite.com/sensitive-page" width="500" height="500"></iframe> 
  </body> 
</html>
```
- Step 1 : Change yoursite.com to target website and save the code
- Step 2 : Copy Paste the following code in Notepad and save it as example.html 
- Step 3 : Open the example.html saved file in your browser
2) http://samy.pl/quickjack/quickjack.html 
3) https://securityheaders.com 
4) GitHub Download Link -https://github.com/shifa123/clickjack 
5) https://clickjacker.io/
