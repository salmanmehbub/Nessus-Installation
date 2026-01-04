<h1>Install Nessus on Kali Linux</h1>

<p>
Vulnerability scanning is an essential part of modern cybersecurity.
Nessus is a popular vulnerability scanner used by security professionals
to identify vulnerabilities across systems, networks, and applications.
It supports Windows, macOS, and Linux.
</p>

<p>
This guide explains how to download and install Nessus on Kali Linux step by step.
</p>

<hr>

<h2>What Is Nessus</h2>

<p>
Nessus is a vulnerability scanner developed by Tenable Inc.
It is available in two main versions:
</p>

<ul>
  <li>Nessus Professional (paid)</li>
  <li>Nessus Essentials (free, limited to 16 IP addresses per scanner)</li>
</ul>

<p>
Nessus provides features such as vulnerability assessment, network scanning,
web scanning, asset discovery, and more, helping security professionals
proactively identify and mitigate vulnerabilities.
</p>

<hr>

<h2>How to Install Nessus on Kali Linux</h2>

<p>
Nessus does not come preinstalled on Kali Linux, but installation is straightforward.
</p>

<hr>

<h3>1. Download Nessus</h3>

<p>
Download the Nessus package for Debian from the official Nessus website:
</p>

<p>
<a href="https://www.tenable.com/downloads/nessus">
https://www.tenable.com/downloads/nessus
</a>
</p>

<p>
Make sure the platform is set to <b>Linux – Debian – amd64</b>.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_download.png" width="800">
</p>

<hr>

<h3>2. Nessus Installation</h3>

<p>
Once the download is complete, open a terminal and navigate to the directory
where the file was downloaded (for example, Downloads).
</p>

<p>
Install the <code>.deb</code> package using the following command:
</p>

<pre>
sudo dpkg -i Nessus-*.deb
</pre>

<p>
This command installs Nessus on your system.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_install.png" width="800">
</p>

<hr>

<h3>3. Start the Nessus Service</h3>

<p>
Start the Nessus daemon using:
</p>

<pre>
sudo systemctl start nessusd
</pre>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_start.png" width="800">
</p>

<p><b>Note:</b></p>

<p>
If you have previously used Nessus and encounter a corrupted database error,
stop the service, remove the Nessus directory, download the latest version,
and reinstall.
</p>

<pre>
sudo systemctl stop nessusd
sudo rm -rf /opt/nessus
</pre>

<hr>

<h3>4. Access the Web Interface</h3>

<p>
After starting the service, go to the following URL in your web browser:
</p>

<pre>
https://kali:8834/
</pre>

<p>
A security warning will appear. Click <b>Advanced</b>, then select
<b>Accept the Risk and Continue</b>.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_ignore_warning.png" width="800">
</p>

<p><b>Hint:</b></p>

<p>
The word <b>kali</b> in the URL refers to your system hostname.
If your hostname is different, replace it accordingly.
</p>

<hr>

<h3>5. Choose Nessus Product</h3>

<p>
Next, you’ll be presented with a Nessus welcome screen.
Click on <b>Continue</b> to move forward.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_choose_product.png" style="width:50%;>
</p>

<p>
Select the Nessus product you want to use.
For the free version, choose <b>Nessus Essentials</b>.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_register.png" width="800">
</p>

<hr>

<h3>6. Register and Activate</h3>

<p>
On the next screen, provide your name and email address and click on
<b>Register</b> to continue.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_register_user.png" width="800">
</p>

<p>
On the next screen, you’ll be presented with an activation code.
Copy and save this code somewhere for future reference.
Click on <b>Continue</b>.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_activation.png" width="800">
</p>

<p>
On the next screen, you must create a Nessus administrator user account,
which will be used to log in to Nessus.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_administrator_account.png" width="800">
</p>

<hr>

<h3>7. Plugin Download</h3>

<p>
Nessus will begin downloading plugins and required files.
This process may take some time.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_plugin_setup.png" width="800">
</p>

<p>
Once completed, you will be redirected to the Nessus dashboard.
</p>

<p>
From here, Nessus will start configuring the plugins, which will take a while
to complete. So grab a cup of coffee and relax while it works its magic.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_plugin_setup_01.png" width="800">
</p>

<p>
Once finished, you’re ready to use Nessus.
</p>

<hr>

<h2>Starting Nessus</h2>

<p>
To start Nessus, use the command:
</p>

<pre>
sudo systemctl start nessusd.service
</pre>

<p>
Then open the following URL in your browser:
</p>

<pre>
https://kali:8834/
</pre>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_login.png" width="800">
</p>

<p>
Once you’re logged in, you can begin to use Nessus.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/salmanmehbub/Nessus-Installation/refs/heads/main/images/nessus_scan.png" width="800">
</p>

<p>
Once you are finished working with Nessus, you can stop the service
with the command:
</p>

<pre>
sudo systemctl stop nessusd.service
</pre>
