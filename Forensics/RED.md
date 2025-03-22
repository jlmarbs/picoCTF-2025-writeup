## DESCRIPTION
RED, RED, RED, RED
Download the image: `red.png`

## MY PROCESS
After downloading the provided flag, I opened the png file and only greeted with a red square.
![image](https://github.com/user-attachments/assets/ddc7b95d-7fac-453d-bbd2-bec5dd65f838)

Zooming in and out did not reveal the flag.

The next thing I did is to run `zsteg` command on the png file and this was the output:
![image](https://github.com/user-attachments/assets/34a8ebe1-f849-4247-a2ce-4a3fcd9f5e14)

The thing that I was interested was on the `b1,rgba,lsb,xy` part since it revealed repeating base64 string which is `cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`.

What I did after is I entered `base64 -d <<< cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==` on the terminal and it revealed the flag for the challenge.
![image](https://github.com/user-attachments/assets/9fe36ed1-255b-44cb-8077-a237af8c1650)

FLAG: `picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}`
