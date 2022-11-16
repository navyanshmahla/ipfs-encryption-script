# Python script for encrypting private data before uploading it to IPFS

This script takes a file or directroy as input, uses tar if a directory and GPG AES256 symmetric encryption with the password you provide and adds it to IPFS and returns the IPFS hash. 

I use this on a Macbook Air with GPG.

## USAGE:
### Add Single File:
```
./ipfs-add-from-encrypted.py -i test.txt -n Secrets.Out
File encrypted and added to IPFS with this hash QmYjK5jHgYSyeyKZqDZyLCzrziphB18wuM93mXtySEryD1
```
### Add Directory:
```
./ipfs-add-from-encrypted.py -i /home/testing/stuff -n Stuff.Out
File encrypted and added to IPFS with this hash QmYjK5jHgYSyeyKZqDZyLCzrziphB18wuM93mXtySEryD1
```

## Help:
```
usage: ipfs-add-from-encrypted.py [-h] -i INPUT -n NAME

Encrypt file/directory and add it to IPFS

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        File.txt or Directory
  -n NAME, --name NAME  Set encrypted output filename
```
A note from me: Navyansh
This IPFS script works all fine apart from the fact that the decryption keys can be easily accessible even to the wallet with whom you don't want to share your data. Once even a single person (that you've allowed to get the decryption keys to access the data) has the keys, can share it to anyone and even that person can access them. In this case, it requires some more modifications regarding how we use this script. We must add feeatures of user consent protocol where a particular person requests for the file and then you accept that request to allow him to see the data. This is something that I plan to achieve.
