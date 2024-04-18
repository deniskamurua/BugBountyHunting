 assetfinder --subs-only HOST | gau | egrep -v 
'(.css|.png|.jpeg|.jpg|.svg|.gif|.wolf)' | while read url; do vars=$curl -s 
$url | grep -Eo "var [a-zA-Z0-9_]+" | sed -e 's, 'var','"$url"?',g' -e 's/
//g' | grep -v '.js' | sed 's/.*/&=xss/g'):echo -e "\e[1;33m$url\n"
"\e[1;32m$vars";done
