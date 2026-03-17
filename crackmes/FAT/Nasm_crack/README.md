<img width="1681" height="948" alt="image" src="https://github.com/user-attachments/assets/1a1c73c3-847f-41cb-9f4a-793c522b07b2" />

This was my first challenge on crackmes.one and also my first time using Ghidra. It was surprisingly easy, though that might be because I took the time to learn Ghidra before jumping into the challenge, and it is, after all, a Level 1.

<img width="1375" height="772" alt="image" src="https://github.com/user-attachments/assets/d2017e63-b657-482b-ae69-cc01cd80be7c" />

In this image, I was looking through the assembly code to find the main function so I could read it more easily in C.

<img width="1376" height="775" alt="image" src="https://github.com/user-attachments/assets/7b0d4829-65c3-4ba9-98f8-b993f4e7da90" />

After searching for a bit, I finally found it and spotted the variable where the password was supposedly stored.

<img width="1379" height="775" alt="image" src="https://github.com/user-attachments/assets/68b2dc21-d89a-4646-b80f-5cf5ce11c13a" />

From there, I jumped to where the password was located in the assembly code and found that the password data was undefined, showing up as '??'.

<img width="1375" height="774" alt="image" src="https://github.com/user-attachments/assets/11a660dc-517a-47a1-ab75-98b078c32bdf" />

To get the password, I highlighted the series of lines holding the password data, right-clicked, and changed the data type to char.

<img width="1380" height="776" alt="image" src="https://github.com/user-attachments/assets/a097e2d4-4724-42c9-ba0b-20697c983a1b" />

After doing so, I finally got the password.

<img width="1379" height="772" alt="image" src="https://github.com/user-attachments/assets/6252d5af-00e1-4d26-9b7f-63170fc89e5f" />

Finally, I entered the password into the application to verify that it was correct, and as shown in the image, it worked.
