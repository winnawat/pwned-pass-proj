# Final Project - Most Vulnerable Passwords
DATA512 project on exploratory analysis on pwned passwords data set.  
Win Nawat Suvansinpan

# II. Project Plan

## Introduction
Today, data security is one of the top concerns for both individuals and organizations. We all have sensitive information that we want protected. Unfortunately, these information has to be online to be useful. Often, the only thing separating bad actors and our private data is a password. Hacks happen every day and almsot anyone can be a victim of a data breach. [Even Mark Zuckerberg's Twitter was compromised](https://www.theguardian.com/technology/2016/jun/06/mark-zuckerberg-hacked-on-twitter-and-pinterest).  

### The Problem
It is tempting to set a simple password that is easy to remember. Often, users would construct passwords out of something they are familiar with. This could be a combination of one's name, date of birth, favorite sport or a series of keys on the keyboard. Meanwhile, hacks happen all the time. Once a website is breached, the hackers often dump the obtained data on the internet. This usually involves emails, passwords, and many other private information. These leaked passwords can then form a corpus of common passwords which can be used to help to gain access of other accounts with weak passwords.

### Motivation
The intended outcome is to compel individuals to think twice before setting up passwords for anything. Even if that password is not protecting anything important. This project aims to replace the common caution that is something along the line of "here are the most common passwords. Please avoid using them" with "here are the most common _types_ of password. Please avoid using them." We should not view "=-0987" as any more secure than "123456" since they are essentailly still consecutive keys on the keyboard. They may appear random and hence secure but they may have already been used for thousands of times by hackers.  

### Goals
This project aims to categorize the passwords that have been dumped on the internet into the following buckets.  

- Passwords that are generated from consecutive keys on the keyboard such as "asdfghjk" or "123qweasdzxc."
- Passwords that are a series of numbers in a date format. This is uaually the case for passwords derived from birthdays or important dates such as 11072019 for November 7th 2019.
- Passwords that are vulnerable to dictionary attacks.
- Any other categories of passwords that may arise as the topic is explored.

The fact that the passwords are hashed allows this project to take the point of view of the bad actors too. This way, it would be possible to show the percentage of most common passwords that can be covered by guessing using the passwords from the abovementioned categories alone.

Another goal of the project would be to uncover how the count of compromised passwords changed in one year. This is made possible because there are two versions of the data set that were updated one year apart.


## Data
The data used in this study is taken from a website by Troy Hunt [haveibeenpwned.com](https://haveibeenpwned.com/Passwords). Troy is a  Microsoft Regional Director and Microsoft Most Valuable Professional for Developer Security and a significant contributor in the cybersecurity community. Troy has made the data freely available to the public with no license and he has persoanlly allowed the dataset to be used for this project.  
The generated passwords according to the above categories will then be hashed and compared against this list to check if they appear on the list at all and if so, how many times have they been leaked.

There are two versions of the data. The most recent version is V.5 which is available on [haveibeenpwned.com](https://haveibeenpwned.com/Passwords). This V.5 data was updated as of July 2019 V.3 is available on the [internet archive](https://archive.org/details/academictorrents_53555c69e3799d876159d7290ea60e56b35e36a9) and was updated on July 2018.  

The dataset is a list of hashed(SHA-1) passwords that have been compromised and the corresponding number of times they appear on data dumps. The compromised passwords are gathered by Troy himself from various data dumps on the internet. He kept on adding new entries and increment the counts of the passwords that are already on the list as new dumps happened.  
_Format of the data_ 

|passwords|number of times the password appears on a dump|
|----|----|
|hashed password1|count_1|
|hashed password2|count_2|
|...|...|
|hashed password_n|count_n|

### Potential limitations
The data is manually gathered and appended by Troy Hunt. This may not be reflective of the complete population of the hacked passwords as not every hacked data is released in data dumps. Also the sources he obtain the data dumps from may not be representative of all the compromised passwords.

## Related Work
There are numerous articles about the most common passwords. In fact, the list is published yearly.
- https://www.teamsid.com/splashdatas-top-100-worst-passwords-of-2018/

An analysis on the common passwords' characteristics such as length and character composition.
- https://blog.binaryedge.io/2017/07/24/antipublic-password-analysis/


## Research Questions
The following are the research questions this project will try to answer.
1. What is the most common type (among the categories listed above) of password?
2. What is the proportion of the passwords that can be classified under the categories above.
3. How do the counts of the different categories of compromised passwords change within a year.

## Methodology and Tools

#### For Analysis
Python scripts will be used to generate the passwords under each category. These passwords are then hashed and compared to the data set to check if they are present. If so, the password's caregory will be annotated.  

#### For Reporting
The investigation will be documented in a Jupyter Notebook.
