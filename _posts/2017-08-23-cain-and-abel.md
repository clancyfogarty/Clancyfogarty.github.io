---
layout: post
title: Cain and Abel
---

*I recently did a case study for the Cain and Abel software for my Cyber Forensics class at the University of San Diego. The following was my results, opinion and suggestions in regards to the topic and the questions i received.*

**Explain the two different types of attacks that can be performed in Cain and Abel to crack user account passwords. Which do you think is the most effective and why?**

The two different types of attacks that can be performed in Cain and Abel are Brute force and Dictionary attacks. Brute force is the process of attempting to crack a password by trying different combinations of numbers and letters. This is an exhaustive effort rather than employing a strategy (TechTarget, 2017). This approach can be very time consuming. This type of attack however lets the attacker set the minimum and maximum password lengths as well as choose a predefined set of characters.

A dictionary attack as described by TechTarget is a password cracking method used to break in by entering multiple or all words in the dictionary to find out the password (TechTarget, 2017). This method can also be used to find the key needed to decrypt a message. This type of attack comes from the theory that most users have passwords that consist of common words or phrases. For this lab we utilized the Wordlist.txt document to act as our dictionary as we performed our attack. Dictionary attacks are more efficient than brute force due to significantly less time needed to perform an attack and successfully crack the password. This attack takes less time because whole words or phrases are tried instead of single letters and numbers.

**Compare and contrast the results from the two methods used to crack the accounts for the three passwords encrypted by the two hash algorithms. What conclusions can you make after using these two methods?**

Brute-force attacks (NTLM):

* User 11 – When I first ran the brute force attack I saw a significant amount of time quoted  (see screenshot below). I found  that if I adjusted the password length max to 7 characters I was able to crack the password in a shorter amount of time. I played around with the combination settings such as upper case letters, numbers and symbols, I noticed that as more combinations were enabled the time quoted increased.

{:.center}
![]({{ site.baseurl }}/img/user11-ntlm.png)

* User 12 – Upon running this attack i noticed the quoted time was higher than User 11. I would assume this was because the password was more complex. I attempted to decrease the quoted time by disabling some combination settings, however this did not decrease the time to a manageable amount. I stopped the test before it was able to solve the password, but had I let the attack carry out I can confidently say the password for this user would have been cracked.

{:.center}
![]({{ site.baseurl }}/img/CA2.png)

* User 13 – This attack was quoting years to solve as well. The difference between a brute force attack on this user compared to the other users is even changing certain setting such as character length and combination settings the quote time stayed the same. I did not successfully uncover the password with this attack. I would not use this method to crack a harder password such as the password for user 13 due to the length of time needed to be successful.

{:.center}
![]({{ site.baseurl }}/img/CA3.png)

Dictionary attacks (NTLM):

* User 11 – The dictionary attack on this user took way less time than the brute force attack. Utilizing the wordlist.txt Cain and Abel was able to crack the password in under a minute. This type of attack seemed more efficient to me.

{:.center}
![]({{ site.baseurl }}/img/CA4.png)

* User 12 – For this attack the wordlist.txt was used, but before running the attack the file position needed to be reset. I noticed that if I did not reset the file position the password was not be cracked. This attack was fairly efficient as well and only took a couple mins to solve the password. Again I believe this type of attack was more efficient than the brute force attack on this user by far.

{:.center}
![]({{ site.baseurl }}/img/CA5.png)

* User 13 – Like the previous dictionary attack I had to reset the initial file position before running the attack. This type of attack was unsuccessful. The entire wordlist.txt was searched with no hashes cracked. This is useful to visualize how important it is to have a harder password when facing brute force or dictionary type attacks on your passwords.

{:.center}
![]({{ site.baseurl }}/img/CA6.png)

Dictionary and Brute force attacks (LM) –

