waybackurls HOST | gf xss | sed 's/=.*/=/' | sort -u | tee FILE.txt && cat 
FILE.txt | dalfox -b YOURS.xss.ht pipe > OUT.txt
