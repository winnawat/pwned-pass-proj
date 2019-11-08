# pwned-pass-proj
DATA512 project on exploratory analysis on pwned passwords

# Project proposal
Today, data security is one of the top concerns for both individuals and organizations. We all have sensitive information that we want protected. Unfortunately, nowadays, these information has to be online for them to be useful. Often, the only thing separating bad actors and our important and private data is a password. Still, hacks happen every day and almsot anyone can be a victim of a data breach. [Even Mark Zuckerberg's Twitter was compromised](https://www.theguardian.com/technology/2016/jun/06/mark-zuckerberg-hacked-on-twitter-and-pinterest).  
This project aims to look at what proportions of the passwords that have been dumped on the internet are "easy".  
That is:
- Passwords that are generated from consecutive keys on the keyboard such as "asdfasdf."
- Passwords that are a series of numbers in a date format. This is uaually the case for passwords derived from birthdays or important dates such as 11072019.
- Passwords that are vulnerable to dictionary attacks.
- Any other categories of passwords that may arise as further research into this topic is done.

The intended outcome is to compel individuals to think twice before setting up passwords for anything. Even if that password is not protecting anything important. Passwords that may appear secure may have already been breached for thousands of times by hackers.

## The data
The data used in this study is taken from a website by Troy Hunt [haveibeenpwned.com](https://haveibeenpwned.com/Passwords). Troy is a  Microsoft Regional Director and Microsoft Most Valuable Professional for Developer Security and a significant contributor in the cybersecurity community. Troy has made the data freely available to the public with no license and he has persoanlly allowed the dataset to be used for this project.

### What is contains
The dataset is a list of hashed(SHA-1) passwords that have been compromised in a data dump before and their corresponding number of times they appear on data breaches. The compromised passwords are gathered by Troy himself from various data dumps on the internet. He kept on adding new entries as new dumps happened.  
_Format of the data_ 

|passwords|number of times the password appears on a dump|
|----|----|
|hashed passwords|count|

## Unknowns and dependencies
- It is unclear how large the portion of "easy" passwords will be among the most frequently exploited passwords. If the portion is low, the findings could be very underwhelming. This may have the opposite effect as it can create a false sense of security among users of "easy" passwords.
- The computational power requried to generate keyboard random walks, numbers in date formats, terms for dictionary attack could be masssive. This is almost equivalent to trying to crack a password. Therefore, some clever restrictions on the password generation will have to be implemented.
