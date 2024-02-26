---
aliases: Brute force attack
---
In [[cryptography]], a brute-force attack consists of an attacker submitting many passwords or passphrases with the hope of eventually guessing correctly. The attacker systematically checks all possible passwords and passphrases until the correct one is found. Alternatively, the attacker can attempt to guess the key which is typically created from the password using a key derivation function. This is known as an **exhaustive key search**.

### Countermeasures
In case of an *offline attack* where the attacker has gained access to the encrypted material, one can try key combinations without the risk of discovery or interference. 

In case of online attacks, database and directory administrators can deploy countermeasures such as *limiting the number of attempts* that a password can be tried, introducing *time delays between successive attempts*, *increasing the answer's complexity* (e.g., requiring a *CAPTCHA* answer or employing multi-factor authentication), *and/or locking accounts out after unsuccessful login attempts*. Website administrators may *prevent a particular IP address from trying more than a predetermined number of password attempt*s against any account on the site.

### Reverse brute-force attack
In a reverse brute-force attack, a single (usually common) password is tested against multiple usernames or encrypted files. The process may be repeated for a select few passwords. In such a strategy, the attacker is not targeting a specific user. 

-> Online-Attack countermeasures can be dodged