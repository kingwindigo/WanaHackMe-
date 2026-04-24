<img width="1919" height="945" alt="image" src="https://github.com/user-attachments/assets/9f694935-1522-4f1c-aa11-f662ffe35345" />

This is my first Level 2 challenge on crackmes.one, and it was made by pratdayzero.

<img width="1725" height="915" alt="Screenshot 2026-04-24 095230" src="https://github.com/user-attachments/assets/f3edc966-9048-4f3d-9ac4-44059bdea0d3" />

As usual, I started with the basic reconnaissance commands: `cd` to navigate to the directory, `ls` to list the contents, `file` to identify the file type, and `wine` to execute it.

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/ee30c317-af5c-4faf-9a63-54154d6d19a8" width="500"/></td>
    <td><img src="https://github.com/user-attachments/assets/b6a57ffd-d72c-4eb9-b6ee-a471b7393a29" width="500"/></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/cd1652ca-eef3-4ce5-acbb-66175745b0c4" width="500"/></td>
  </tr>
</table>

I went through all three possible choices to see what would happen. Typing 1 responded with "The payment system is down", 2 with "All representatives are busy. Try again later", and attempting -1 was immediately rejected with "Negative values are not allowed".

<img width="1718" height="914" alt="Screenshot 2026-04-24 095312" src="https://github.com/user-attachments/assets/a416c01b-98f4-400a-b743-1b44b9fca69a" />

Solving Method 1:

Since I couldn't access anything, I went ahead and used the strings command on the .exe file, which let me see what could be read as a string.

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/fd5f81b7-f4a0-4c65-9bad-01040aa45f6c" width="500"/></td>
    <td><img src="https://github.com/user-attachments/assets/867cfbec-f986-4ab3-bc14-c66926ee9e04" width="500"/></td>
  </tr>
</table>

Through this method, I was able to quickly identify the flag: dzctf(bob_is_free_1337).

Solving Method 2:

Next, I used Ghidra to read through the code of the file. I scrolled through it and checked the program trees one by one until I found the GUI-related section of the code, which was under .pdata. 

<img width="1919" height="1003" alt="image" src="https://github.com/user-attachments/assets/8b0301f8-ba02-49c3-8fd1-0f4499a094be" />

I got stuck here for a while, unsure of what to do next. I then figured out after some time that my input was being stored as a 32-bit integer, which was first checked to see if it was < 0. Then checked a second time, but this time, the integer input was typecasted to a char and compared against 0xFF. 

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/00ec1923-653c-46ad-8a6a-1be56757d658" width="500"/></td>
    <td><img src="https://github.com/user-attachments/assets/2729ef8f-32e6-4357-b697-51114b8862dd" width="500"/></td>
  </tr>
</table>

After learning about this, I searched on Google to find out what would happen if an integer was typecasted into a char. This is where I learned about Integer Truncation Vulnerability, where a 32-bit integer is truncated to 8 bits, keeping only the last byte. With this knowledge, I exploited the loophole and typed 255 into the exe, since the char value of 255 is 0xFF, which granted me access to the hidden admin terminal.

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/e8955caa-ba44-446a-a4b1-f787a5960893" width="500"/></td>
    <td><img src="https://github.com/user-attachments/assets/4937154f-9a79-41de-b002-d0b44bd6dfde" width="500"/></td>
  </tr>
</table>

Through this method, I was able to successfully clear Bob's debt and also retrieve the flag dzctf(bob_is_free_1337).
