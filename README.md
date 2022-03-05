# winget-script
A list of programs I might install.

## Installing Winget on Windows 10 LTSC (IoT) manually:

> ⚠ Manual installation does not receive auto updates, but is the only option without installing Windows Store on LTSC ⚠

1. Make sure you have the correct [VC++ v14 Desktop Framework Package](https://docs.microsoft.com/en-gb/troubleshoot/cpp/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) for your architecture installed.
1. Winget v1.2.10271 introduced a new dependency for Microsoft.UI.Xaml.2.7 which you have to install manually, otherwise Winget will not work! Refer to this [comment](https://github.com/microsoft/winget-cli/issues/1861#issuecomment-1021240355) for instructions.
1. From the latest release download the .msixbundle install- and .xml license file:
https://github.com/microsoft/winget-cli/releases
1. Open an elevated PowerShell prompt and run the following command, replacing the text between the quotation marks with the correct filepath:

`Add-AppxProvisionedPackage -Online -PackagePath "PATH TO MSIXBUNDLE" -LicensePath "PATH TO XML" -Verbose`

Wait for the install to finish and you're done. You may need to restart the terminal, or reboot your pc.
