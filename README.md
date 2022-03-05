# winget-script
A list of programs I might install.

## Installing Winget on Windows 10 LTSC (IoT) manually:

> ⚠ Manual installation does not receive auto updates, but is the only option without installing Windows Store on LTSC ⚠

* Make sure you have the correct [VC++ v14 Desktop Framework Package](https://docs.microsoft.com/en-gb/troubleshoot/cpp/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) for your architecture installed.
* From the latest release download the .msixbundle and .xml file:
https://github.com/microsoft/winget-cli/releases

> ⚠ Winget v1.2.10271 introduced a new dependency for Microsoft.UI.Xaml which you have to install manually, otherwise Winget will not work! Refer to this [comment](https://github.com/microsoft/winget-cli/issues/1861#issuecomment-1021240355) for instructions. ⚠

Open an elevated PowerShell prompt and run (replace file paths to correct locations):

`Add-AppxProvisionedPackage -Online -PackagePath PATH TO MSIXBUNDLE -LicensePath PATH TO XML -Verbose`

Wait for install to finish and you're done.
