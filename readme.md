Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
npm -v
open poweshell as admin...

Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072

iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

restart the powershell

choco install nodejs --version="24.21.0"

restart the powershell

node -v
