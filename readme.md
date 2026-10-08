Node.js Installation on Windows

Follow these steps to install Node.js v24.21.0 on Windows using Chocolatey.

Prerequisites
Windows 10 or Windows 11
PowerShell
Administrator access
1. Open PowerShell as Administrator

Search for PowerShell in the Windows Start menu.

Right-click PowerShell and select Run as administrator.

2. Set PowerShell Execution Policy

Run:

Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned


If PowerShell asks for confirmation, enter:

Y

3. Check Node.js and npm

Before installing Node.js, you can check whether they are already installed:

node -v
npm -v


If they are not installed, continue with the next steps.

4. Install Chocolatey

Run the following commands in Administrator PowerShell:

Set-ExecutionPolicy Bypass -Scope Process -Force

[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072

iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

Note: Only run the Chocolatey installation once. Do not run multiple Chocolatey installation commands.
5. Restart PowerShell

Close PowerShell completely.

Open PowerShell as Administrator again.

Verify that Chocolatey was installed successfully:

choco -v


You should see a Chocolatey version number.

6. Install Node.js 24.21.0

Run:

choco install nodejs --version="24.21.0"


If Chocolatey asks for confirmation, enter:

Y

7. Restart PowerShell

Close PowerShell and open it again.

This ensures the updated environment variables and PATH are loaded.

8. Verify Node.js Installation

Run:

node -v


Expected output:

v24.21.0


Then check npm:

npm -v


You should see an npm version number.

Installation Complete

If the following commands return version numbers, Node.js and npm are installed successfully:

node -v
npm -v


You can now start installing your project's dependencies:

npm install

Troubleshooting
choco is not recognized

Close PowerShell and open a new Administrator PowerShell window.

Then run:

choco -v

node is not recognized

Restart PowerShell after installing Node.js:

node -v


If it still doesn't work, restart Windows and try again.

Check where Node.js is installed

Run:

where.exe node

Check Chocolatey installation

Run:

choco -v

Quick Installation

For experienced users, the essential commands are:

Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

Set-ExecutionPolicy Bypass -Scope Process -Force
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

choco install nodejs --version="24.21.0"

node -v
npm -v
