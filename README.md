# brut3k1t
Server-side brute-force module.

# NOTE: FACEBOOK BRUTEFORCE IS FINALLY COMPLETE! YAY!!! TIME FOR TESTING!

## 1. Introduction

__brut3k1t__ is a server-side bruteforce module that supports dictionary attacks for several protocols.
The current protocols that are complete and in support are:

    ssh
    ftp
    smtp
    XMPP
    instagram
    facebook
    twitter
    skype



## 2. Installation

Installation is simple. __brut3k1t__ requires several dependencies, which will all be installed by running the `installer.py` executable.

* __argparse__ - utilized for parsing command line arguments
* __paramiko__ - utilized for working with SSH connections and authentication
* __ftplib__ - utilized for working with FTP connections and authentication
* __smtplib__ - utilized for working with SMTP (email) connections and authentication
* ~~ __fbchat__ - utilized for connecting with Facebook ~~
* __selenium__ - utilized for web scraping, which is used with Instagram (and later Twitter)
* __xmppy__ - utiized for XMPP connections
* __SkPy__ - utilized for Skype connections


Downloading is simple. Simply `git clone`.

    git clone https://github.com/ex0dus-0x/brut3k1t

Change to directory:

    cd /path/to/brut3k1t

Run the Installer file (as root)

    sudo python installer.py

## 3. Troubleshooting (troubleshooting guide coming soon!)

If you received any errors about dependencies, try to manually install the requirements. Here's how:

1. Installing dependencies:

    sudo apt-get install build-essential libssl-dev libffi-dev python-dev

Make sure `firefox` is installed (default for most OS). If your operating system permits, install `firefoxdriver` as well.

2. Installing `pip` modules

    sudo pip install -r requirements.txt

while you are in the `brut3k1t/` directory.

If you are having any trouble installing `pip` dependencies, you can try using `easy_install` as an alternative


## 4. Usage

Utilizing __brut3k1t__ is a little more complicated than just running a Python file.

Typing `python brut3k1t -h` shows the help menu:

    usage: brut3k1t.py [-h] [-s SERVICE] [-u USERNAME] [-w PASSWORD] [-a ADDRESS]
                   [-p PORT] [-d DELAY]

    Server-side bruteforce module written in Python

    optional arguments:
    -h, --help            show this help message and exit
    -a ADDRESS, --address ADDRESS
                        Provide host address for specified service. Required
                        for certain protocols
    -p PORT, --port PORT  Provide port for host address for specified service.
                        If not specified, will be automatically set
    -d DELAY, --delay DELAY
                        Provide the number of seconds the program delays as
                        each password is tried

    required arguments:
    -s SERVICE, --service SERVICE
                        Provide a service being attacked. Several protocols
                        and services are supported
    -u USERNAME, --username USERNAME
                        Provide a valid username for service/protocol being
                        executed
    -w PASSWORD, --wordlist PASSWORD
                        Provide a wordlist or directory to a wordlist

### 5. Examples of usage:

Cracking SSH server running on `192.168.1.3` using `root` and `wordlist.txt` as a wordlist.

    python brut3k1t.py -s ssh -a 192.168.1.3 -u root -w wordlist.txt

The program will automatically set the port to 22, but if it is different, specify with `-p` flag.

Cracking email `test@gmail.com` with `wordlist.txt` on port `25` with a 3 second delay. For email it is necessary to use the SMTP server's address. For e.g Gmail = `smtp.gmail.com`. You can research this using Google.

    python brut3k1t.py -s smtp -a smtp.gmail.com -u test@gmail.com -w wordlist.txt -p 25 -d 3

Cracking XMPP `test@creep.im` with `wordlist.txt` on default port `5222`. XMPP also is similar to SMTP, whereas you will need to provide the address of the XMPP server, in this case `creep.im`.

    python brut3k1t.py -s xmpp -a creep.im -u test -w wordlist.txt

Cracking Facebook requires either the username (preferable, in this case, `test`), email, phone number, or even ID.

    python brut3k1t.py -s facebook -u test -w wordlist.txt

Cracking Instagram with username `test` with wordlist `wordlist.txt` and a 5 second delay

     python brut3k1t.py -s instagram -u test -w wordlist.txt -d 5

 Cracking Twitter with username `test` with wordlist `wordlist.txt`

     python brut3k1t.py -s twitter -u test -w wordlist.txt


## 6. KEY NOTES TO REMEMBER

 * If you do not supply the port `-p` flag, the default port for that service will be used. You do not need to provide it for Facebook and Instagram, since they are um... web-based. :)

 * If you do not supply the delay `-d` flag, the default delay in seconds will be 1.

 * Remember, use the SMTP server address and XMPP server address for the address `-a` flag, when cracking SMTP and XMPP, respectively.

 * Make sure the wordlist and its directory is specified. If it is in `/usr/local/wordlists/wordlist.txt` specify that for the wordlist `-w` flag.

 * Remember that some protocols are not based on their default port. A FTP server will not necessarily always be on port `21`. Please keep that in mind.

 * Use this for educational and ethical hacking purposes, as well as the sake of learning code and security-oriented practices. __No script kiddies!__

Thanks for trying out brut3k1t! I've been pretty lazy in terms of development and keeping this code updated and in track, so please __PLEASE__ report any sort of errors that arise (including false-positives).

## 7. TODO

* Proxy support
* Randomized user agents
* GUI or web-based GUI
* Telnet and HTTP attack vectors
* Using Skype login + selenium rather than `Skpy` module.


# Much more features to come!
