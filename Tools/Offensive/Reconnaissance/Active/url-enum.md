# URL Enumeration

URL enumeration is noting but extracting /enumerating all the links or URLs from domains.

## GAUPLUS

- Get All URLs (gau) fetches known URLs from AlienVault's Open Threat Exchange, the Wayback Machine, and Common Crawl for any given domain. Inspired by Tomnomnom’s waybackurls. Since 3 Sources so more urls.
- Link: https://github.com/bp0lr/gauplus
- Command: ```cat subs.txt | gauplus -o urls3.txt```

## Waybackurls

- Waybackurls is also a made by tomnomnom, this tool built on Go lang and url enumeration speed is very quick. fetch known URLs from the Wayback Machine for *.domain and output them on stdout.
- Link: https://github.com/tomnomnom/waybackurls.git
- Command: ```cat subdomain.txt | waybackurls | tee urls.txt```

## Arjun

- Arjun can find query parameters for URL endpoints & this is tool is best for finding hidden parameters.
- Link: https://github.com/s0md3v/Arjun.git
- Command: ```arjun -i probed.txt -t 100 --passive -oT arjun_params.txt```

## paramspider

- Best Parameter miner tool.
- Finds parameters from web archives of the entered domain.
- Finds parameters from subdomains as well.
- Link: https://github.com/devanshbatham/ParamSpider.git
- Command: ```python3 paramspider.py --domain example.com -o paramslist.txt```

## Gf tool

- This tool is Used for sorting parameters depending on vulnerability.
- Link: https://github.com/tomnomnom/gf
- Link: https://github.com/1ndianl33t/Gf-Patterns
- Command:
```cat params.txt | gf sqli > sqli.txt```
```cat params.txt | gf xss > xss.txt```
