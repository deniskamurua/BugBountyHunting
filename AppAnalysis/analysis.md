
# ANALYSIS CONCEPT

# Ask and answer these questions for the application

1. What stack/languages are used?
2. What server is running the application?
3. Is there a WAF?
4. What additional libraries are used? Are there known exploits for these libraries?  Custom JS Llbraries?
5. Is there Authentication?
    - Username
    - Email
    - OAuth
    - OAuth w/ OpenID Connect
    - SSO
    - MFA
    - Reset Password
    - OTP
6. What Objects are used?  
7. How is session established?
    ~ Cookie?
    ~ Bearer Token?
    ~ JWT?
    ~ Is it serialized? (Java, PHP, .NET, Python)
8. Are there useful comments?
9. How does it handle special characters?
10. Can you trigger any error messages?
    ~ Send malicious characters to every parameter
        - Emojis
        - List of naughty strings (SecLists)
    ~ Change parameters to array
        EX: http://example.com/search.php?q[]=test
11. What common features are present?
    ~ Edit Profile
    ~ Email/Messaging
    ~ File Upload
    ~ Shopping/Checkout
    ~ Webhook
    ~ Flight/Hotel Booking
    ~ Banking
12. How is a user identified?
13. Are there multiple user roles?
14. Is there an API?
15. Is there an Content Management System?
16. Is there a Content Security Policy?
17. Is CORS implemented?
18. Is Captcha used?
19. Are WebSockets used?
20. Is the source code publicly available?


# Ask yourself these questions about the server hosting the application
1. What ports are open?
2. What services are running on those ports?
3. Is it hosted in the cloud?
    - Check org's ASN #'s
    - Check IP against known AWS/Azure IP ranges
4. Is it hosting multiple apps using VHosting?
5. What is the OS?
6. Can you get the kernel version?



# Tech PROFILING
Identifying Web Server, programming language and frameworks
> wappalyzer
> builtwith
both firefox extensions

# The Big Questions
1. How does the app pass data? 

>Does it use a resource, parameter, value, format? https://app.com/resource?parameter=value&param2=value
Or does it use a RESTful format?
> https://app.com/route/resource/sub-resource/.

2. How/where does the app talk about users? 
> Where : cookiees, ApiCalls or JWT
> How : UID, UUID, EMAIL. username

3. Does the app have multi-tenancy or user levels?
> is it designed for multiple users? if so does it have multiple user levels

4. Does the app have a unique threat model?
5. Has there been past security research & vulns? 
6. How does the app/framework handle specific vuln classes?
> how does it handle XSS

7. How does the app store Data?
>Where are images and file uploads going?
> Which type of database do you thing they are using?



# HEAT MAPPING 
where Vulnelabilities commonly appear
