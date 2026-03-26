<img width="984" height="435" alt="image" src="https://github.com/user-attachments/assets/c215feb7-ae18-49af-92cc-9c9babebc636" />

This is the second crackme level 1 that I tried, Acrack by MicrosoftStorage

<img width="1454" height="769" alt="image" src="https://github.com/user-attachments/assets/ccf551fb-ba58-405d-9c77-aab1e2a47360" />

As usual, I tried running the application in the terminal first, but it returned a 'Permission Denied' error. I tried a few other things thinking it was just a file error, until I realized I hadn't done a file check on it. It turned out that was the problem, as the executable was actually built for Windows.

<img width="1467" height="768" alt="image" src="https://github.com/user-attachments/assets/de1d1bcb-ef48-49e9-a3b1-1a3a565ef071" />

After searching a bit about Wine, I learned that it is a compatibility layer that allows Windows executables to be run on Ubuntu. So I went ahead and installed it.

<img width="1460" height="776" alt="image" src="https://github.com/user-attachments/assets/3a980385-81cc-4fb4-8884-4e6824eb1b66" />

Though I ran into a small problem, as even after installing Wine it still indicated that wine32 was missing, requiring me to run 3 more commands to resolve it. 

<img width="1476" height="776" alt="image" src="https://github.com/user-attachments/assets/be6a166f-3faf-418c-a483-e9ab2a5acc06" />

Even after doing all of that, I ran into another problem where Wine couldn't load kernel32.dll. I had to search for the cause and the solution, but after applying the fix I finally got it working, so all was good...

<img width="1461" height="771" alt="image" src="https://github.com/user-attachments/assets/81177dd3-96ee-4eea-becb-4e213cb0f143" />

Well, it turns out not all was good. I ran into yet another problem, but this time it was an error with the file itself. After everything I had done, I still got an error. 

<img width="1473" height="771" alt="image" src="https://github.com/user-attachments/assets/fdd35363-b62d-47d4-8a1a-921dde0bfa92" />

At that point, I just went ahead and opened the file in Ghidra to examine its code directly. From there, I started looking at the main function.

<img width="1476" height="775" alt="image" src="https://github.com/user-attachments/assets/03f8e4af-da43-48f8-84ea-aadd5babe4bf" />

If you haven't realized it just yet, the nickname and password I was looking for were actually right in front of me the whole time I had the file open in Ghidra. Yet I hadn't noticed it one bit.

<img width="1471" height="774" alt="image" src="https://github.com/user-attachments/assets/d5423e1b-d26b-4a51-846e-f0783a6c3100" />

After finally noticing it, I didn't know whether to be happy that I found it or to be frustrated that my brain was so fried from installing Wine that I hadn't noticed it at all.

<img width="1474" height="773" alt="image" src="https://github.com/user-attachments/assets/2a60a6a4-8513-4128-bcc3-ad564e995079" />

Regardless, what matters is that I was able to obtain what was needed to complete the challenge successfully.
