# Third times the charm - Cryptography - Easy
Author: MdHaazim | Team: FreshOuttaStack | Date: 2025-08-31

# About
The challenge provided a string of letters: EDEWIbsygfuyaxkktlnqvjuui and mentions along the lines of "the first layer shifts by 2, then the next by 1, then others stays the same".

# How to solve 
I used CyberChef (https://gchq.github.io/CyberChef/) to decode the ciphertext by manually applying Caesar (ROT) shifts, layer by layer.

### Step 1: Start with ROT13
I loaded the ciphertext into CyberChef and used the ROT13 operation (which is just a Caesar shift).
I changed the rotation amount to -2, and it revealed the first 3 letters of the flag. The rest of the text still looked encrypted.
### Step 2: Adjust the shift for the next layer
I then decreased the rotation to -3, and this revealed the next 3 letters of the flag. However, the first 3 letters were no longer correct, since the new shift affected the entire input.
### Step 3: Extract in segments
I repeated this process:
- Shift -2 → copy first 3 letters
- Shift -3 → copy next 3 letters
- Shift -4 → copy next 3 letters
- And so on...
Each time, I captured a 3-letter segment of the decrypted flag and ignored the rest that was affected by the shift.
### Step 4. Reconstruct the flag
After extracting all the 3-letter segments from each shift step, I combined them to form the full flag.

# Flag
```
CBCTF{you_captured_me_finally}
```
