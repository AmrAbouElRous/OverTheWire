# Bandit Level 12 → Level 13

## 🧠 Goal

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

---

## 🔐 Credentials

- **Username:** `bandit12`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

---

## 🖥️ Commands Used

```bash
#make a directory under /temp then copy file into it then rename it
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ mktemp -d /tmp/amr.XXX
/tmp/amr.Llr
bandit12@bandit:~$ cp data.txt /tmp/amr.Llr
bandit12@bandit:~$ cd /tmp/amr.Llr
bandit12@bandit:/tmp/amr.Llr$ ls
data.txt
bandit12@bandit:/tmp/amr.Llr$ mv data.txt test
bandit12@bandit:/tmp/amr.Llr$ ls
test

# the puzzle begins here
bandit12@bandit:/tmp/amr.Llr$ ls
test
bandit12@bandit:/tmp/amr.Llr$ file test
test: ASCII text
bandit12@bandit:/tmp/amr.Llr$ xxd -r test >file1
bandit12@bandit:/tmp/amr.Llr$ ls
file1  test
bandit12@bandit:/tmp/amr.Llr$ file file1
file1: gzip compressed data, was "data2.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 585
bandit12@bandit:/tmp/amr.Llr$ rm file1
bandit12@bandit:/tmp/amr.Llr$ ls
test
bandit12@bandit:/tmp/amr.Llr$ ls
test                                                                                                 
bandit12@bandit:/tmp/amr.Llr$ ls
test                                                                                                 
bandit12@bandit:/tmp/amr.Llr$ xxd -r test > file1                                                    
bandit12@bandit:/tmp/amr.Llr$ ls                                                                     
file1  test                                                                                          
bandit12@bandit:/tmp/amr.Llr$ file file1                                                             
file1: gzip compressed data, was "data2.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 585                                                          
bandit12@bandit:/tmp/amr.Llr$ mv file1 file1.gz
bandit12@bandit:/tmp/amr.Llr$ ls                                                                     
file1.gz  test                                                                                       
bandit12@bandit:/tmp/amr.Llr$ file file1.gz                                                          
file1.gz: gzip compressed data, was "data2.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 585                                                       
bandit12@bandit:/tmp/amr.Llr$ gzip -d file1.gz                                                       
bandit12@bandit:/tmp/amr.Llr$ ls
file1  test                                                                                          
bandit12@bandit:/tmp/amr.Llr$ file file1
file1: bzip2 compressed data, block size = 900k                                                      
bandit12@bandit:/tmp/amr.Llr$ mv file1 file1.bz2                                                     
bandit12@bandit:/tmp/amr.Llr$ ls                                                                     
file1.bz2  test                                                                                      
bandit12@bandit:/tmp/amr.Llr$ bzip2 -d file1.bz2
bandit12@bandit:/tmp/amr.Llr$ ls                                                                     
file1  test                                                                                          
bandit12@bandit:/tmp/amr.Llr$ file file1                                                             
file1: gzip compressed data, was "data4.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 20480                                                        
bandit12@bandit:/tmp/amr.Llr$ mv file1 file1.gz && gzip -d file1.gz
bandit12@bandit:/tmp/amr.Llr$ ls                                                                     
file1  test                                                                                          
bandit12@bandit:/tmp/amr.Llr$ file file1
file1: POSIX tar archive (GNU)
bandit12@bandit:/tmp/amr.Llr$ tar -xf file1
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  file1  test
bandit12@bandit:/tmp/amr.Llr$ file file1
file1: POSIX tar archive (GNU)
bandit12@bandit:/tmp/amr.Llr$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/amr.Llr$ tar -xf data5.bin
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6.bin  file1  test
bandit12@bandit:/tmp/amr.Llr$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/amr.Llr$ man tar
bandit12@bandit:/tmp/amr.Llr$ tar -xf data5.bin
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6.bin  file1  test
bandit12@bandit:/tmp/amr.Llr$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/amr.Llr$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6.bz2  file1  test
bandit12@bandit:/tmp/amr.Llr$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6  file1  test
bandit12@bandit:/tmp/amr.Llr$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/amr.Llr$ tar -xf data6
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6  data8.bin  file1  test
bandit12@bandit:/tmp/amr.Llr$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/amr.Llr$ mv data8.bin data8.gz
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6  data8.gz  file1  test
bandit12@bandit:/tmp/amr.Llr$ gzip -d data8.gz
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6  data8  file1  test
bandit12@bandit:/tmp/amr.Llr$ file data8
data8: ASCII text
bandit12@bandit:/tmp/amr.Llr$ xxd -r data8 > file2
bandit12@bandit:/tmp/amr.Llr$ ls
data5.bin  data6  data8  file1  file2  test
bandit12@bandit:/tmp/amr.Llr$ cat file2
bandit12@bandit:/tmp/amr.Llr$ file file2
file2: empty
bandit12@bandit:/tmp/amr.Llr$ rm file2
bandit12@bandit:/tmp/amr.Llr$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

#
```
___

## 💡 Tips

# Continue this loop:

| **File Output**   | **What to Do**                                          |
|-------------------|---------------------------------------------------------|
| **gzip**          | `mv test file1.gz && gunzip file1.gz`                     |
| **bzip2**         | `mv test file1.bz2 && bunzip2 file1.bz2`                  |
| **tar archive**   | `tar -xf file1` (no renaming needed)                     |
| **ASCII text**    | `cat file1` and find the password inside                 |

# need to solve this level
```bash
# Recommended because it safe unique and make u a unuque temporary directory for your work
mktemp -d /tmp/amr.XXX
# copy file into this unique directordy and move to it
cp data.txt /tmp/amr.Llr
cd /tmp/amr.Llr
#rename a file , you can also change its suffix
mv data.txt test
# get more info about the file
file test
```
This file is a hex dump — a textual representation of binary data. It looks something like this:

00000000: 1f8b 0800 0000 0000 0003 ecbd ...

It was created using xxd, which turns binary data into this readable hex format.
🔄 xxd -r

    xxd is a tool to convert binary <--> hex.

    The -r flag tells it to reverse the process.

    So instead of making a hex dump, it takes a hex dump and rebuilds the original binary data
```bash
# xxd is a tool to convert binary <--> hex.
# The -r flag tells it to reverse the process.
xxd -r test >file1

#if File output showed gzip compressed data
mv file1.txt file1.gz && gzip -d file1.gz

#if File output showed bzip2 compressed data
mv file1.txt file2.bz2 && bzip2 -d file1.bz2


#if File output showed POSIX tar archive (GNU)
tar -xf data5.bin
```
___

## 📤 Output
```bash
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

