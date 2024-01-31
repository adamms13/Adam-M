## ISSessions CTF 2023 
# Totally A Virus

### The Challenge:
![1](https://github.com/magdzzia/Adam-M/assets/158006085/162b748f-b3e1-4dc8-bb1e-690b14c78b53)

I was given a .txt file called ransom_note, so I downloaded it and opened it up:

![2](https://github.com/magdzzia/Adam-M/assets/158006085/9ce09ae4-05b6-4507-9522-80a59715ec6a)

... no comment.

Anways, given the clue in the text file, I knew that I needed to find the previous name of the file.

I knew that it's almost impossible to find previous names of downloaded files, so there had to be another way.

After looking around online, I stumbled across VirusTotal for the first time.<sup>1</sup>

![3](https://github.com/magdzzia/Adam-M/assets/158006085/d4134d62-91b8-4b09-94df-a7fdeead7c49)

I uploaded the ransom_note.txt file onto the website and noticed some interesting:

![4](https://github.com/magdzzia/Adam-M/assets/158006085/e9c05a64-ceea-45d7-877c-05e733cbf8ee)

**Last Analysis Date: 10 days ago.** 

_Hmmm.. I didn't upload this document 10 days ago._

So I decided to click under the 'details' tab and... _voila_

![5](https://github.com/magdzzia/Adam-M/assets/158006085/ed3aa7a6-ecca-4ef8-8e1e-00d2574950a5)

The Final Flag: EspionageCTF{Y0u_F0und_M3}.txt

## Lessons Learned
1. VirusTotal is an important online cybersecurity webapp that allows you to upload documents, domains, etc... to get them tested for any malicious threat. 
