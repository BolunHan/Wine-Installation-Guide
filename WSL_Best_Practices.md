# install wsl

open PowerShell with admin privilege

```PowerShell
wsl --install
```

and wait until installation complete

# setup windows ssh server

open Setting -> Apps -> Optional features -> Add an optional feature and install OpenSSH Server

# set auto start for sshd

```PowerShell
# Start the sshd service
Start-Service sshd

# OPTIONAL but recommended:
Set-Service -Name sshd -StartupType 'Automatic'

# Confirm the Firewall rule is configured. It should be created automatically by setup. Run the following to verify
if (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
} else {
    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
}
```

# make ssh login to wsl instead of cmd

Configuring the default ssh shell is done in the Windows registry by adding the full path to the shell executable to `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\OpenSSH` in the string value `DefaultShell`.

Set default shell to bash.exe will start and open a wsl session automatically

```PowerShell
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\WINDOWS\System32\bash.exe" -PropertyType String -Force
```
