1.nginx is running with what additional software designed to serve web applications?
First what we need to do is turn on nmap, and check the resul:

![obraz](https://github.com/Anogota/Precious-/assets/143951834/e53cd72a-2db0-46ee-b73e-a5e05fe1ffd2)

But on the scan we don't have any special, we need to go on this website and check what's is there, after small recon i use wapalyzer and i found it, this a Phusion Passenger 

2.Which HTTP response header reveals the underlying scripting Language of the web application?
Turn on the burp and we need intercept traffic, i found it the HTTP response header is X-Runtime, and the script language is ruby.

![obraz](https://github.com/Anogota/Precious-/assets/143951834/1f82406f-ae84-4b96-af8d-c960c1333e5e)

3.Which Ruby library are the PDF documents generated with?
First create ur own server with help python -m http.server, than write here ur ip and port
and you got a pdf with random characters

![obraz](https://github.com/Anogota/Precious-/assets/143951834/87879b44-f256-4fa4-be8a-516f429865a2)
 
now we find to figure it out what kind of libery is this, open ur terminal and use exiftool on this .pdf
We can see here ruby library 

![obraz](https://github.com/Anogota/Precious-/assets/143951834/02001b72-4861-4c9f-b680-e7eed19704ca)

4.Which 2022 CVE applies to that specific version of pdfkit?
Now we need use google to find CVE from 2022 for pdfkit, let's go :P
After few secend i foun this exploit, this is a RCE
"RCE vulnerabilities allow an attacker to execute arbitrary code on a remote device. An attacker can achieve RCE in a few different ways, including"

![obraz](https://github.com/Anogota/Precious-/assets/143951834/0b130a51-73f0-4b42-9765-0ef6b92070d6)

5.Which directory located in the running user's home directory is used by Bundler to store configuration files?
Now we need to get in i found how to do it, we can do it with reverse shell python
here is the website with this reverse shell, here we can every shell we want
And also here is the articule to get a RCE: https://vk9-sec.com/ruby-pdfkit-command-execution-rce-cve-2022-25765/
https://www.revshells.com/
And we got a shell

![obraz](https://github.com/Anogota/Precious-/assets/143951834/38bc61b1-bfb2-4e63-a25b-9d8d1be07b96)

