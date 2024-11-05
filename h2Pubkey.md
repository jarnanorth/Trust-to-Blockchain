# Read & summarize Scheiner 2015: Applied Cryptography & Rosenbaum 2019: Grokking Bitcoin

Scheiner (2015) tells that the roots of public-key cryptography trace back to 1976, when Whitfield Diffie and Martin Hellman shifted the cryptographic paradigm by describing public-key cryptography.

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



## a) Pubkey today
## b) Messaging
## c) Other tool
## d) Eve and Mallory
## f) Password management
## g) Refer to sources
