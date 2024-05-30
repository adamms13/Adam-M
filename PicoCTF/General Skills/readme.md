# Challenge 1 - Obedient Cat

![Screenshot from 2024-05-29 07-37-32](https://github.com/magdzzia/CTF-Writeups/assets/158006085/be8da5ec-3b59-48c8-9388-1e3171944076)

A simple file was downloaded, and considering that 'cat' was in the title... why don't we try the cat command?

![Screenshot from 2024-05-28 22-50-00](https://github.com/magdzzia/CTF-Writeups/assets/158006085/2ec47515-be8b-49f8-a623-40953c973551)

Flag: picoCTF{s4n1ty_v3r1f13d_28e8376d}

#  Challenge 2 - Python Wrangling

![Screenshot from 2024-05-29 07-38-27](https://github.com/magdzzia/CTF-Writeups/assets/158006085/aa4a7262-3540-4d45-81fd-38ecc85c5fac)

Given a Python script, a password, and a flag I would need to translate, I first opened the Python script to see what it would do.

In a .txt file, the password was: dbd1bea4dbd1bea4dbd1bea4dbd1bea4
In a .txt file, the flag was: gAAAAABgUAIWuksW6PU7W1WFXiBWkF2S8VhtL_5335iazHhuBnWloiyt3ZAFwR2zyuG7iZLSVPaQIZLTxgo-WXIk6Cnk7-KZm1g1qo_v1zDMK5wDocmVFxL0o5ae6OrB9VKdh3HerIsy

![Screenshot from 2024-05-29 07-33-14](https://github.com/magdzzia/CTF-Writeups/assets/158006085/85bf751e-4c2f-439b-b2ce-e804e590774c)

I see that a -e option encrypts with a password, and a -d option decrypts with a password.

So I ran the script with the flag file.

![Screenshot from 2024-05-29 07-35-55](https://github.com/magdzzia/CTF-Writeups/assets/158006085/351bb7d4-09c5-4db5-80f0-376a91705011)

Flag: picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}

# Challenge 3 - Wave a Flag

![Screenshot from 2024-05-29 07-38-50](https://github.com/magdzzia/CTF-Writeups/assets/158006085/32ab21e0-6981-4e0e-bb14-d17434e7c7ec)

This was the file that was downloaded:

![Screenshot from 2024-05-29 07-39-27](https://github.com/magdzzia/CTF-Writeups/assets/158006085/9352a1dc-e982-4a57-bdc9-bf95cc46e4d1)

Trying to cat the file, it didn't work.

![Screenshot from 2024-05-29 07-40-42](https://github.com/magdzzia/CTF-Writeups/assets/158006085/74a82121-77a5-45a6-bc8f-fb955910ec71)

So instead, I opted in for using strings from now on to open a file. And since I know the string I'm looking for, I can combine strings with grep.

![Screenshot from 2024-05-29 07-42-51](https://github.com/magdzzia/CTF-Writeups/assets/158006085/23b8d9c6-1001-42ea-bcb7-fe4300ca672e)

Flag: picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}

# Challenge 4 - Nice NetCat...

![Screenshot from 2024-05-29 15-53-50](https://github.com/magdzzia/CTF-Writeups/assets/158006085/9b945041-a859-46e3-b1f4-9d9a80643e1e)

I know I needed to connect with nc through the terminal, and did just that:

![Screenshot from 2024-05-29 15-55-09](https://github.com/magdzzia/CTF-Writeups/assets/158006085/09b0c236-e537-49e5-b188-5f57a33ca3d4)

I was given a list of numbers and honestly, I had to use the hint as I didn't really know where to go with it. 

I came across ASCII and immediately was dumbfounded. 

Yep, those are ASCII numbers. So I just plopped them into an ASCII > Text converter and got the flag. Now I know that whenever I see a list of numbers, always try ASCII.

Flag: picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}
