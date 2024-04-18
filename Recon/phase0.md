First run whatthefuckisthis
# wtfis -s -g -m-1 domain.com
1. Reverse whois
> https://viewdns.info/reversewhois/

2.Reverse dns
#  nslookup -type=NS domain.com

3. Whois
> https://www.whois.com/whois/

4.Reverse DNS
> http://domaineye.com/

5.Reverse IP
> http://domaineye.com/

6. ASN
Use [http://bgp.he.net] to get ASN numbers then use asnmap [~/go/bin]  to get the ip ranges [# echo AS10695 | ./asnmap] 
# amass intel -org facebook (enter the orrganisation you are testing)

 Domains running on a given ASN
# amass intel -asn <asn number>

7. GOOGLE DORKING

# Google Dorks
## List
- inurl:example.com intitle:"index of"
- inurl:example.com intitle:"index of /" "*key.pem"
- inurl:example.com ext:log
- inurl:example.com intitle:"index of" ext:sql|xls|xml|json|csv
- inurl:example.com "MYSQL_ROOT_PASSWORD:" ext:env OR ext:yml -git
- inurl:example.com intitle:"index of" "config.db"
- inurl:example.com allintext:"API_SECRET*" ext:env | ext:yml
- inurl:example.com intext:admin ext:sql inurl:admin
- inurl:example.com allintext:username,password filetype:log
site:example.com "-----BEGIN RSA PRIVATE KEY-----" - inurl:id_rsa
- site:codepad.co "keyword"
- site:scribd.com "keyword"
- site:npmjs.com "keyword"
- site:npm-runkit.com "keyword"
- site:libraries.io "keyword"
- site:ycombinator.io "keyword"
- site:coggle.it "keyword"
- site:papaly.com "keyword"
- site:google.com "keyword"
- site:trello.com "keyword"
- site:prezi.com "keyword"
- site:jsdelivr.net "keyword"
- site:codepen.io "keyword"
- site:codeshare.io "keyword"
- site:sharecode.io "keyword"  
- site:pastebin.com "keyword"
- site:repl.it "keyword"
- site:productforums.google.com "keyword"
- site:gitter.im "keyword"
- site:bitbucket.org "keyword"
- site:*atlassian.net "keyword"
- inurl:gitlab "keyword"
- inurl:github "keyword"


