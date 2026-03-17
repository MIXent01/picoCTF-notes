#### information

Checked metadata with exiftool. Found strange string in "license" field. It was ending with "=" so it was encoded with base64. Decoded this string and found the flag.

#### Disk, disk, sleuth!

Used "srch_strings" on disk image with "less" and found picoCTF* pattern and got the flag.

#### Disk, disk, sleuth! II 

Searched files on disk image with "fls -ro 2048 dds2-alpine.flag.img | less" and found txt provided txt file in description. Found inum number and used icat on it with "icat -o 2048 dds2-alpine.flag.img 18291" and got the flag.

#### Wireshark doo dooo do doo...

Analyzed packet file with wireshark. Followed TCP stream and found something interesting in stream 5. It looked liked pico flag. Tried to decrypt it with different staff. ROT13 worked and got the flag.


#### Trivial Flag Transfer Protocol

Analyzed packet file with wireshark. Followed udp streams and in stream 0 found something about file "instructions.txt.octet". I followed other streams and found more files were transferred. Found 6 files overall. Downloaded them and checked "instructions.txt". It was in strange text so I decrypted it with ROT13. Followed the instructions. Downloaded .deb program. It was steghide. Used it on pictures with given passphrase and got the flag.




