# Challenge 1 - Mod 26

![Screenshot from 2024-05-29 07-38-10](https://github.com/magdzzia/CTF-Writeups/assets/158006085/b0aa2d76-8b0b-40fc-90d0-3a21e7c55a32)

Given cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}, figure out the flag. Pretty simple, since Rot13 was given in the question.

But other than using dcode or cyberchef, I wanted to figure out how to do it in the terminal, and stumbled across tr - the command used to translates characters from an input to a different output.

Syntax: cat [filename].txt | tr [set of characters to be replaced] [set of characters to replace with]

After learning about how sets work, I came up with this command:

cat decode.txt | tr A-Za-z N-ZA-Mn-za-m

A-Za-z means every letter in the string, plus it's lowercase.
And since tr translates 1 for 1, N-ZA-Mn-za-m means that if an A pops up in the string, it would translate to N (which is 13 letters down the alphabet), B to O, C to P and so on. Once it goes past Z, it will then hit the range of A-M, plus it's lowercase.

![Screenshot from 2024-05-28 22-50-00](https://github.com/magdzzia/CTF-Writeups/assets/158006085/7de3ddfc-40f9-442d-96ce-59ce970bec0c)

Flag: picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}
