## Read and summarize (with some bullet points)
Schneier 2015: Applied Cryptography: Chapter 2 https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003

### One-Way Function:
•	A central concept in public-key cryptography

•	Relatively easy to compute, but reversing it is significantly harder

•	Cannot be used for encryption as-is, because no one would be able to decrypt it

•	A trapdoor one-way function can also be computed in the reverse direction using secret trapdoor information


### One-Way Hash Function:
•	Known by many names: compression function, contraction function, message digest, fingerprint, cryptographic checksum, message integrity check (MIC), and manipulation detection code (MDC)

•	Takes a variable-length input string (called a pre-image) and converts it into a fixed-length (usually shorter) output string (called a hash value)

•	A one-way hash function works in only one direction

•	It is also collision-free, meaning it is hard to create two pre-images that have the same hash value

•	It is public, but its security is based on its one-way nature

•	There is no discernible connection between input and output

•	A single bit change in the pre-image changes, on average, half of the bits in the hash value

•	A message authentication code (MAC) is a one-way hash function with an added secret key















## a) Billion dollar busywork. 
Command 'echo -n "hello"|sha256sum' prints a hash. Try adding something to the string, e.g. 'echo -n 'hello asdf'|sha256sum'. What do you have to add to get a hash that starts with a zero? 

## b) Compare hash.
Create a small text file. Take it's hash (e.g. 'sha256sum tero.txt'). Change one letter. Take the hash again. Compare hashes. What do you notice?

## c) Hashcat. 
Install hashcat and test that it works.

Karvinen 2022: Cracking Passwords with Hashcat https://terokarvinen.com/2022/cracking-passwords-with-hashcat/ :

Tried this one but it didnt work:

![image](https://github.com/user-attachments/assets/2a0eec97-5a0e-44d4-9aee-3f0fdefda9a6)

Asked help from ChatGTP askin what would be good way to get rockyou and ChatGTP recommend this: 

![image](https://github.com/user-attachments/assets/7240c831-7349-4e48-ac21-89566890cd3b)

and then I managed to continue same way than in teachers instructions:

![image](https://github.com/user-attachments/assets/1a11d7d2-2cf2-4345-8733-767d93c62b5a)

But then I crash straight in to problem which is going stole too much of my time: 

![image](https://github.com/user-attachments/assets/10557b6e-969e-4837-901a-47426b0d0f71)



## d) Dictionary attack. 
Crack this hash: 21232f297a57a5a743894a0e4a801fc3

## e) How can you make a password that's protected against a dictionary attack?
