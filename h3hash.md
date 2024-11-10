# Read and summarize (with some bullet points)
Schneier 2015: Applied Cryptography: Chapter 2 - Protocol Building Blocks: subchapters "2.3 One-way Fuctions" and "2.4 One-Way Hash Functions".
Karvinen 2022: Cracking Passwords with Hashcat

# a) Billion dollar busywork. 
Command 'echo -n "hello"|sha256sum' prints a hash. Try adding something to the string, e.g. 'echo -n 'hello asdf'|sha256sum'. What do you have to add to get a hash that starts with a zero? 

# b) Compare hash.
Create a small text file. Take it's hash (e.g. 'sha256sum tero.txt'). Change one letter. Take the hash again. Compare hashes. What do you notice?

# c) Hashcat. 
Install hashcat and test that it works.

# d) Dictionary attack. 
Crack this hash: 21232f297a57a5a743894a0e4a801fc3

# e) How can you make a password that's protected against a dictionary attack?
