---
title: "RSA encryption"
output: pdf_document
---

# Estiam Lyon 

**Group Members:**
1. Mamoudou Diallo

**Campus:**
[Name of the Campus]

---

## Activity 1: RSA Encryption Program in Java

### Introduction
The first activity, undertaken by Mamoudou Diallo, involves the creation of a Java program to execute RSA encryption. This program is designed to run exclusively on the host machine, simulating enhanced system protection, especially when dealing with customer data used in electronic transactions, such as those in an e-commerce environment.

### Implementation Details

#### Parameters Selection
To enhance the security of the system, Mamoudou Diallo deliberately chose values different from those discussed in the classroom for the parameters P, Q, and E (K). This strategic decision contributes to the uniqueness and robustness of the encryption process.

- **P (Prime Number):** [Replace with the selected prime number]
- **Q (Prime Number):** [Replace with the selected prime number]
- **E (Public Exponent):** [Replace with the selected public exponent]

### Program Description

#### Overview
The RSA encryption program is implemented in Java to perform encryption exclusively on the host machine. This approach aims to bolster security, particularly in scenarios involving sensitive customer data for electronic transactions.

#### Key Generation
The program includes a key generation process, where the prime numbers P and Q are used to calculate both public and private keys. The chosen public exponent E plays a crucial role in this process.

```{java}
// Parameters chosen by Mamoudou Diallo
BigInteger p = new BigInteger("your_selected_prime_P");
BigInteger q = new BigInteger("your_selected_prime_Q");
BigInteger e = new BigInteger("your_selected_public_exponent_E");

// Key generation
BigInteger n = p.multiply(q);
BigInteger m = (p.subtract(BigInteger.ONE)).multiply(q.subtract(BigInteger.ONE));
BigInteger d = e.modInverse(m);
