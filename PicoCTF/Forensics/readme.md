# Challenge 1 - Information

![Screenshot from 2024-05-29 07-43-47](https://github.com/magdzzia/CTF-Writeups/assets/158006085/45a0dbf2-98fb-4bc1-8437-4553b1e30396)

So I downloaded the picture, and here it was:

![cat](https://github.com/magdzzia/CTF-Writeups/assets/158006085/4d594754-d238-4f32-bca4-4ad6c2bc9aab)

The first thing to do is to string and grep anything just in case.

I got nothing.

So I checked it's details with exiftool and saw a string of characters under the license section.

![Screenshot from 2024-05-29 13-14-22](https://github.com/magdzzia/CTF-Writeups/assets/158006085/54c42a33-a246-48e4-b4de-746b5d2bc8b9)

Took that into cyberchef and used magic, and found that it was base64 encoded.

Flag: picoCTF{the_m3tadata_1s_modified}
