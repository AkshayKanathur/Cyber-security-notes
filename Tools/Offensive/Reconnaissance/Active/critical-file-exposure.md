# Critical file vulnerability 
The targeted files are often configuration files that contain critical information for the operation of the application or website. The attacker can access this type of files if the server is not properly configured. For example, if access to indexes has not been blocked, the attacker can easily access to the sensitive files.
Some example of critical files are: 
1) !.htpasswd
2) !.gitignore
3) .htusers
4) /debug/pprof
### Method-1 STEPS:
1. Go to the target website.
2. Type /idnf in URL and intercept the request in BurpSuite.
3. Send this request to intruder.
4. Go to positions tab and clear all injection point (clear $), select 'idnf' as the injection
point(add $).
5. Go to Payloads and load the CrticalFile.txt and start attack.
6. Lookout of '200' response code.
7. When you get '200' code right click and click on show response in browser.
8. Check if you got any sensitive data by reading the response. ; )
### Method-2 STEPS:
1. Go to https://github.com/maurosoria/dirsearch
2. git clone https://github.com/maurosoria/dirsearch.git
3. cd dirsearch
4. wget https://raw.githubusercontent.com/danielmiessler/SecLists/master/Dis covery/Web-Content/golang.txt
5. Now use the command:
```shell
python3 dirsearch.py -u ‘(target url) ' -e * -w golang.txt-x 404,301,500,400 -t 80 dirsearch -u https://example.com/ -e php,asp,aspx,jsp,py,txt,conf,config,bak,backup,swp,old,db,sqlasp,aspx,aspx~,asp~,py,py~,rb,rb~,php,php~,bak,bkp,cac he,cgi,conf,csv,html,inc,jar,js,json,jsp,jsp~,lock,log,rar,old,sql,sql.gz,sql.zip,sql.tar.gz,sql~,swp,swp~,tar,tar.bz2,tar.gz,tx t,wadl,zip,json,html,css,java,xml -i 200
```
### How to know if what you have found is a sensitive information or not?
1) Just do some recon on google.
##### Some Examples with Severity:
1) Password Disclosed(P1)
2) Private API Keys Disclosed(P1)
3) Source Code Disclosed(P4)
4) Oauth Secrets Disclosed(Depends on Program)
5) Admin Panel Accessible.(P1 if you can enter admin account).
