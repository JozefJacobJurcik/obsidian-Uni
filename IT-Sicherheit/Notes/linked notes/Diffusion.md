
*Diffusion* means that if we change a single bit of the [[plaintext]], then about half of the bits in the [[ciphertext]] should change, and similarly, if we change one bit of the ciphertext, then about half of the plaintext bits should change. This is equivalent to the expectation that encryption schemes exhibit an [[Avalanche Effekt|avalanche effect]].

The purpose of diffusion is to hide the statistical relationship between the ciphertext and the plain text. For example, diffusion ensures that any patterns in the plaintext, such as redundant bits, are not apparent in the ciphertext. Block ciphers achieve this by "diffusing" the information about the plaintext's structure across the rows and columns of the cipher. 