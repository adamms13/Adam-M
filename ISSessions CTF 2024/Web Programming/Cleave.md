## ISSessions CTF 2023 
# Cleave

### The Challenge:
![1](https://github.com/magdzzia/Adam-M/assets/158006085/8dc75d16-e5c1-445b-8837-1db2fb5e6542)

When I clicked to open the link, the cleave website with a simple ui popped up:

![2](https://github.com/magdzzia/Adam-M/assets/158006085/90a625f6-15b8-47a6-9598-979be5c443fe)

I did click on inspect element to see if any easy flag was there, but you could imagine my disappointment :(

After typing out 'test' as the name, it led to a welcome screen:

![3](https://github.com/magdzzia/Adam-M/assets/158006085/f570b9e1-ecbf-4af8-949e-3265de8e0959)

### I wish they had a dark mode, but I digress...

To continue on the challenge, I tried recalling attacks that could be used on web servers & HTML from my previous classes. After what was probably about 20 minutes, I remembered about XSS. While that wasn't the answer, it led me down the road of finding out about SSTI attacks.<sup>1</sup>

But I ran into a crossroads... I had no idea how to exploit this attack.

So admittedly, I did have to do some research. Eventually, I came across a string that allowed me to test for potential SSTI attacks: 

${{<%[%"'}}%\ <sup>2</sup>

So after putting this string into the input, I was greeted with this beautiful screen. 

![5](https://github.com/magdzzia/Adam-M/assets/158006085/99ca2c6d-3cac-468d-8e64-0b3912b3ffc4)

_Now I know I'm making progress! But what do I do now..._

I did have to research quite a bit into making the proper command to exploit this vulnerability. I could have asked ChatGPT but where's the fun in that right? 

After trying to make the right single-line payload<sup>3</sup> with the commands I individually found online, I was just stumped. I felt like whatever I was trying didn't make sense. So I took to Google and found this beautiful one-liner:

{{request.application.\_\_globals\_\_.\_\_builtins\_\_.\_\_import\_\_('os').popen('insert shell command').read()}}

**Whoever I got this from, thank you.**

Having knowledge of shell, I was able to explore the system a little bit. After a bit of thinking, the first command I tried was to check the current directory's files and folders, so I attempting the following command: 

{{request.application.\_\_globals\_\_.\_\_builtins\_\_.\_\_import\_\_('os').popen('ls').read()}}

And got this:

![8](https://github.com/magdzzia/Adam-M/assets/158006085/045d9d02-7dbf-434e-994c-68dd2ce2002e)

I highlighted challenge.yml in the screenshot because that's the first thing that caught my eye. 

_I think that's where the flag is. I just need to see the text inside._ 

Which is exactly what I did. I ran this command into the input:

{{request.application.__globals__.__builtins__.__import__('os').popen('strings challenge.yml').read()}}

And poof, just like magic:

![9](https://github.com/magdzzia/Adam-M/assets/158006085/447162eb-db7c-439e-9a26-734c599a456a)

The Final Flag: EspionageCTF{u5e_sEcUr3_t3MpL@tiNg_eNgin3s}

## Lessons Learned
1: SSTI (Server Side Template Injections) are vulnerabilities based on template engines that allow malicious actors to add/run their code on the web server. 
  - Template engines are essentially blueprints for a web server that allows the content to be dynamic in the webpage.
  - SSTI works because the malicious actor is injecting malicious code into a template that would otherwise take a normal input, not expecting anything else but that normal input.

2: ${{<%[%"'}}%\ works because these are common template expressions used in the regular web templates.

3: Payloads are the strings of SSTI malicious code used for injection.

## Final Thoughts

For one of my first CTF challenges ever, I liked it a lot. It was a rush when I saw challenge.yml and definitely got me hooked on CTFs. 

