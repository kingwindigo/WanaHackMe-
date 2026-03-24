# Bookmarklet
### Author: Christian Jay Siton
---

This challenge is a mix of web exploitation and cryptography. It led me to a website where it apparently gave me the bookmarklet.
Since this bookmarklet was in the form of javascript, I tried running it on the browser's console and magically, it returned with a dialog box containing the flag.

This is the bookmarklet contained in the website.
```
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÒËÉ§©í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    
```
<img width="1199" height="368" alt="Screenshot 2026-03-24 103414" src="https://github.com/user-attachments/assets/b8ad16ff-c508-4a41-8846-fc40dfd5511d" />

Alternatively, we could also solve the challenge through the shell using node -e, but we replace alert() with console.log() so the flag can be displayed on the shell:

<img width="555" height="253" alt="Screenshot 2026-03-24 100727" src="https://github.com/user-attachments/assets/bbfa7ebb-dcde-4a9c-8a9e-839a2d00ac07" />