I had some trouble with the LM hashes loading at first. I installed the Cain and Abel software into a virtual box running windows 7, but that did not fix the issue. After doing some more research I was able to fix the issue. A setting “do not store LAN manager has value on next password change” was automatically enabled for the program. After this setting was disabled I was able to load the lm hashes, thus I was ready to begin password cracking. Also it is worth noting I had the same results for the brute force attacks on the users using the lm hashes method. The only exception was the time quoted grew significantly and I was unable to crack the user12 password using brute force.

* User 11 – The dictionary attack was able to solve both LM hashes correctly in a few minutes. This method is definitely more secure than the html hashes.

{:.center}
![]({{ site.baseurl }}/img/CA7.png)

* User 12  - This attack was only successful for one hash. For some reason it doesn't show what the hash is translated to. I think this is because the last part is a number 7 which is not in the wordlist.txt, but i'm not too sure exactly.

{:.center}
![]({{ site.baseurl }}/img/CA8.png)

* User 13 – For this attack it was again able to crack the second hash of the password and provides the user with a D. This is just another example of why LM hashes are more secure.

{:.center}
![]({{ site.baseurl }}/img/CA9.png)

* All users screenshot - This is the overall results for running the dictionary attacks with lm hashes on my virtual box machine. As you can see the only password that was cracked was user 11.

{:.center}
![]({{ site.baseurl }}/img/CA10.png)

This brings me to conclude that lm hashes appeared to be harder to crack with the tools we used for this exercise. Overall the dictionary attack was more efficient for both types of attacks for all users. However it is important to note when running a dictionary attack the attack is only as good as the word file you are using to act as the “dictionary”. I found this out by creating extra users with odd passwords such as “longpassword”. Both those words separate are found in the wordlist.txt,  but it was unfortunately not able to crack this password utilizing both ntlm or lm hashes.

**Research and thoroughly discuss another algorithm used to store passwords that was not discussed here. (Include APA references.)**

Advanced Encryption standard (AES) is the algorithm used by the United States government (Storagecraft, 2017). It uses 128-bit but can also use keys of 192 and 256 for better encryption (Storagecraft, 2017). The block length can be up to 128 bits. It is a symmetric encryption algorithm meaning the sender and receiver must both know the key otherwise it will not be decrypted. The way it works is complicated to explain so I will use the explanation from Tech Target, “The AES encryption algorithm defines a number of transformations that are to be performed on data stored in an array. The first step of the cipher is to put the data into an array; after which the cipher transformations are repeated over a number of encryption rounds. The number of rounds is determined by the key length, with 10 rounds for 128-bit keys, 12 rounds for 192-bit keys and 14 rounds for 256-bit keys.” (TechTarget, 2017). It then performs transformation on the data. During the first substitution the data is switched with a substitution table. During the second transformation the data rows are shifted. During the third transformation the data columns are mixed. Those transformations are performed depending on the encryption key. This encryption algorithm seems to be the most secure out of the other options out in the market. The AES encryption algorithm would be the best one to use when attempting to encrypt highly confidential information such as government data or sensitive emails.

The National Institute of Standards and Technology (NIST) started the development of AES in 1997 to counteract the current algorithm Data Encryption Standard (DES) which had become vulnerable to brute-force attacks (TechTarget, 2017).  They designed this algorithm to be very versatile so it could work with hardware, software, and restricted environments (TechTarget, 2017). The key things the NIST were looking for when replacing the DES algorithm were cost, security and implementation. They wanted to have a good balance of each. They ultimately selected Rijndael algorithm which was invented by two Belgium cryptographers’ names John Daemen and Vincent Rijmen. This algorithm became AES (TechTarget, 2017). This encryption standard became federal government standard in 2002.

{:.center}
![]({{ site.baseurl }}/img/CA11.jpg)
Figure 1.1 AES Design (TechTarget, 2017).

The website aesencryption.net provides brief examples of AES encryption in Java and PHP to better understand how this algorithm works (AES encryption, 2017).

