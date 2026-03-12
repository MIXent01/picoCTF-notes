#### information

Checked metadata with exiftool. Found strange string in "license" field. It was ending with "=" so it was encoded with base64. Decoded this string and found the flag.

#### Disk, disk, sleuth!

Used "srch_strings" on disk image with "less" and found picoCTF* pattern and got the flag.

#### Disk, disk, sleuth! II 

Searched files on disk image with "fls -ro 2048 dds2-alpine.flag.img | less" and found txt provided txt file in description. Found inum number and used icat on it with "icat -o 2048 dds2-alpine.flag.img 18291" and got the flag.
