---
aliases: key schedule
---

[[Advanced Encryption Standard|AES]] uses a *key schedule* to expand a short key into a number of separate round keys. The three AES variants have a different number of rounds. Each variant requires a separate 128-bit round key for each round plus one more. The key schedule produces the needed round keys from the initial key.

More: https://en.wikipedia.org/wiki/AES_key_schedule