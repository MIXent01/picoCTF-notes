#### Enhance!

Read svg file with "cat drawing.flag.svg | less" and found flag in it.

#### Sleuthkit Intro

Unzipped disk image with "gzip -d disk.img.gz". Checked Linux partition length with "mmls disk.img".

#### Sleuthkit Apprentice

Used "mmls disk.flag.img" found there are two Linux partitions. First one was pretty empty and useless so I checked the second one with "fls -ro 360448 disk.flag.img | less" and found "flag.txt" file and checked it with "icat -o 360448 disk.flag.img 2371" and found the flag.

#### St3g0

Used zsteg on file and got the flag.


