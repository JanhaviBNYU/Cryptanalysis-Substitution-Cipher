# Cryptanalysis Substitution Cipher 

The project consists of a software implementation of an algorithm that tries to decrypt an L-symbol challenge ciphertext using a plaintext dictionary (containing a number q of English words or plaintexts obtained as a sequence of space-separated English words), using only partial knowledge of the encryption algorithm used, and no knowledge of any keys involved. The program's goal is to find the plaintext (as one of the plaintexts in Dictionary1 or one sequence of space-separated English words from those included in Dictionary2) and decrypt a ciphertext on the longest possible Dictionary2, within the afforded amount of time.

Inputs :</br>
    the number t of key symbols</br>
    an L-symbol challenge ciphertext</br>
    
Algorithm Implemented:</br>
For Dictionary 1:</br>
1. Import the Dictionary 1 in memory.</br>
2. Read the next 100 character sentence from Dictionary 1, say p</br>
3. Perform an operation (Cipher Text (c) – Plaintext (p)) to get a string of 100 numbers.</br>
4. Calculate the number of Unique Numbers in this string, say n.</br>
5. If n == t,</br>
    (Yes)</br>
    If (The unique symbols are repeated as much as t)</br>
    (If t=5, L=100, there must be 5 unique symbols repeating 20 times)</br>
      (Yes)</br>
      This is the most likely required plaintext, we print it and terminate the program.</br>
6. If n != t, continue from step 2</br>
7. If no matches are found in Dictionary 1, we check Dictionary 2.</br>

For Dictionary 2:</br>
We consider a Cartesian product of all words in the dictionary as multiple possible plaintext (permutations)</br>
1. Import Dictionary 2 in memory.</br>
2. Read next word from the Dictionary 2.</br>
3. Append the word to a string, say s</br>
4. Perform the operation (Cipher Text – Plain text).</br>
5. Calculate the number of Unique Numbers in this string, say n</br>
    If n <= t continue steps 1 through 4.</br>
    If n > t, discard this and go to next permutation.</br>
6. When the string append is of 100 characters</br>
   If n == t,</br>
      (Yes)</br>
      If (The unique characters are repeated as much as t)</br>
      (If t=5, L=100, there must be 5 unique symbols repeating 20 times)</br>
        (Yes)</br>
          This is the most likely required plaintext, we print it and terminate the program.</br>
      If n != t, discard this and go to next permutation</br>
        Backtrack if the current permutation no longer is the probable candidate for plaintext.</br>



