<h1 align="center">Install Nessus on Kali Linux</h1>

<p align="center">
Step-by-step guide to install and configure Nessus Vulnerability Scanner on Kali Linux.
</p>

<hr>

<h2>🔍 What Is Nessus</h2>

<p>
Nessus is a widely used vulnerability scanner developed by
<strong>:contentReference[oaicite:0]{index=0}</strong>.
It helps security professionals identify vulnerabilities, misconfigurations,
and security issues in systems, networks, and applications.
</p>

<p>
Nessus is <strong>proprietary software</strong> and is available in:
</p>

<ul>
  <li><b>Nessus Essentials</b> (Free – limited to 16 IPs)</li>
  <li><b>Nessus Professional</b> (Paid)</li>
</ul>

<hr>

<h2>⚙️ Prerequisites</h2>

<ul>
  <li>Kali Linux (latest version recommended)</li>
  <li>Root or <code>sudo</code> access</li>
  <li>Internet connection</li>
  <li>Web browser</li>
</ul>

<hr>

<h2>📥 Step 1 — Download Nessus</h2>

<p>
Visit the official Nessus download page and select:
</p>

<ul>
  <li><b>Platform:</b> Linux</li>
  <li><b>Distribution:</b> Debian / amd64</li>
</ul>

<p>
After downloading, open a terminal and navigate to the download directory:
</p>

<pre>
cd ~/Downloads
</pre>

<hr>

<h2>📦 Step 2 — Install Nessus</h2>

<p>
Install the downloaded package using <code>dpkg</code>:
</p>

<pre>
sudo dpkg -i Nessus-*.deb
</pre>

<p>
This installs Nessus in <code>/opt/nessus</code>.
</p>

<hr>

<h2>🚀 Step 3 — Start Nessus Service</h2>

<p>
Start the Nessus daemon:
</p>

<pre>
sudo systemctl start nessusd
</pre>

<p>
(Optional) Enable Nessus at boot:
</p>

<pre>
sudo systemctl enable nessusd
</pre>

<p>
Check service status:
</p>

<pre>
sudo systemctl status nessusd
</pre>

<hr>

<h2>🌐 Step 4 — Access Nessus Web Interface</h2>

<p>
Open your browser and visit:
</p>

<pre>
https://localhost:8834/
</pre>

<p>
You may see an SSL warning — click
<b>Advanced → Accept the Risk and Continue</b>.
</p>

<p>
<b>Note:</b> If accessing remotely, replace <code>localhost</code> with your system IP.
</p>

<hr>

<h2>🔑 Step 5 — Initial Configuration</h2>

<ol>
  <li>Select <b>Nessus Essentials</b> (free version) or another edition</li>
  <li>Register with your name and email to receive an activation code</li>
  <li>Paste the activation code into the setup page</li>
  <li>Create an admin username and password</li>
  <li>Click <b>Skip</b> if prompted to re-register</li>
</ol>

<hr>

<h2>📥 Step 6 — Plugin Download</h2>

<p>
Nessus will now download plugins and vulnerability databases.
This may take several minutes depending on your connection.
</p>

<p>
Once complete, you will be redirected to the Nessus dashboard.
</p>

<hr>

<h2>🧭 Nessus Dashboard Overview</h2>

<ul>
  <li><b>My Scans</b> – Scans created by the current user</li>
  <li><b>All Scans</b> – Scans created by all users</li>
  <li><b>Policies</b> – Scan configurations and templates</li>
  <li><b>Plugins</b> – Vulnerability detection modules</li>
  <li><b>Scanners</b> – Hosts responsible for executing scans</li>
  <li><b>Trash</b> – Deleted scan templates</li>
</ul>

<p>
You can now start creating scans and exploring Nessus features.
</p>

<hr>

<h2>⚠️ Troubleshooting</h2>

<ul>
  <li>
    If Nessus fails to start, reinstall the package using the latest version.
  </li>
  <li>
    <b>Clean reinstall (only if required):</b>
    <pre>
sudo systemctl stop nessusd
sudo rm -rf /opt/nessus
    </pre>
  </li>
  <li>
    Ensure port <b>8834</b> is not blocked by firewall rules.
  </li>
</ul>

<hr>

<p align="center">
✅ Nessus is now successfully installed and ready to use on Kali Linux.
</p>
