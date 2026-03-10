<img width="964" height="576" alt="image" src="https://github.com/user-attachments/assets/2624e325-c337-4930-ba93-19e0e1f3e274" />
This pico CTF was not as good as i thought it was, since it said  something about formats, I immediately went to check the source code and saw the requirements for how to pass, honestly it was more of an introduction towards breaking the system using string formats
such as %, the menu itself had % which was a vulnerability in it of itself, it did make me realize just how vulnerable a system is if not properly formatted. one idea that came to mind as a i finished it was printf statements, since im mostly using C this could prove to be
a vulnerability in it of itself if i dont format it correctly. such as overflowing to break my system, or even getting vulnerable data using the formats

Overall it was a fun introduction challenge


<img width="898" height="882" alt="image" src="https://github.com/user-attachments/assets/a6ca399c-5af4-4a1b-bae6-9531a6fdc2c1" />
At first i entered the menu, and realized grilled cheese menu was formated as Gr%114d_Cheese, the %114d would create a large enough file to overflow the dataset. then, after the next challenged i first tried to understand, i even tried to input my own string such as
Pe%1046dto_Portobello, by adding a 1046d i wanted to overflow it to the max so it breaks, sadly the system was case sensitive so i couldnt really add into it hoping to overflow it, then i noticed a particular menu such as
Cla%sic_Che%s%steak, i noticed the % had an s, which meant that by accident, it WILL print out a string data file %s, then i just entered that and it overflowed just as expected, honestly i was hoping for a more brain teaser challenge but since its a beginner level i cant 
really expect much, it was fun thought
