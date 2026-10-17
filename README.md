# Cryptography Lab Experiments
# Sainath Pillai
This repository contains the implementation and output of cryptography laboratory experiments performed using Python and PyCryptodome.

## Experiments Included

- Experiment 12A — AES Security Analysis: ECB vs CBC
- Experiment 12B — Design and Analysis of a Secure Encryption Scheme

---

# Experiment 12A — AES Security Analysis: ECB vs CBC

## Aim

To study the security implications of AES block cipher modes by comparing ECB and CBC modes and analyzing repeated plaintext patterns in ciphertext.

## Objectives

- Implement AES-128 encryption and decryption.
- Implement AES in ECB mode.
- Implement AES in CBC mode.
- Generate a random Initialization Vector (IV).
- Apply PKCS#7 padding.
- Compare ciphertext blocks.
- Analyze repeated-pattern visibility.
- Verify successful encryption and decryption.

## Plaintext Used

The experiment uses a deliberately repeated plaintext pattern:

```text
1234567890ABCDEF1234567890ABCDEF1234567890ABCDEF1234567890ABCDEF
```

The plaintext length is 64 bytes.

AES-ECB Encryption

ECB encrypts every plaintext block independently.

ECB Result

- Total ECB Blocks: 5
- Unique ECB Blocks: 2

The ciphertext blocks were:

- Block 1: 96b296ec8b41e3d5a850df7441ed2c3c
- Block 2: 96b296ec8b41e3d5a850df7441ed2c3c
- Block 3: 96b296ec8b41e3d5a850df7441ed2c3c
- Block 4: 96b296ec8b41e3d5a850df7441ed2c3c
- Block 5: 34af336c9f031b3556738c63e61ea2f6

The first four ciphertext blocks are identical because the corresponding plaintext blocks are identical.

ECB Observation

Repeated ciphertext blocks are present. Identical plaintext blocks produced identical ciphertext blocks; this reveals patterns in the plaintext.

AES-CBC Encryption

CBC uses an Initialization Vector (IV) and chaining between ciphertext blocks.

CBC Result

- Total CBC Blocks: 5
- Unique CBC Blocks: 5

The ciphertext blocks were:

- Block 1: 10cca7769f41bd299d150ed5ac44bd63
- Block 2: 2f2287439c1a01ce6b78bf88fe1eb88b
- Block 3: 314e5337a6cb95cc0e1c552f18f4a140
- Block 4: 5f30ebe0612a228ad82bfed2e09c3ef9
- Block 5: 3c46983519d8be4ebb411f90b475ba39

All CBC ciphertext blocks are different.

CBC Observation

Ciphertext blocks are different. The repeated plaintext pattern is hidden.

Decryption Verification

- ECB: Decryption successful.
- CBC: Decryption successful.

Final Result

EXPERIMENT 12: SUCCESS

Conclusion

The experiment demonstrates the security difference between AES ECB and CBC modes.

- ECB encrypts each plaintext block independently. Therefore, identical plaintext blocks produce identical ciphertext blocks, which can reveal plaintext patterns.
- CBC uses an Initialization Vector and chaining between ciphertext blocks. Therefore, repeated plaintext blocks do not directly produce repeated ciphertext blocks.

Experiment 2B — Design and Analysis of a Secure Encryption Scheme

Aim

To implement classical cryptographic techniques, mathematical foundations used in cryptography, and AES-CBC encryption.

Techniques Implemented

- Caesar Cipher
- Euclidean Algorithm
- Modular Inverse
- Affine Cipher
- Vigenere Cipher
- Congruence Relation
- Fermat's Little Theorem
- Chinese Remainder Theorem
- AES-CBC

How to Run

- Install dependencies: `python -m pip install -r requirements.txt` (requirements.txt includes pycryptodome)
- Run Experiment 12A: `python experiment_12_aes_ecb_cbc/aes_ecb_cbc.py`
- Run Experiment 2B: `python experiment_2b_secure_encryption/experiment2_cryptography.py`
