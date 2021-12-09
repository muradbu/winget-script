# winget-script
A list of programs I might install.

## Installing Winget on Windows 10 LTSC (NO AUTO UPDATES):
From the latest release download the .msixbundle and .xml file:
https://github.com/microsoft/winget-cli/releases

> Make sure you have the [VC++ v14 Desktop Framework Package](https://docs.microsoft.com/en-gb/troubleshoot/cpp/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) installed as well before you do the above!

Open PowerShell and run (replace file paths to correct locations):

`Add-AppxProvisionedPackage -Online -PackagePath PATH TO MSIXBUNDLE -LicensePath PATH TO XML -Verbose`

Wait for install to finish and you're done.
