# Cryptanalysis Substitution Cipher 

The project consists of a software implementation of an algorithm that tries to decrypt an L-symbol challenge ciphertext using a plaintext dictionary (containing a number q of English words or plaintexts obtained as a sequence of space-separated English words), using only partial knowledge of the encryption algorithm used, and no knowledge of any keys involved. Your program's goal is to find the plaintext (as one of the plaintexts in Dictionary1 or one sequence of space-separated English words from those included in Dictionary2) and within a reasonable amount of time. Your program will be tested on different-length versions of Dictionary2 and your program's goal should be to successfully decrypt a ciphertext on the longest possible Dictionary2, within the afforded amount of time.

Inputs :
    the number t of key symbols,
    an L-symbol challenge ciphertext,

where each symbol is either a space or one of the 26 lower-case letters from the English alphabet (thus, not a special character, punctuation symbol or upper-case letter). Your program should return as output a guess for which L-symbol plaintext was encrypted, where again each symbol is either a space or one of the 26 lower-case letters from the English alphabet (thus, not a special character, punctuation symbol or upper-case letter). A text file Dictionary1 containing a number u of L-symbol candidate plaintexts will be provided to you (as an attachment at the top of this page), as an example, but during testing your program will be run using a similar file, with different content. A text file Dictionary2 containing a number v of English words will be provided to you (as an attachment at the top of this page), but during testing your program will be run using a similar file, with different content, and variable lengths v.

Algorithm Implemented:
For Dictionary 1:
1. Import the Dictionary 1 in memory.
2. Read the next 100 character sentence from Dictionary 1, say p
3. Perform an operation (Cipher Text (c) – Plaintext (p)) to get a string of 100 numbers.
4. Calculate the number of Unique Numbers in this string, say n.
5. If n == t,
    (Yes)
    If (The unique symbols are repeated as much as t)
    (If t=5, L=100, there must be 5 unique symbols repeating 20 times)
      (Yes)
      This is the most likely required plaintext, we print it and terminate the program.
6. If n != t, continue from step 2
7. If no matches are found in Dictionary 1, we check Dictionary 2.

For Dictionary 2:
We consider a Cartesian product of all words in the dictionary as multiple possible plaintext (permutations)
1. Import Dictionary 2 in memory.
2. Read next word from the Dictionary 2.
3. Append the word to a string, say s
4. Perform the operation (Cipher Text – Plain text).
5. Calculate the number of Unique Numbers in this string, say n
    If n <= t continue steps 1 through 4.
    If n > t, discard this and go to next permutation.
6. When the string append is of 100 characters
   If n == t,
      (Yes)
      If (The unique characters are repeated as much as t)
      (If t=5, L=100, there must be 5 unique symbols repeating 20 times)
        (Yes)
          This is the most likely required plaintext, we print it and terminate the program.
      If n != t, discard this and go to next permutation
        Backtrack if the current permutation no longer is the probable candidate for plaintext.



