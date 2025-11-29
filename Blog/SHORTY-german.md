![Image](/img/BannerServer.jpg)

(Photo: pixabay.com)

# SHORTY

**SHORTY is a complete public key algorithm, it is suitable for both encryption and digital signatures. The ciphertext is hardly larger than the plaintext and the modular multiplication used is much less computationally intensive than modular exponentiation as used in other algorithms.**

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕓 April 12, 2000.

## Description

To prepare, divide the message into sub-blocks of fixed size nbits and choose the four values a, b, c and m so that holds:

- c and m must not have a common divisor (relatively prime)
- m must be greater than 2 ^ nBits
- a * b * c mod m must be 1

The values a and b form the private key, c and m the public key. The larger these values are chosen, the stronger the security. Then calculate the number sequence K as follows:

For i = 0, 1, 2, ... to nBits - 1 
K[i] = (2 ^ i) * a mod m 

For encryption set the ciphertext ("cipher") to 0.

For i = 0, 1, 2... to nBits - 1 
If in the message the bit 2 ^ i is set, then: cipher = cipher + K[i]

cipher = cipher * b mod m 

For decryption calculate:

Plaintext = cipher * c mod m

## Example

We divide the message into sub-blocks of 6 bits and choose a = 7, b = 2, c = 9 and m = 125. 

The number sequence K is calculated from this as follows:

```
1 * 7 mod 1301 = 7 
2 * 7 mod 1301 = 14 
4 * 7 mod 1301 = 28 
8 * 7 mod 1301 = 56 
16 * 7 mod 1301 = 112 
32 * 7 mod 1301 = 99
```

Thus, the sequence of numbers K consists of: { 7, 14, 28, 56, 112, 99 }.

If the message is 010110, the encryption proceeds as follows:

010110 equals 14 + 28 + 112 = 154. 
The ciphertext is then: 154 * 2 mod 125 = 58

The decryption is done quite simply via:

58 * 9 mod 125 = 22, which corresponds to 10110

The recovered plaintext is then: 010110

## Derivation

SHORTY is derived from the knapsack algorithm of Merkle-Hellman [1], which is defined as follows:

1. choose a knapsack sequence with the superincreasing property. 
2. choose a multiplier n and a modulus m with the following properties:

m > sum of all numbers in the knapsack sequence, n and m have no common divisors. 

3. calculate the normal knapsack sequence from: superKnapsack[i] * n mod m
4. add for each set bit in the message the corresponding element in the normal knapsack sequence to the ciphertext 

knapsack sequence to the ciphertext.

5. determine nn so that: n * nn = 1 (mod m) 
6. calculate: ciphertext * nn mod m
7. gain the plaintext over the knapsack sequence with the superincreasing property.

For SHORTY, we take the power-of-two knapsack sequence (1, 2, 4, 8, 16, 32, ...) in step (1), which satisfies the superincreasing property, so step (7) can then be omitted.

Step (6) is split into two modular multiplications, since holds: 
ab * x mod m equals:  (a * x mod m) * b mod m

nn is split into the 2 multipliers b and c, n corresponds to a in SHORTY.

## Example key

For 80 bits:

```
private a = 1b538a (24 bit)
private b = abd93 (20 bit)

public c = 66bf4b8ecceafb123c7961ba37c655f8a61eae2b7cb1ceb6cf402ad7eb788a6d6e14b311b6ac3bd9f700ae32a1e41ff8ccd48792ea2448f04cfd7346ed733e0c1b8a5972d5af0acf0dd34c1b741adae718599d69e550431a14235b5f403f917324a5ec40fe372f9d7e3d1ce27a8ba9a00cd97c71712e84344d2aa7d1d2b824a5c652c36567 (1064 bit)
public mod = dcffdb7769a382d02f69 (80 bit)
```

For 96 bits:

```
private a = 1a4824 (24 bit)
private b = 219a9c (24 bit)

public c = 3441ae7ce03d48bc2139b0d95838d41e9e86ace4085396d5c254262385aae2fcda47941ec8668ad53b81005a9e7e380b23e3ff4352d43d5507aeace418b27654719506536151e17c347065c5d35e62ee4dc31b565aaba000c3a7c40579dfea1d54ad3ff994ff1d3fdd0e34270d26c4e311f98307fe138580164ce0c9c65a7a13b7eb192442889d (1080 bit)
public mod = c3c694bcb70d5dcfb3d5f239 (96 bit)
```

For 100 bit:

```
private a = 1fdb48 (24 bit)
private b = 2457c6 (24 bit)

public c = 181e0b1397d13baa66e861d0feae1734b418db2e1aa5efc74a3c1a2fe920dacc26adca8b1dd579bb2bc51ef204b778e8dd04d0f3f02ed8edb254582f8a99ecb26aab5a58c433a3332ca82f5c44f64a5265fb611d1fc0a3b200fdc21f42836ece72fb20060d03b30f9416cbc82f8fe9f4ea0fc15de1e8084d518a6b (984 bit)
public mod = 8ee82a56a73549610d9dbf8db (100 bit)
```

## Patents and licenses

The Merkle-Hellman algorithm is patented in many countries, but patent protection has expired in most countries [2]:

Germany: number 2843583 granted May 10, 1979. 
Germany: number 2843583 granted on June 3, 1982 
Germany: number 2857905 granted on July 15, 1982 
Canada: number 1128159 issued on July 20, 1982 
USA: expired on 19 August 1997

## Sources

1. Bruce Schneier "Applied Cryptography", Addison-Wesley Publishing Company, ISBN 3-89319-854-7, page 526 
2. Bruce Schneier "Applied Cryptography", Addison-Wesley P