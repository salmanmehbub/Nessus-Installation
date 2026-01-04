Install Nessus on Kali Linux
Vulnerability scanning is an essential part of modern cybersecurity. Nessus is a popular vulnerability scanner used by security professionals to identify vulnerabilities across systems, networks, and applications. It supports Windows, macOS, and Linux.
This guide explains how to download and install Nessus on Kali Linux step by step.

What Is Nessus
Nessus is a vulnerability scanner developed by Tenable Inc. It is available in two main versions:
•	Nessus Professional (paid)
•	Nessus Essentials (free, limited to 16 IP addresses per scanner)
Nessus provides features such as vulnerability assessment, network scanning, web scanning, asset discovery, and more, helping security professionals proactively identify and mitigate vulnerabilities.

How to Install Nessus on Kali Linux
Nessus does not come preinstalled on Kali Linux, but installation is straightforward.

1. Download Nessus
Download the Nessus package for Debian from the official Nessus website. https://www.tenable.com/downloads/nessus 
Make sure the platform is set to Linux – Debian – amd64.
 


2. Nessus Installation
Once the download is complete, open a terminal and navigate to the directory where the file was downloaded (for example, Downloads). Install the .deb package using the following command:

sudo dpkg -i Nessus-*.deb

This command installs Nessus on your system.
 

3. Start the Nessus Service
Start the Nessus daemon using:
sudo systemctl start nessusd

 

Note:
If you have previously used Nessus and encounter a corrupted database error, stop the service, remove the Nessus directory, download the latest version, and reinstall.

sudo systemctl stop nessusd
sudo rm -rf /opt/nessus

4. Access the Web Interface
After starting the service, go to https://kali:8834/ in your web browser to access and configure Nessus.
A security warning will appear. Click Advanced, then select Accept the Risk and Continue.
 


Hint:
The word kali in the URL refers to your system hostname. If your hostname is different, replace it accordingly.

5. Choose Nessus Product
Next, you’ll be presented with a Nessus welcome screen. Click on “Continue” to move forward. 

 

Select the Nessus product you want to use. For the free version, choose Nessus Essentials. 
Select “Register for Nessus Essentials” on the following screen and click on “Continue.”
 

6. Register and Activate
On the next screen, provide your name and email address and click on “Register” to continue.

 

On the next screen, you’ll be presented with an activation code. Copy and save this code somewhere for future reference. Click on “Continue.”
 

On the next screen, you must create a Nessus administrator user account, which will be used to login to Nessus.

 

7. Plugin Download
Nessus will begin downloading plugins and required files. This process may take some time. Once completed, you will be redirected to the Nessus dashboard.
 

Once finished, you’ll be taken to the Nessus dashboard.
From here, Nessus will start configuring the plugins, which will take a while to complete. So grab a cup of coffee and relax while it works its magic.

 
Once finished, you’re ready to use Nessus.

Starting Nessus
To start Nessus, use the command 
sudo systemctl start nessusd.service 
and then open https://kali:8834/ in your browser.
 

Once you’re logged in, you can begin to use Nessus.

 

Once you are finished working with Nessus, you can stop the service with the command: 
sudo systemctl stop nessusd.service.


