# What's this?

In this repo I maintain a script ([winget.ps1](https://github.com/muradbuyukasik/winget-script/blob/main/winget.ps1)) of software I may install on a fresh installation of Windows 10 using Winget, and an installation guide for Winget on Windows 10 LTSC which can be found below.

# Installing Winget on Windows 10 LTSC (IoT) manually

> ⚠ Manual installation does not receive auto updates, but is the only option without installing Windows Store on LTSC ⚠

## Installing Dependencies

* Open an elevated (administrator) PowerShell prompt and keep it open throughout this guide.

### VC++ v14 Desktop Framework Package

1. Download the correct [VC++ v14 Desktop Framework Package](https://docs.microsoft.com/en-gb/troubleshoot/cpp/c-runtime-packages-desktop-bridge#how-to-install-and-update-desktop-framework-packages) for your architecture.
2. Install with: `Add-AppxPackage -Path "PATH TO FILE"`

### Microsoft.UI.Xaml.2.7

Winget v1.2.10271 introduced a new dependency for Microsoft.UI.Xaml.2.7 which you have to install manually. The solution to install this on LTSC is not pretty, but it works.

1. Download the [Nuget package](https://www.nuget.org/packages/Microsoft.UI.Xaml/) manually by clicking "Download package" on the right hand side under the "About" section.
2. Change the file extension from `.nuget` to `.zip` and open it with any archiving program.
3. Within the archive navigate to `tools\AppX\[YOUR ARCHITECTURE]\Release` and extract `Microsoft.UI.XAML.2.7.appx`.
4. Install with: `Add-AppxPackage -Path "PATH TO FILE"`

[#1861](https://github.com/microsoft/winget-cli/issues/1861)

## Installing Winget

0. Make sure all dependencies are installed before doing this!
1. From the latest release download the .msixbundle install- and .xml license file:
https://github.com/microsoft/winget-cli/releases
2. Install with:
`Add-AppxProvisionedPackage -Online -PackagePath "PATH TO MSIXBUNDLE" -LicensePath "PATH TO XML" -Verbose`
3. Wait for the install to finish and you're done. You may need to restart the terminal, or reboot your pc.
4. Verify that the installation succeeded by running `winget` in PowerShell. If no errors occur then you're done!
