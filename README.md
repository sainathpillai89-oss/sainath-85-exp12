# Cryptography Lab Experiments
# Parth Patil TE AIDS 124A8078
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

The plaintext length is 64 bytes.

AES-ECB Encryption

ECB encrypts every plaintext block independently.
ECB Result
Total ECB Blocks: 5
Unique ECB Blocks: 2

The ciphertext blocks were:

Block 1: 96b296ec8b41e3d5a850df7441ed2c3c
Block 2: 96b296ec8b41e3d5a850df7441ed2c3c
Block 3: 96b296ec8b41e3d5a850df7441ed2c3c
Block 4: 96b296ec8b41e3d5a850df7441ed2c3c
Block 5: 34af336c9f031b3556738c63e61ea2f6

The first four ciphertext blocks are identical because the corresponding plaintext blocks are identical.

ECB Observation

Repeated ciphertext blocks are present.

Identical plaintext blocks produced identical ciphertext blocks.

This reveals patterns in the plaintext.

AES-CBC Encryption

CBC uses an Initialization Vector (IV) and chaining between ciphertext blocks.

CBC Result
Total CBC Blocks: 5
Unique CBC Blocks: 5

The ciphertext blocks were:

Block 1: 10cca7769f41bd299d150ed5ac44bd63
Block 2: 2f2287439c1a01ce6b78bf88fe1eb88b
Block 3: 314e5337a6cb95cc0e1c552f18f4a140
Block 4: 5f30ebe0612a228ad82bfed2e09c3ef9
Block 5: 3c46983519d8be4ebb411f90b475ba39

All CBC ciphertext blocks are different.

CBC Observation

Ciphertext blocks are different.

The repeated plaintext pattern is hidden.

Decryption Verification

ECB: Decryption successful.
CBC: Decryption successful.
Final Result
EXPERIMENT 12: SUCCESS
Conclusion

The experiment demonstrates the security difference between AES ECB and CBC modes.

ECB encrypts each plaintext block independently. Therefore, identical plaintext blocks produce identical ciphertext blocks, which can reveal plaintext patterns.

CBC uses an Initialization Vector and chaining between ciphertext blocks. Therefore, repeated plaintext blocks do not directly produce repeated ciphertext blocks.

Hence, the experiment demonstrates that the choice of block cipher mode is an important part of cryptographic system design.

Experiment 2B — Design and Analysis of a Secure Encryption Scheme
Aim

To implement classical cryptographic techniques, mathematical foundations used in cryptography, and AES-CBC encryption.

Techniques Implemented
Caesar Cipher
Euclidean Algorithm
Modular Inverse
Affine Cipher
Vigenere Cipher
Congruence Relation
Fermat's Little Theorem
Chinese Remainder Theorem
AES-CBC
1. Caesar Cipher
Input
Plaintext : HELLO WORLD
Key       : 3
Encryption Result
Ciphertext: KHOOR ZRUOG
Decryption Result
Decrypted : HELLO WORLD

The decrypted text matches the original plaintext.

2. Euclidean Algorithm

The Euclidean algorithm was used to calculate the greatest common divisor.

GCD(35, 26) = 1

Therefore:

gcd(35, 26) = 1
3. Modular Inverse

The modular inverse of 5 modulo 26 was calculated.

a = 5
modulus = 26
GCD(5, 26) = 1
Multiplicative inverse = 21

Verification:

(5 × 21) mod 26 = 1

Therefore, 21 is the multiplicative inverse of 5 modulo 26.

4. Affine Cipher

The Affine Cipher was implemented using:

a = 5
b = 8

The required condition was verified:

gcd(5, 26) = 1

The multiplicative inverse of 5 modulo 26 is:

21
Encryption and Decryption
Plaintext : HELLO WORLD
Keys      : 5 8
Ciphertext: RCLLA OAPLX
Decrypted : HELLO WORLD

The decrypted text matches the original plaintext.

5. Vigenere Cipher

The Vigenere Cipher was implemented using the key:

KEY
Encryption and Decryption
Plaintext : HELLO WORLD
Key       : KEY
Ciphertext: RIJVS UYVJN
Decrypted : HELLO WORLD

The decrypted text matches the original plaintext.

6. Congruence Relation

The following congruence was verified:

29 mod 26 = 3

Therefore:

29 ≡ 3 (mod 26)
7. Fermat's Little Theorem

Fermat's Little Theorem was verified using:

a = 3
p = 7

The calculation was:

3^(7-1) mod 7 = 1

Result:

Fermat's Little Theorem verified.
8. Chinese Remainder Theorem

The following system of congruences was solved:

x ≡ 2 (mod 3)
x ≡ 3 (mod 5)
x ≡ 2 (mod 7)

The calculated solution was:

CRT Solution: x = 23
Verification
23 mod 3 = 2
23 mod 5 = 3
23 mod 7 = 2

Therefore, the CRT solution is correct.

9. AES-CBC

AES-CBC encryption and decryption were implemented using a 128-bit AES key.

AES Key
0123456789ABCDEF
Plaintext
HELLO WORLD
Result
Plaintext : HELLO WORLD
AES Key   : 0123456789ABCDEF
IV        : 133fe81a63d288c5637434e0fc539bae
Ciphertext: b7267a479d54d187cb8186911ce044da
Decrypted : HELLO WORLD

The plaintext was successfully recovered after decryption.

Final Verification

All implemented cryptographic and mathematical operations passed successfully.

Caesar Cipher: PASS
Affine Cipher: PASS
Vigenere Cipher: PASS
AES-CBC: PASS
Euclidean Algorithm: PASS
Modular Inverse: PASS
Congruence: PASS
Fermat's Little Theorem: PASS
CRT: PASS

Final verification message:

All cryptographic and mathematical tests completed successfully.

Technologies Used
Python 3.x
PyCryptodome
Visual Studio Code
Git
GitHub
Installation

Make sure Python 3.x is installed.

Install the required dependency using:

python -m pip install -r requirements.txt

Alternatively:

python -m pip install pycryptodome
How to Run
Experiment 12A

From the project root:

python experiment_12_aes_ecb_cbc/aes_ecb_cbc.py
Experiment 2B

From the project root:

python experiment_2b_secure_encryption/experiment2_cryptography.py
Project Structure
cryptography-lab-experiments/
│
├── experiment_12_aes_ecb_cbc/
│   ├── aes_ecb_cbc.py
│   └── output.txt
│
├── experiment_2b_secure_encryption/
│   ├── experiment2_cryptography.py
│   └── output.txt
│
├── README.md
├── requirements.txt
└── .gitignore
Output Files

Each experiment contains an output.txt file containing the successful terminal execution output.

These files provide evidence that the implemented programs were executed and verified successfully.

Conclusion

These experiments demonstrate both classical and modern cryptographic concepts.

Experiment 12A demonstrates the security implications of AES block cipher modes by comparing ECB and CBC. The experiment shows that ECB can reveal repeated plaintext patterns, while CBC uses an I[...]