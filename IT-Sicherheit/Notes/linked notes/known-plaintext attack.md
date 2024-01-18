---
aliases: KPA
---
 The *known-plaintext attack (KPA)* is an attack model for [[Kryptoanalyse|cryptanalysis]] where the attacker has access to both the [[Plaintext]] (called a **crib**) and its encrypted version ([[Ciphertext]]). These can be used to reveal secret keys and code books. The term "crib" originated at Bletchley Park, the British World War II decryption operation, where it was defined as:

> A plain language (or code) passage of any length, usually obtained by solving one or more cipher or code messages, and occurring or believed likely to occur in a different cipher or code message, which it may provide a means of solving.
> 
> 	- The Bletchley Park 1944 Cryptographic Dictionary formatted by Tony Sale, 2001


### History

The usage "crib" was adapted from a slang term referring to cheating (e.g., "I cribbed my answer from your test paper"). A "crib" originally was a literal or interlinear translation of a foreign-language text—usually a Latin or Greek text—that students might be assigned to translate from the original language.

The idea behind a crib is that cryptologists were looking at incomprehensible ciphertext, but if they had a clue about some word or phrase that might be expected to be in the ciphertext, they would have a "wedge," a test to break into it. If their otherwise random attacks on the cipher managed to sometimes produce those words or (preferably) phrases, they would know they might be on the right track. When those words or phrases appeared, they would feed the settings they had used to reveal them back into the whole encrypted message to good effect.

In the case of Enigma, the German High Command was very meticulous about the overall security of the Enigma system and understood the possible problem of cribs. The day-to-day operators, on the other hand, were less careful. The Bletchley Park team would guess some of the plaintext based upon when the message was sent, and by recognizing routine operational messages. For instance, a daily weather report was transmitted by the Germans at the same time every day. Due to the regimented style of military reports, it would contain the word Wetter (German for "weather") at the same location in every message. (Knowing the local weather conditions helped Bletchley Park guess other parts of the plaintext as well.) Other operators, too, would send standard salutations or introductions. An officer stationed in the Qattara Depression consistently reported that he had nothing to report. "Heil Hitler," occurring at the end of a message, is another well-known example.

more: https://en.wikipedia.org/wiki/Known-plaintext_attack