---
aliases: OTP
---

In cryptography, the one-time pad (OTP) is an encryption technique that cannot be cracked, but requires the use of a *single-use pre-shared key* that is *larger than or equal to the size of the message being sent*. In this technique, a plaintext is paired with a random secret key (also referred to as a one-time pad). Then, each bit or character of the plaintext is encrypted by combining it with the corresponding bit or character from the pad using modular addition.

The resulting ciphertext will be impossible to decrypt or break if the following four conditions are met:

1. The *key* must be at least as long as the [[plaintext]].
2. The key must be random (uniformly distributed in the set of all possible keys and independent of the plaintext), entirely sampled from a non-algorithmic, chaotic source such as a hardware random number generator; patternless, according to Gregory Chaitin definition. It is not sufficient for OTP keys to pass statistical randomness tests as such tests cannot measure entropy, and the number of bits of entropy must be at least equal to the number of bits in the plaintext. For example, using cryptographic hashes or mathematical functions (such as logarithm or square root) to generate keys from fewer bits of entropy would break the uniform distribution requirement, and therefore would not provide perfect secrecy.
3. The key must never be reused in whole or in part.
4. The key must be kept completely secret by the communicating parties.

It has also been *mathematically proven that any cipher with the property of perfect secrecy must use keys with effectively the same requirements as OTP keys*. Digital versions of one-time pad ciphers have been used by nations for critical diplomatic and military communication, but the problems of *secure key distribution make them impractical* for most applications. 