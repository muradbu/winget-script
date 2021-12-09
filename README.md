# winget-script
A list of programs I might install.

## Installing Winget on Windows 10 LTSC (NO AUTO UPDATES):
From the latest release download the .msixbundle and .xml file:
https://github.com/microsoft/winget-cli/releases

Open PowerShell and run (replace file paths to correct locations):

`Add-AppxProvisionedPackage -Online -PackagePath PATH TO MSIXBUNDLE -LicensePath PATH TO XML -Verbose`

Wait for install to finish and you're done.
