site="URL"; gau "$site" | while read url; do target=$(curl -sIH "origin:
https://evil.com" -X GET $url) | if grep 'https://evil.com'; then 
[Potentional CORS Found] echo $url; else echo Nothing on "$url"; fi; done
