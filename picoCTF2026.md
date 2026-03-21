#### MY GIT

Cloned repo. Created blank "flag.txt". Added it with "git add" and then commited with provided username in README.md file from repo with command: "git commit -m "xd" --author="root <root@picoctf>"" and got the flag with "git push"

#### Piece by Piece

Connect files with command "cat part_aa part_ab part_ac part_ad part_ae > x". Then learned what type of archive is this with "file x". It was zip, so I used "unzip x" and got flag.

#### bytemancy 0

Searched python script. Found that it gives me flag when user_input == "\x65\x65\x65". This is "eee" in normal input. Typed "eee" as input and got a flag.

#### Printer Shares

Listed the available shares with "smbclient -L //mysterious-sea.picoctf.net -p 51427 -N" and found "shares" connected with "smbclient //mysterious-sea.picoctf.net/shares -p 51427 -N" and found "flag.txt" file. Used "get flag.txt" to get a file and read the flag 

#### SUDO MAKE ME A SANDWICH

Checked permissions with "ls -la". Checked "sudo -l". Found I can open flag.txt file with emacs. Opened it and read the flag.

#### bytemancy 1 

Check python script and found out I need to pass "e" 1751 times. Gave 1751 "e" to script and got the flag.

#### bytemancy 2 

Checked python script and found out I need to pass "\xff\xff\xff" to get a flag. I can't do this with typing "\xff\xff\xff" neither "ÿÿÿ" (from hex to string). I gave correct input with printf: "printf "\xff\xff\xff\n" | nc lonely-island.picoctf.net 58973"

#### Gatekeeper

Opened given file with ghidra and auto-analyzed it. Found that I need number bigger than 1000, which is 3 character long. The decimal 1000 is 3E8 in hex and it is 3 characters long. Got strange string: "}1f7ftc_oc_ip6832ftc_oc_ipa_99ftc_oc_ip9_TGftc_oc_ip_xehftc_oc_ip_tigftc_oc_ipid_3ftc_oc_ip{FTCftc_oc_ipocipftc_oc_ip". It looks similar to normal picoCTF flag. I reversed it and saw "pi_co_ctf" pattern, deleted it and got a flag.

#### Binary Digits

Checked if the number of bytes is divisible by 8 or 16 with "wc -c digits.bin" and checked if it was a square of a number. It was divisible by 8. I created python script to group by 8 and convert to bytes and extract it. Python code:
``` Python
with open('digits.bin', 'r') as f:
    # Read the file and strip any accidental whitespace/newlines
    data = f.read().replace('\n', '').replace(' ', '')

# Group by 8 and convert to bytes
byte_array = bytearray()
for i in range(0, len(data), 8):
    byte_chunk = data[i:i+8]
    if len(byte_chunk) == 8:
        byte_array.append(int(byte_chunk, 2))

with open('x', 'wb') as out:
    out.write(byte_array)
```
Next, I checked what type of file it is with "file x". It was JPEG file. Opened it and there was a flag in the picture.



