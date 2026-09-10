# Hashing-Things-Out
# 🔐 Lab - Hashing Things Out

## Overview

This lab demonstrates how cryptographic hashing is used to verify file integrity and detect unauthorized modifications. Using OpenSSL along with the `sha256sum` and `sha512sum` utilities, SHA-256 and SHA-512 hashes were generated and compared to validate file authenticity.

---

## Objectives

- Generate SHA-256 and SHA-512 hashes using OpenSSL.
- Generate hashes using Linux hash utilities.
- Observe the avalanche effect of cryptographic hash functions.
- Verify file integrity by comparing hash values.

---

## Technologies Used

- Kali Linux
- OpenSSL
- SHA-256
- SHA-512
- `sha256sum`
- `sha512sum`

---

## Lab Tasks

### Part 1 – Hashing a Text File

- Generated SHA-256 and SHA-512 hashes for `letter_to_grandma.txt`.
- Modified the file by changing **"Hi Grandma"** to **"Hi Grandpa"**.
- Generated new hashes after the modification.
- Compared the original and modified hash values.

### Results

- A single text change produced a completely different hash value.
- This demonstrates the **avalanche effect**, where even a minor modification dramatically changes the resulting hash.
- Hashes generated with OpenSSL matched those produced by `sha256sum` and `sha512sum`, confirming the accuracy of both tools.

---

### Part 2 – Verifying File Integrity

- Compared the provided SHA-256 hash for `sample.img` with a newly generated hash.
- Both hash values matched exactly.

### Result

The matching hashes confirmed that the downloaded file had not been altered or corrupted.

---

## Commands Used

```bash
cd /home/analyst/lab.support.files

cat letter_to_grandma.txt

openssl sha256 letter_to_grandma.txt
openssl sha512 letter_to_grandma.txt

sha256sum letter_to_grandma.txt
sha512sum letter_to_grandma.txt

cat sample.img_SHA256.sig
sha256sum sample.img
```

---

## Key Concepts Learned

- Cryptographic hash functions generate a unique fingerprint for data.
- SHA-256 produces a 256-bit hash, while SHA-512 produces a 512-bit hash.
- The avalanche effect ensures that even a one-character change creates a completely different hash.
- Matching hashes verify file integrity and authenticity.
- Hashing is commonly used for software verification, digital forensics, password storage, and cybersecurity.

---

## Conclusion

This lab demonstrated the importance of cryptographic hashing for verifying data integrity. By generating and comparing SHA-256 and SHA-512 hashes, it was shown that even the smallest change to a file results in a completely different hash value, while identical hashes confirm that a file has remained unchanged. These techniques are essential in cybersecurity for validating downloads, detecting tampering, and ensuring data integrity.
