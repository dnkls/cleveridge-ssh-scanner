cleveridge-ssh-scanner
======================

The Cleveridge SSH Scanner is a SSH Brute Force tool written in python. The tool tries to get access to machines (IPv4) on the SSH port (22). When the machines is accesable on port 22, the tool brute forces the ssh login with the most common default user names and passwords.

The tool offers you the options to attack
- one IP
- a range of IP's (e.g. 192.168.0.1-25)
- IP's listed in a file

!!! The tool works only in combination Tor, Proxychains and Python !!!

Tested
++++++

At this moment the Cleveridge SSH Scanner is only tested in a Linux Kali environment with Python 2.7, Proxychains (http://proxychains.sourceforge.net/) and Tor (https://www.torproject.org/) installed.

*How to use in Linux
1. Be sure you have tor and proxychains installed.
if you have problems installing these programs there is enough documentation available online.

2. Edit your proxychains configuration file:
Most of the time you will find this file at /etc/proxychains.conf
What to change...
1st : uncomment 'dynamic_chain' (remove the # in front of it)
2nd : comment 'strict_chain' and 'ramdom chain' (add a # in front of it)
3th : Below [ProxyList], add your Tor Listener settings, this could be
      socks4 127.0.0.1 9050
More info : http://www.shellhacks.com/en/Anonymous-Port-Scanning-Nmap-Tor-ProxyChains

3. Download the Cleveridge SSH Scanner files into a directory of your choise and chmod it so you are allowed to execute it.

4. In Terminal, go to the Cleveridge SSH Scanner directory and execute:
    service tor start
    proxychains ./cl_ssh_scan.py
