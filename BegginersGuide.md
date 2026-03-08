

## The Beginner's Guide to the picoGym

### Section 1 (Sanity)

#### 1. Obedient Cat

Read the file you downloaded

#### 2. Super SSH 

Used command "ssh ctf-player@titan.picoctf.net -p 56307" with password f3b61b38

#### 3. What's a net cat?

Used netcat with command: "nc fickle-tempest.picoctf.net 52934"


### Section 2

#### 1. Mod 26

Decoded given text with ROT13

#### 2. Warmed Up

Changed number from base 16 to base 10. Remember to write result in good format. If x is the answer write: 'picoCTF{x}'

#### 3. 2warm

Changed number from base 10 to  base 2. Remember to write result in good format. If x is the answer write: 'picoCTF{x}'

#### 4. Bases

Decoded from base64. Remember to write result in good format. If x is the answer write: 'picoCTF{x}'


### Section 3

#### 1. Wave a flag

Downloaded a program. Gave executable permissions (chmod u+x warm) and typed ./warm -h

#### 2. Tab, Tab, Attack

Unziped the file and found executable and used it.

#### 3. Insp3ct0r

Searched html, css and javascript files of the website to find a flag.

#### 4. strings it

Used strings strings, in terminal additionaly I used 'grep' to capture the string with 'picoCTF' beginning. Command: strings strings | grep "picoCTF"

#### 5. First Grep

Used grep with 'picoCTF' to find a flag. Command: grep -o "picoCTF{.*}" file

#### 6. where are the robots

Looked in /robots.txt path and went futher with given new path.


### Section 4 (Python)

#### 1. Python Wrangling

Used this python program with given password on given file to decode. Command python ende.py -d flag.txt.en

#### 2. PW Crack 1

Opened python program and found the password in level_1_pw_check() function in if statement.

#### 3. PW Crack 2

Dectrypted password in python program in function level_2_pw_check() in if statement with python code.

#### 4. PW Crack 3

Saw the code and found: pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]. Then I tried every password and found the flag.

#### 5. PW Crack 4

Change level_4_pw_check() function to accept an argument "pw" and then pass it to hash function and deleted print with "password incorrect" info. Then check every possible password with for loop.

#### 6. PW Crack 5

Change level_5_pw_check() function to accept an argument "pw" and then pass it to hash function and deleted pritn with "password incorrect" info. Then wrote this code to check every possible password from dictionary.txt

```python
pos_pw_list = open("dictionary.txt", "r").readlines()

for pw in pos_pw_list:
    level_5_pw_check(pw.strip())
```

### Section 5

#### 1. Enhance!

Read svg file with "cat drawing.flag.svg and found flag in it.

#### 2. Big Zip

Used grep. Command: grep -r "picoCTF{.*}" big-zip-files

#### 3. vault-door-training

Opened java file and there was a password.

#### 4. keygenme-py

Analyzed python script. Checked check_key function and found hashes. Then wrote own script to get a flag.

The script:
```python
#!/usr/bin/python

import hashlib

key_part_static1_trial = "picoCTF{1n_7h3_kk3y_of_"
key_part_static2_trial = "}"

username_trial = "BENNETT"
bUsername_trial = b"BENNETT"

hash = hashlib.sha256(bUsername_trial).hexdigest()
dynamic = hash[4] + hash[5] + hash[3] + hash[6] + hash[2] + hash[7] + hash[1] + hash[8]

flag = key_part_static1_trial + dynamic + key_part_static2_trial

print(flag)
```

#### 5. buffer overflow 0

Made simply buffer overflow with more than 100 letters letters 'a'