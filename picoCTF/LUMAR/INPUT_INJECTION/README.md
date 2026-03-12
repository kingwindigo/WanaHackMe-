<img width="936" height="627" alt="image" src="https://github.com/user-attachments/assets/03a492f6-3411-4726-8a9e-a4a62ddf3777" />

In this picoCTF challenge, it took me quite a long while to get, approximately around 7 hours. at first point i was greeted with a simple interface that showed the addresses of username and then the shell. after that it asked for my username, so there i thought
i had to do some exploitation in that point. I initially didnt know what to do so i just tested aroundlike copy pasting the address and inputting the addresses where it asked for my username, but it didnt really do much of anything, so i just fiddled around
then, at one point i realized that the addresses last 3 digits never really changed, based on my previous picoCTF challenge called PIE, and the 2nd hint, i knew i could get something related to the win flag if i get the offsets of those addresses, so i did so

<img width="748" height="368" alt="image" src="https://github.com/user-attachments/assets/c98cdb3c-ef63-47a4-8e91-15d0c87d2f68" />

which gave -30, now, i didnt know what it was, so i opted to download the source code hoping to find something interesting, at the source code there i found a very peculiar vulnerability 

<img width="286" height="66" alt="image" src="https://github.com/user-attachments/assets/d194e2af-da8e-429b-80df-4094009ab593" />

it was an unprotected scanf that was using %s, based on other easy challenges i also knew i needed to overflow the buffer, but i didnt know how much so i first tried 28 since the memory allocation of username was 28

<img width="307" height="46" alt="image" src="https://github.com/user-attachments/assets/f5a02cd5-2b91-42b7-bb1a-9260f435e593" />

but it didnt work, so i tried 30, but it also didnt work, now, this part i was very confused so i just started to fiddle, in all honesty i tried to brute force 1-20 bytes before stopping since i didnt really think of anything, so i really tried my best to think, i
watched a YT video about hexadecimals to try and relearn what i missed, then i realized hexadecimal is different from base 10, which got me thinking to convert the offset i got which was 30 into base 10, which got me 48
i then tried to overflow the buffer with 48 junk letters

<img width="622" height="91" alt="image" src="https://github.com/user-attachments/assets/0f402273-f506-4aa4-bb84-3e35509ca01b" />

Success! i thought, after that i tried to input the addresses of shell and username but it didnt work, then i thought about it and realized thats not the winning condition, i still had to do more. I went around to think for about 2 hours and was stuck at a 
bottleneck, so i turned to other community members and asked them, they didnt give me the answer but gave me various hints, one of them told me to use this /bin/cat and /home/ctf-player/flag.txt, they explained that /bin/cat is used to get the
binary path of the system no matter where it is located, and then told me that /home/ctf-player/flag.txt was the flag location. he told me to try and study what to do using those information so i did. but before that i simply just tried to input it
/bin/cat/home/ctf-player/flag.txt. then i notice the output, it only printed "Hello, AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA/bin/cat/home/ctf-player/flag.txt. Your shell is /bin/cat"
i was wondering why it stopped there, then i realized that scanf %s stops reading after it reads a space. i tried multiple ways until i gave up and went to more research about how to bypass scanf %s space reading. this took a long time before i found something
that could help which was called the $IFS (Internal Field Separator), apparently this was used to bypass security filters that blocks spaces, i knew this was exactly what i was looking for, so i looked for example use cases and found how to use it, so 
i injected this AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA/bin/cat%IFS/home/ctf-player/flag.txt

<img width="1304" height="91" alt="image" src="https://github.com/user-attachments/assets/01337c1b-1012-427a-aa51-11c14582b8c9" />

And it worked flawlessly!

What i learned
* I learned how to make uses of leaked addresses
* I learned the vulnerabilities of an unprotected scanf
* I learned how to find the file location using a command injection to get what file i want
  
