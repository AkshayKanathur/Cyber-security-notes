# Directory Brute-Forcing

Tools used to discover hidden or unlinked directories and files on a web server by systematically guessing names from a wordlist. Useful during reconnaissance to find admin panels, backups, configuration files, or other sensitive resources not meant to be publicly accessible.

## Dirbuster

#### Description
Performs directory brute-forcing on websites.

#### Command
```shell
dirbuster -u <url> -w <wordlist>
```
#### Use Case
Used to find hidden folders or files on a web server.

## Dirsearch

#### Description
Fast command-line tool for directory brute-forcing with advanced options like threading, status code filtering, and reporting.

#### Command
```shell
dirsearch -u <url> -e php,html -t 50
```

Or for batch scanning:
```shell
dirsearch -l subdomain.txt -t 100 --plain-text-report=dir.txt -i 200,403
```
#### Use Case
Used to discover hidden paths efficiently; suitable for automation and large-scale scans.