**Research another password recovery software program and provide a thorough discussion of it. Compare and contrast it to Cain and Abel. (Include APA references.)**

Ophcrack is another password recovery software that I have played with. It is a free Windows password cracker based on rainbow tables (Ophcrack, 2017). This tool can run on various platforms such as Windows, Linux, Mac OS X and more. Like Cain and Abel it can crack LM and NTLM hashes. The program is also open source. The null byte website does a great job of showing the user how to download the program by either online download, installing from a CD or DVD,  USB, or external hard drive (Null Byte, 2017). I actually used this resource to download Ophcrack on my machine and the process was smooth and easy.

A third option that we did not use was cryptanalysis. During this password cracking attempt you would use a rainbow table instead of the wordlist we used. The big difference between Ophcrack and Cain and Abel programs are that Ophcrack relies on those rainbow tables to decrypt the passwords. Cain and Abel does still provide the cryptanalysis option. One thing that stood out to me in Ophcrack that was not an option in Cain and Abel is the ability to create a bootable drive (Null Byte, 2017). This means that you don’t need to be logged into an environment such as windows. This would be a big help if the user was locked out of their login and needed a way to reset the password. My experience with Ophcrack led me to believe this tool is very user friendly. There seems to be less functionality than the Cain and Abel program, but it was still able to crack the user11 and user12 passwords just fine. Ophcrack was not able to crack my user13 password.

**Anti-virus software detects Cain and Able as malware. Do you feel that Cain and Able is malware? Why or why not?**

While many anti-virus tools feel that Cain and Abel is malware, I however disagree. On the Cain and Abel website it specifically addresses the users concern. It states that while many anti-virus tools may have signatures from this program or classify it as a Trojan virus, the program itself does not infect files, send our passwords over the internet, and all the features are clearly laid out and documented (Oxid, 2017). One article I found described malware as accessing and tempering the information on the computer without the user’s knowledge or consent (ACM Digital Library, 2017). In the case of Cain and Abel the user is downloading this program under an administrative account. The software only accesses information on the computer with the user’s consent and knowledge. The user decides which passwords on the system to find out. At no point while using this program does the user not know what is going on. With those ideas in mind I do not categorize Cain and Abel as malware, however I do believe this program is a powerful tool that can potentially be abused if in the wrong hands and should be utilized with caution.

**References**

What is dictionary attack? - Definition from WhatIs.com. (n.d.). Retrieved June 05, 2017, from http://searchsecurity.techtarget.com/definition/dictionary-attack

What is brute force cracking? - Definition from WhatIs.com. (n.d.). Retrieved June 05, 2017, from http://searchsecurity.techtarget.com/definition/brute-force-cracking

Capturing system-wide information flow for malware detection and analysis. (n.d.). Retrieved June 06, 2017, from http://dl.acm.org/citation.cfm?id=1315261

Home. (n.d.). Retrieved June 06, 2017, from http://www.oxid.it/
5 Common Encryption Algorithms and the Unbreakables of the Future. (2016, October 03). Retrieved June 08, 2017, from https://www.storagecraft.com/blog/5-common-encryption-algorithms/

AES encryption. (n.d.). Retrieved June 08, 2017, from http://aesencryption.net/

What is Advanced Encryption Standard (AES)? - Definition from WhatIs.com. (n.d.). Retrieved June 08, 2017, from http://searchsecurity.techtarget.com/definition/Advanced-Encryption-Standard

Ophcrack. (n.d.). Retrieved June 09, 2017, from http://ophcrack.sourceforge.net/

Bradley, J., M., Quarter, J., LaTour, C., Domalaon, K. I., C., . . . Marino, C. C. (2012, September 23). How to Recover Passwords for Windows PCs Using Ophcrack. Retrieved June 09, 2017, from https://null-byte.wonderhowto.com/how-to/recover-passwords-for-windows-pcs-using-ophcrack-0135358/
