- [Introduction](#introduction)
- [Notes on Part 1 (ch 1-5)](#notes-on-part-1-ch-1-5)
  - [Ch 1](#ch-1)

# Introduction
In this repo I host my notes for The **Shellcoder's Handbook: Discovering and Exploiting Security Holes**. It can be purchased from here for example: https://www.wiley.com/en-us/The+Shellcoder's+Handbook%3A+Discovering+and+Exploiting+Security+Holes%2C+2nd+Edition-p-9781118079126#downloadstab-section
or elsewhere as well. 


Side notes:
1. For the beginning of the journey look here: https://github.com/RegistersNinja/coding_from_groundup
2. There is a good accompanying course that can be found here: https://www.samsclass.info/127/127_S23.shtml 
3. A note on this book: it's old and that is true. Most resources on the internet (i.e reddit & quora) say it's still relevant. They do however mention that it can be a tough read for various reasons, as well as it's worthwhile to do research on topics from the book. A repeated message is that basically the exploitations have not changed, but the defense systems have been enhanced/put in place where they were not.
# Notes on Part 1 (ch 1-5)
## Ch 1
Interesting notes from Sam: 
1. registers like AL or AH (or smaller segments of larger registers) typically do not concern developers, they are however **important to hackers**. If you want to inject shellcode into a text field, something like 0xB942000000, the last zero bytes (that are extended to fill the bigger register) act like null terminating string bits, thus terminating your code prematurely.
2. ROP chains - an attack that injects code in a data field, but since that area of the code is not executable, the injection is just addresses where there is some code you would want to execute.
3. Since not covered previously, lea is an important mnemonic. By definition it calculates the address of something without looking it up. From [handmade.network](handmade.network): 

        lea stands for "load effective address", and it is the assembly equivalent of &. If mov destination, [source] means "look up the element at address [source] and copy it to destination", lea destination, [source] means "just get the address [source]."
4. NOP instruction - means No Operation. Originally used to pad instructions that had to be a certain word length. Used by hackers as something called a NOP sled, that helps them navigate the memory of the target machine. Has to be explored further.
5. In linux there is one heap for everything. In windows it's more complicated and there can be many heaps.