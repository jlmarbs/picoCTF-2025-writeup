## DESCRIPTION
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.
To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!
Find the PCAP file here `Network Traffic PCAP file` and try to get the flag.

## MY PROCESS
After downloading the `.pcap` file, I immediately checked for traces of flag since there was a hint saying that `attacks were done in timely manner`.

And that is where I noticed the `Len=12`s and 1 `Len=4`, and that is where I started to find the flag.

What I have noticed is that my packet bytes is not showing the full hex data shown in the picture below:
![image](https://raw.githubusercontent.com/jlmarbs/picoCTF-2025-writeup/refs/heads/main/Forensics/image.png)

With that in mind, that made me filter my packets that only has the length of 12 and 4.
![image](https://raw.githubusercontent.com/jlmarbs/picoCTF-2025-writeup/refs/heads/main/Forensics/image-1.png)

And with that, I started converting the hex in base64 as it is partially displayed as base64 on the packet bytes.

And this is all I got in the TCP lengths of 12 and 4:
- `PACKET 8 LEN=4: fQ== -> }`
- `PACKET 9 LEN=4: cGljb0NURg== -> picoCTF`
- `PACKET 13 LEN=12: ZTEwZTgzOQ== -> e10e839 (this might be different on your end)`
- `PACKET 15 LEN=12: XzM0c3lfdA== -> _34sy_t`
- `PACKET 17 LEN=12: bnRfdGg0dA== -> nt_th4t`
- `PACKET 20 LEN=12: YmhfNHJfOA== -> bh_4r_8`
- `PACKET 21 LEN=12: ezF0X3c0cw== -> {1t_w4s`

And since they are all jumbled around, I pieced them together and got the final flag.

FLAG: `picoCTF{1t_w4snt_th4t_34sy_tbh_4r_8e10e839}`
