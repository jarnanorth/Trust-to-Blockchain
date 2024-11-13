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








Karvinen 2022: Cracking Passwords with Hashcat

## a) Billion dollar busywork. 
Command 'echo -n "hello"|sha256sum' prints a hash. Try adding something to the string, e.g. 'echo -n 'hello asdf'|sha256sum'. What do you have to add to get a hash that starts with a zero? 

# b) Compare hash.
Create a small text file. Take it's hash (e.g. 'sha256sum tero.txt'). Change one letter. Take the hash again. Compare hashes. What do you notice?

# c) Hashcat. 
Install hashcat and test that it works.

# d) Dictionary attack. 
Crack this hash: 21232f297a57a5a743894a0e4a801fc3

# e) How can you make a password that's protected against a dictionary attack?
