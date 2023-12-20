---
title: "RSA Encryption and Decryption Report"
author: "Mamoudou Diallo"
output: pdf_document
---

# Group Report

**Group Members:**
1. Mamoudou Diallo

**Campus:**
ESTIAM

---

## Activity 1: RSA Encryption and Decryption Program in Java

### Introduction
The first activity, conducted by Mamoudou Diallo, involves the development of a Java program for RSA encryption and decryption. The program aims to demonstrate the secure transmission of information using RSA cryptography, specifically on the host machine.

### Implementation Details

#### RSA Parameters
To enhance the security of the system, unique values for P, Q, and E have been chosen. The parameters are as follows:

- **P (Prime Number):** [Replace with your chosen value]
- **Q (Prime Number):** [Replace with your chosen value]
- **E (Public Exponent):** [Replace with your chosen value]

### Program Description

#### Overview
The RSA program is designed to encrypt and decrypt messages securely. The algorithm involves key generation, encryption, and decryption processes to ensure data integrity.

#### Key Generation
The program generates public and private keys using the chosen prime numbers P and Q, along with the public exponent E.


#### Key generation
BigInteger n = p.multiply(q);
BigInteger m = (p.subtract(BigInteger.ONE)).multiply(q.subtract(BigInteger.ONE));
BigInteger d = e.modInverse(m);

BigInteger n = p.multiply(q);

p and q are prime numbers chosen for the RSA algorithm.
n is the product of p and q and represents the modulus for both the public and private keys.
The modulus (n) is a crucial component in RSA, as it is used in both the encryption and decryption processes.
BigInteger m = (p.subtract(BigInteger.ONE)).multiply(q.subtract(BigInteger.ONE));

The variable m represents Euler's totient function (ϕ(N)) for the chosen primes p and q.
Euler's totient function is calculated as the product of (p-1) and (q-1). It denotes the count of positive integers less than n that are coprime to n (do not share any common factors with n except 1).
BigInteger d = e.modInverse(m);

e is the public exponent chosen for the RSA algorithm.
d is the private exponent, and it is calculated as the modular multiplicative inverse of e modulo m. In other words, it is the value such that (d * e) % m = 1.
The private exponent d is a crucial component for the decryption process and is kept secret.

#### Encryption
byte[] msgBytes = "thank mister for this course".getBytes(StandardCharsets.UTF_8);
BigInteger[] encrypted = encrypt(msgBytes, e, n);

byte[] msgBytes = "thank mister for this course".getBytes(StandardCharsets.UTF_8);

The string "thank mister for this course" is converted into an array of bytes (msgBytes) using UTF-8 encoding.
This step is necessary because cryptographic algorithms often operate on raw byte data.
BigInteger[] encrypted = encrypt(msgBytes, e, n);

The encrypt function is called with three parameters:
msgBytes: The byte array representing the message to be encrypted.
e: The public exponent chosen for the RSA algorithm.
n: The modulus used for both the public and private keys.
#### Decryption
BigInteger[] decrypted = decrypt(encrypted, d, n);
String decryptedMessage = new String(arrayToBytes(decrypted), StandardCharsets.UTF_8);

BigInteger[] decrypted = new BigInteger[encrypted.length];

An array of BigInteger objects (decrypted) is created to store the decrypted values for each encrypted BigInteger in the array.
for (int i = 0; i < encrypted.length; i++) {

The program iterates over each element in the encrypted array.
decrypted[i] = encrypted[i].modPow(d, n);

For each encrypted value, the modPow method is used to decrypt it using the private exponent (d) and modulus (n).
The decrypted value is stored in the corresponding position in the decrypted array.
return decrypted;

The array of decrypted BigInteger values is returned.
String decryptedMessage = new String(arrayToBytes(decrypted), StandardCharsets.UTF_8);

The decrypted BigInteger values are converted back into a byte array using the arrayToBytes function.
The byte array is then converted into a string (decryptedMessage) using UTF-8 encoding.
#### Conclusion
In conclusion, the RSA encryption and decryption program aims to provide a secure mechanism for protecting sensitive information. The unique parameter values enhance the program's resilience against potential vulnerabilities
