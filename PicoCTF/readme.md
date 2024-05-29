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

Syntax: cat [filename].txt | tr [set of characters to be replaced] [set of characters to replace with]

After learning about how sets work, I came up with this command:

cat decode.txt | tr A-Za-z N-ZA-Mn-za-m

A-Za-z means every letter in the string, plus it's lowercase.
And since tr translates 1 for 1, N-ZA-Mn-za-m means that if an A pops up in the string, it would translate to N (which is 13 letters down the alphabet), B to O, C to P and so on. Once it goes past Z, it will then hit the range of A-M, plus it's lowercase.

![Screenshot from 2024-05-28 22-50-00](https://github.com/magdzzia/CTF-Writeups/assets/158006085/7de3ddfc-40f9-442d-96ce-59ce970bec0c)

Flag: picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}

#  Challenge 3 - Python Wrangling

Given a Python script, a password, and a flag I would need to translate, I first opened the Python script to see what it would do.

In a .txt file, the password was: dbd1bea4dbd1bea4dbd1bea4dbd1bea4
In a .txt file, the flag was: gAAAAABgUAIWuksW6PU7W1WFXiBWkF2S8VhtL_5335iazHhuBnWloiyt3ZAFwR2zyuG7iZLSVPaQIZLTxgo-WXIk6Cnk7-KZm1g1qo_v1zDMK5wDocmVFxL0o5ae6OrB9VKdh3HerIsy

![Screenshot from 2024-05-29 07-33-14](https://github.com/magdzzia/CTF-Writeups/assets/158006085/85bf751e-4c2f-439b-b2ce-e804e590774c)

I see that a -e option encrypts with a password, and a -d option decrypts with a password.

So I ran the script with the flag file.

![Screenshot from 2024-05-29 07-35-55](https://github.com/magdzzia/CTF-Writeups/assets/158006085/351bb7d4-09c5-4db5-80f0-376a91705011)

Flag: picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}

# Challenge 4 - Wave a Flag






