### 🔌 Common Services, Explanations, Ports, and Commands

| Service  | Explanation                                       | Port | Command Example                          |
|----------|---------------------------------------------------|------|-------------------------------------------|
| FTP      | File transfer (not secure)                        | 21   | `ftp target.com`                          |
| SSH      | Secure remote login                               | 22   | `ssh user@target.com`                     |
| Telnet   | Remote login (not secure)                         | 23   | `telnet target.com`                       |
| SMTP     | Sending emails                                    | 25   | `telnet target.com 25`                    |
| DNS      | Domain name resolution                            | 53   | `nslookup google.com` / `dig google.com`  |
| HTTP     | Web traffic (unsecure)                            | 80   | `curl http://target.com`                  |
| POP3     | Downloading emails                                | 110  | `telnet target.com 110`                   |
| IMAP     | Reading emails on the server                      | 143  | `telnet target.com 143`                   |
| HTTPS    | Secure web traffic                                | 443  | `curl https://target.com`                 |
| SMB      | Windows file sharing                              | 445  | `smbclient -L //target.com`               |
| RDP      | Remote Desktop (Windows GUI access)               | 3389 | `rdesktop target.com`                     |
| MySQL    | MySQL database access                             | 3306 | `mysql -h target.com -u root -p`          |
| HTTP-Alt | Alternate web service port                        | 8080 | `curl http://target.com:8080`             |
