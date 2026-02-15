One of the most difficult problems i encountered, I was mostly doing general knowledge and they were smooth sailing like reading a book, but this problem PIE_TIME really stumped me, extremly, at first i only typed nc rescued-float.picoctf.net 52076, and it would give 
me the main address 0x61bf5e7c333d, but after that i didnt know what to do. i was so confused i downloaded the source code and tried to dechiper its meaning, it took me almost an hour to solve this. but, after a while i remembered about grep, and since the file
was a .log file, i knew i could try and find something, so i tried searching for "FLAG" "FLAGPART" with no avail, but then, i searched "win" and there i found another hexadecimal address "00000000000012a7", now i didnt know what to do with that so i tried to
just input that and of course it didnt work, so i continued around and tried to add 12a7 to my original main address and it didnt work, so i went back to search for keywords then i stumbled upon another hexadecimal by searching "main"
"000000000000133d" and i knew it had something to do with the original from win, then i started to think, 133d is bigger than win, so i tried to subtract 12a7 from 133d and got 96, with the knowledge of hexadecimals i learned that win MUST be around 96 address and
it was the offset, so i went back and got my main address again, then there i subtracted the main address and 97, which got me the last digits as 2A7 and there i found the key, it rewarded me with the flag 

overall this was a very fun and difficult challenge, stumped me alot and made me think

what i learned:
The basics of hexadecimals and its addresses
I learned how to use gerp when the vulnerability is a file
I learned how to get the bits and pieces of information to get the key
I learned the usage of nm vuln | grep 'keyword'


<img width="1832" height="398" alt="image" src="https://github.com/user-attachments/assets/d6e249e8-f0a3-4c84-b706-3f8246e90a82" />



<img width="929" height="578" alt="image" src="https://github.com/user-attachments/assets/fa82cebf-a526-482d-926a-6ccb566184df" />

