# The Beginning of Solving PicoCTF

For this summer, I made it my goal to learn more about CTFs.

And what better way to do that than trying to solve all of Pico's Practice Gym CTFs, with writeups.

## Challenges Completed: 5

# Challenge 1 - Obedient Cat

![Screenshot from 2024-05-29 07-37-32](https://github.com/magdzzia/CTF-Writeups/assets/158006085/be8da5ec-3b59-48c8-9388-1e3171944076)

A simple file was downloaded, and considering that 'cat' was in the title... why don't we try the cat command?

![Screenshot from 2024-05-28 22-50-00](https://github.com/magdzzia/CTF-Writeups/assets/158006085/2ec47515-be8b-49f8-a623-40953c973551)

Flag: picoCTF{s4n1ty_v3r1f13d_28e8376d}

# Challenge 2 - Mod 26

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

#  Challenge 3 - Python Wrangling

![Screenshot from 2024-05-29 07-38-27](https://github.com/magdzzia/CTF-Writeups/assets/158006085/aa4a7262-3540-4d45-81fd-38ecc85c5fac)

Given a Python script, a password, and a flag I would need to translate, I first opened the Python script to see what it would do.

In a .txt file, the password was: dbd1bea4dbd1bea4dbd1bea4dbd1bea4
In a .txt file, the flag was: gAAAAABgUAIWuksW6PU7W1WFXiBWkF2S8VhtL_5335iazHhuBnWloiyt3ZAFwR2zyuG7iZLSVPaQIZLTxgo-WXIk6Cnk7-KZm1g1qo_v1zDMK5wDocmVFxL0o5ae6OrB9VKdh3HerIsy

![Screenshot from 2024-05-29 07-33-14](https://github.com/magdzzia/CTF-Writeups/assets/158006085/85bf751e-4c2f-439b-b2ce-e804e590774c)

I see that a -e option encrypts with a password, and a -d option decrypts with a password.

So I ran the script with the flag file.

![Screenshot from 2024-05-29 07-35-55](https://github.com/magdzzia/CTF-Writeups/assets/158006085/351bb7d4-09c5-4db5-80f0-376a91705011)

Flag: picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}

# Challenge 4 - Wave a Flag

![Screenshot from 2024-05-29 07-38-50](https://github.com/magdzzia/CTF-Writeups/assets/158006085/32ab21e0-6981-4e0e-bb14-d17434e7c7ec)

This was the file that was downloaded:

![Screenshot from 2024-05-29 07-39-27](https://github.com/magdzzia/CTF-Writeups/assets/158006085/9352a1dc-e982-4a57-bdc9-bf95cc46e4d1)

Trying to cat the file, it didn't work.

![Screenshot from 2024-05-29 07-40-42](https://github.com/magdzzia/CTF-Writeups/assets/158006085/74a82121-77a5-45a6-bc8f-fb955910ec71)

So instead, I opted in for using strings from now on to open a file. And since I know the string I'm looking for, I can combine strings with grep.

![Screenshot from 2024-05-29 07-42-51](https://github.com/magdzzia/CTF-Writeups/assets/158006085/23b8d9c6-1001-42ea-bcb7-fe4300ca672e)

Flag: picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}

# Challenge 5 - Information

![Screenshot from 2024-05-29 07-43-47](https://github.com/magdzzia/CTF-Writeups/assets/158006085/45a0dbf2-98fb-4bc1-8437-4553b1e30396)

So I downloaded the picture, and here it was:

![cat](https://github.com/magdzzia/CTF-Writeups/assets/158006085/4d594754-d238-4f32-bca4-4ad6c2bc9aab)

The first thing to do is to string and grep anything just in case.

I got nothing.

So I checked it's details with exiftool and saw a string of characters under the license section.

![Screenshot from 2024-05-29 13-14-22](https://github.com/magdzzia/CTF-Writeups/assets/158006085/54c42a33-a246-48e4-b4de-746b5d2bc8b9)

Took that into cyberchef and used magic, and found that it was base64 encoded.

Flag: picoCTF{the_m3tadata_1s_modified}

# Challenge 6 - Nice NetCat...

![Screenshot from 2024-05-29 15-53-50](https://github.com/magdzzia/CTF-Writeups/assets/158006085/9b945041-a859-46e3-b1f4-9d9a80643e1e)

I know I needed to connect with nc through the terminal, and did just that:

![Screenshot from 2024-05-29 15-55-09](https://github.com/magdzzia/CTF-Writeups/assets/158006085/09b0c236-e537-49e5-b188-5f57a33ca3d4)

I was given a list of numbers and honestly, I had to use the hint as I didn't really know where to go with it. 

I came across ASCII and immediately was dumbfounded. 

Yep, those are ASCII numbers. So I just plopped them into an ASCII > Text converter and got the flag. Now I know that whenever I see a list of numbers, always try ASCII.

Flag: picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}

# Challenge 7 - Transformation













