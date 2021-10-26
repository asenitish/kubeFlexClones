This script creates a clone of a volume and mounts the clone in the namespace.

  Instructions on installing Powershell Core and running the script  
    Update the list of packages
     sudo apt-get update
    Install pre-requisite packages.
     sudo apt-get install -y wget apt-transport-https software-properties-common
    Download the Microsoft repository GPG keys
     wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
    Register the Microsoft repository GPG keys
     sudo dpkg -i packages-microsoft-prod.deb
    Update the list of packages after we added packages.microsoft.com
     sudo apt-get update
    Install PowerShell
     sudo apt-get install -y powershell
    Start PowerShell
     pwsh
    Verify the version of PowerShell
     $psversiontable
    Install NetApp Powershell Module
     Install-Module NetApp.ONTAP (select [A] Yes tl All)
    Copy the Script on to Linux Host and change permissions
     chmod +x <script-name>
    exit powershell and run script-name
     exit
     pwsh Set-VolumeClones-v1.2.ps1

  Update the following variables unde "Declarations" section
  $svmName -  Name of the storage SVM where Trident volumes are hosted
  $svmMgmtLif = management IP address of the storage SVM where user connects and authenticates to run NetApp storage commands

  Keep a note of "SVM management" username and password to connect and authenticate to run NetApp storage
