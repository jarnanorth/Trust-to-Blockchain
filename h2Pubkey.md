# Read & summarize Scheiner 2015: Applied Cryptography & Rosenbaum 2019: Grokking Bitcoin

Scheiner (2015) https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec005  tells that the roots of public-key cryptography trace back to 1976, when Whitfield Diffie and Martin Hellman shifted the cryptographic paradigm by describing public-key cryptography.

     -Two keys: one public and one private
     -Computational difficulty: it is computationally hard to deduce the private key from the public key
     -Message encryption: anyone with the public key can encrypt a message
     -Message decryption: only the holder of the private key can decrypt the secret message
     
There are two main reasons why the public key is not used to encrypt messages directly but instead to encrypt keys:

      1. The public-key algorithm is slow, whereas symmetric algorithms are significantly faster.
      2. Public-key systems are vulnerable to chosen-plaintext attacks.
      
In a hybrid cryptosystem, the public key is used to secure and share a session key, which in turn is used with symmetric algorithms to encrypt message traffic. Ralph Merkle invented the first public-key cryptographic structure, and his method was based on "puzzles."

Signatures have long been used as proof that a person has authored a document or at least approved its content. Public-key algorithms can function as digital signatures.

Random number generators do not actually produce a truly random sequence, and generating a truly random sequence on a computer is impossible. A pseudo-random sequence is the closest approximation to randomness that a computer can produce.

In Grokking Bitcoin (2019) https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/OEBPS/Text/kindle_split_011.html#ch02lev2sec10 Rosenbaum tells common applications of digital signatures, which play a key role in both securing messages and authenticating identities within digital systems. He uses uses a simple metaphor of an office currency, "cookie tokens," to illustrate how digital signatures work in practice. He also tells the concept of key pair reuse and different methods for using a key pair in cryptographic contexts like Bitcoin. Key Pair Reuse refers to generating a single key pair—one private key and one corresponding public key—which can then be reused multiple times for signing. This approach simplifies the verification process, as individuals or systems can rely on the same public key repeatedly to verify various transactions or messages signed with the corresponding private key.



## a) Pubkey today
I used public key cryptography Yesterday when I was doing basic crocery shopping as then when you make payments with a card or through mobile apps, cryptography ensures you have the authority to charge the account and that the funds go to the correct recipient. It also ensures that the correct amount is transferred from the payer to the receiver. This authenticity and integrity, enabled by cryptography, is essential in mobile payments. A+ verkkopohjainen oppimisympäristö. Kurssimateriaali, Johdatus kryptografiaan https://plus.cs.aalto.fi/cs-ej4404/2022/02-Kryptografiankasitteet/01-kryptonintro/


## b) Messaging
I thought I was following the instructions exactly, but I still couldn't succeed with gpg. I was using the instructions provided by the teacher: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/ I also reread the previously given instructions https://terokarvinen.com/2021/install-debian-on-virtualbox/#boot-to-desktop---choose-to-live  and tried to figure out what might be the problem. I spent so much time on this that I simply ran out of time.

![image](https://github.com/user-attachments/assets/219e2925-f75f-4362-89ec-546be9e4fea5)

Update (after due time): I checked my own screenshot again and finally saw why its not working and the reason is so stupid: misspelling. 

![image](https://github.com/user-attachments/assets/0675dfe5-9f6a-4040-8a4d-e5937cafe53a)

1. Creating a keypair (public & secret key) using command $ gpg --gen-key


   ![2024-11-06 18_30_35-Window](https://github.com/user-attachments/assets/c0cff2d1-3bfb-4b90-afce-5c0e13000ca9)


2. Exporting my public key to Alice. Starting using command $ cd  and $ gpg --export --armor --output jarna.pub
   

   ![image](https://github.com/user-attachments/assets/1e1a003d-ebe6-437b-9358-03d204856186)


3. Creating folder to simulate Alice so that I have a another user for this test. Starting with commands $ cd  and $ mkdir alice/  and $ chmod og-rwx alice/ to create folder in home directory.


   ![image](https://github.com/user-attachments/assets/9f652a08-dde1-4636-94fe-bdaa19fef5ed)


4. Creating Alice`s own keypair using command $ gpg --homedir . --gen-key


![image](https://github.com/user-attachments/assets/bf5320f0-3da2-4411-96c3-7a67d6961eff)




5. Importing my key to Alice and verifying it´s really mine signing it using command $ gpg --homedir . --sign-key  .... 

  ![image](https://github.com/user-attachments/assets/75a49bf8-7b9c-4785-beaf-e46da6db7a7c)


6. Seeing the trust between me & Alice

   ![image](https://github.com/user-attachments/assets/fd7f8494-3570-43eb-9759-c5bc0d7a9489)

   ![image](https://github.com/user-attachments/assets/19ac0134-fd1e-48e4-83cb-6ef5f911452d)


7. Exporting Alice`s key, importing it to me and signing the trusted key.
8. Alice sends a message to me
9. Encrypting the message
10. Decrypting and verifying the message




   



## c) Other tool

 I didn’t have any more time for this, and I need to learn to ask for help right away instead of just continuing to try on my own. Later on I realised that my biggest problem is timing and I need to reorganize my weeks so that I dont even try to do these assingments in the evening when I am too exhausted after long days in really stormy situation at work and literally cant see anything anymore. Its better for me to wake up earlier and use early morning hours for these assingments and save evenings for recovering.

## d) Eve and Mallory

I understood that PGP protects against Eve by using encryption methods that prevent an outsider from reading the content of the message. In this case, the message sender uses the recipient’s public key to encrypt the message, and only the recipient can decrypt it with their private key. To protect against Mallory, PGP uses a digital signature. The sender can add a digital signature to the message using their private key, allowing the recipient to verify the message’s origin and ensure that its content has not been altered during transmission. If Mallory tries to modify the message, the signature will no longer match, and the recipient will notice this.

## f) Password management

A password manager helps store and use passwords across different online services. The user only needs to remember the master password for the manager, and all other passwords are securely stored behind it. A strong password generated by the manager protects against brute-force and guess-based attacks, and by using unique passwords for each site, attackers cannot access multiple accounts with a single compromised password. Additionally, the manager helps prevent phishing attempts by filling in passwords only on legitimate sites. Traficom: https://www.kyberturvallisuuskeskus.fi/fi/ajankohtaista/neuvoja-salasanan-hallintasovelluksen-kayttoonottoon


