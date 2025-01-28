# Awesome Steganography
<p align="center">
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/15b81a67-2409-45ff-82a3-b5c825b81079" width=20% height=20% class="center"/> 
<p/>
  
## Awesome Tools for Steganography 🕵️
_Para o tutorial em português clique [aqui 🇧🇷](https://github.com/cristiancmoises/awesome-steganography/blob/main/Leia-me.md)_
# Table Of Contents

* [`Hidden with GUI`](#Stegoshare)
* [`Hidden with TCP`](#Steganoroute)
* [`Low file size`](#Snow)
* [`Popular Tool`](#Steghide)

# Stegoshare:
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/1734d34c-541d-4696-8f05-4fb8fc88690e" width=45% height="45%">

The program uses 3 least significant bits (LSB) for red and blue channels and 2 LSB for the green channel. Using lossless compression (PNG), StegoShare provides about 40% capacity (in the 250Mb images you can hide 100Mb file). Visually images looks that there are no any files embedded, human eye cannot detect the difference. 128-bit encryption makes detecting hidden file more difficult.
| Features                                                                                           |
|----------------------------------------------------------------------------------------------------|
|   Simple and easy to use                                                                           |
|   Works on any platform that runs Java                                                             |


> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%>  Running:

    apt install wget openjdk-8-jdk openjdk-8-jre
    wget http://downloads.sourceforge.net/stegoshare/StegoShare.jar
    java -jar StegoShare.jar

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> On Gentoo:

    emerge openjdk
    emerge jre
    wget http://downloads.sourceforge.net/stegoshare/StegoShare.jar
    java -jar StegoShare.jar

# Steganoroute:
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/6438b4f4-0c4b-4c65-99cb-f5e588617fb9" width=45% height="45%">

Is a tool to send steganographed text messages to another computer over the network. The receiver must make a traceroute to the sender using the mtr program (and pressing d once to switch the display mode to the continuous graph). This tool, the sender, creates several fake hops and makes them answer the ICMP packets (or not) to write the letters one by one on the mtr client screen.
| Features                                                                                           |
|----------------------------------------------------------------------------------------------------|
|    It can print upper and lower-case letters.                                                      |
|   It can print in normal or color-inverse mode.                                                    |
|   It can loop forever.                                                                             | 
|  It should work on your own localhost computer, on your LAN and over the Internet.                |
|   Is uses the Sinclair ZX Spectrum (1982) font.                                                    |
|   You can select the TTL value on demand and therefore 'move' the text up and down the mtr graph.  |
#### Warning! _You can filter the IP address that should receive the traceroute. If you don't filter it, every traceroute coming out of the server will mysteriously add fake hops to any destination!You can feel the sensation of being MITMed by the top intelligence organizations in the world by using the conspiracy mode!_

> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Running:
     
    apt install git mtr python3 python-scapy
    git clone https://github.com/stratosphereips/steganoroute.git
    cd ./steganoroute
    iptables -I INPUT -p icmp --icmp-type 8 -j DROP
    python3 ./steganoroute.py -i lo -m "MATRIX has You!" -l
    mtr -t yourlocalLANip
_*MTR command used to list the message_
> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> On Gentoo:

    emerge mtr 
    emerge python 
    emerge scapy
    git clone https://github.com/stratosphereips/steganoroute.git
    cd ./steganoroute
    iptables -I INPUT -p icmp --icmp-type 8 -j DROP
    python3 ./steganoroute.py -i lo -m "MATRIX has You!" -l
    mtr -t yourlocalLANip
_*MTR command used to list the message_

# Snow: 
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/27980d7d-37cb-47ee-a686-64e246f8fc8d" width=50% height=50% >

A lightweight tool that uses whitespace and tabs to hide information inside text files. Unlike other steganographic tools, snow does not rely on binary formats to encode secret data. This can be incredibly useful in cases where it is not possible to share large binary files.

| Features                                                                                           |
|----------------------------------------------------------------------------------------------------|
|    Produces small files                                                                            |
|    Output text can be used on any program that accepts plain text                                  |

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Running:     
     
    apt install stegsnow
    stegsnow -C -m "Encrypted Message Here" -p "angrypassword" infile outfile 
    stegsnow -C -p "angrypassword" outfile
    
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> On Gentoo:

    wget https://darkside.com.au/snow/snow.zip
    unzip snow.zip
    cd snow 
    make
    cp snow /bin/
    snow -C -m "Encrypted Message Here" -p "angrypassword" infile outfile
    snow -C -p "angrypassword" outfile

# Steghide   
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/43aa8701-9aa3-4fbf-ab64-44e1757d81aa" width=45% height=45%>

One of the most popular steganographic tools today. It is a simple command line program that encodes text inside images. Steghide works by creating a random list of bits inside your dummy file and inserts your secret data in between those bits.

| Features                                          |
|---------------------------------------------------|
|    Quick and easy to use                          |
|    Uses checksums to verify the integrity of data |

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Running:   

    apt install steghide
    cd steghide
    steghide embed -ef topsecretfile.txt -cf photo.jpg -sf photoX.jpg
    steghide extract –sf photoX.jpg

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> On Gentoo:

    wget https://ufpr.dl.sourceforge.net/project/steghide/steghide/0.5.1/steghide-0.5.1.zip
    cd steghide
    ./configure 
    make
    make check
    make install 
    steghide embed -ef topsecretfile.txt -cf photo.jpg -sf photoX.jpg
    steghide extract –sf photoX.jpg


## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=cristiancmoises/torando&type=Date)](https://star-history.com/#cristiancmoises/awesome-steganography&Date)
