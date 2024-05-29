# The Beginning of Solving PicoCTF

For this summer, I made it my goal to learn more about CTFs.

And what better way to do that than trying to solve all of Pico's Practice Gym CTFs, with writeups.

## Challenges Completed: 0

# Challenge 1 - Obedient Cat

A simple file was downloaded, and considering that 'cat' was in the title... why don't we try the cat command?

![Screenshot from 2024-05-28 22-50-00](https://github.com/magdzzia/CTF-Writeups/assets/158006085/2ec47515-be8b-49f8-a623-40953c973551)

Flag: picoCTF{s4n1ty_v3r1f13d_28e8376d}

# Challenge 2 - Mod 26

Given cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}, figure out the flag. Pretty simple, since Rot13 was given in the question.

But other than using dcode or cyberchef, I wanted to figure out how to do it in the terminal, and stumbled across tr - the command used to translates characters from an input to a different output.

Syntax: cat [filename].txt | tr [characters] [characters to replace with]

