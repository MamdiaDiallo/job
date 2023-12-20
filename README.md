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


// Key generation
BigInteger n = p.multiply(q);
BigInteger m = (p.subtract(BigInteger.ONE)).multiply(q.subtract(BigInteger.ONE));
BigInteger d = e.modInverse(m);

// Encryption
byte[] msgBytes = "thank mister for this course".getBytes(StandardCharsets.UTF_8);
BigInteger[] encrypted = encrypt(msgBytes, e, n);

// Decryption
BigInteger[] decrypted = decrypt(encrypted, d, n);
String decryptedMessage = new String(arrayToBytes(decrypted), StandardCharsets.UTF_8);

conclusion
In conclusion, the RSA encryption and decryption program aims to provide a secure mechanism for protecting sensitive information. The unique parameter values enhance the program's resilience against potential vulnerabilities
