This is the second picoCTF challenge I completed, Transformation, an easy difficulty challenge.

<img width="1371" height="772" alt="image" src="https://github.com/user-attachments/assets/5ab214e3-fbc0-407d-9c2e-0a76b2bb27b1" />

As usual, I began by using wget to get the file, ls to check its name, and file to determine its type. Since it was identified as a Unicode text file, I then used cat to view its contents

<img width="1346" height="753" alt="image" src="https://github.com/user-attachments/assets/b11c9d3b-cdbf-4600-a408-b457651f61d3" />

Surprised by the sudden appearance of Chinese characters, I couldn't help but type a series of question marks and double checked the challenge description and the provided hint for more context.

<img width="248" height="263" alt="image" src="https://github.com/user-attachments/assets/79d79846-9eee-4c44-9c8c-c3ee90d3d5d3" />

Through the hint, I discovered that an online decoder would be needed to translate the characters.

<img width="1373" height="772" alt="image" src="https://github.com/user-attachments/assets/d657cfb9-58fa-45fc-9ed5-7a5d25275011" />

After some research, I came across CyberChef and learned that it is a reliable tool used by many cybersecurity enthusiasts. I also discovered the Magic recipe and used it as my operation to decode the characters.

<img width="1377" height="773" alt="image" src="https://github.com/user-attachments/assets/8644103e-10d8-4276-b79f-e8afebdfd9ab" />

I then copied and pasted the Chinese characters into the input and scrolled through the options until I found the correct translation, which in this case was the flag.

<img width="1373" height="775" alt="image" src="https://github.com/user-attachments/assets/0c386f51-0d38-4507-a01d-4acf268b6e16" />

Finally, after spotting the flag I needed, I copied and pasted it right away to submit it.

<img width="1382" height="773" alt="image" src="https://github.com/user-attachments/assets/7edd0807-080e-45e9-b910-4547594258fa" />
