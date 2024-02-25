---

---

A **rainbow table** is a *precomputed table for caching the outputs of a cryptographic hash function*, usually for cracking password hashes. Passwords are typically stored not in plain text form, but as hash values. If such a database of hashed passwords falls into the hands of an attacker, they can use a precomputed rainbow table to recover the plaintext passwords. A common defense against this attack is to compute the hashes using a key derivation function that adds a *"salt"* to each password before hashing it, with different passwords receiving different salts, which are stored in plain text along with the hash.

Rainbow tables are a practical example of a *space-time tradeoff*: they use less computer processing time and more storage than a brute-force attack which calculates a hash on every attempt, but more processing time and less storage than a simple table that stores the hash of every possible password. 