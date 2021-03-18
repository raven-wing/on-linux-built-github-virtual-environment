# How to create github virtual environment on Linux

##1. Clone repo with virtual environment
https://github.com/actions/virtual-environments

##2. Install packer
https://www.packer.io/downloads
unzip packer**

###2.1 Add packer to PATH
EXPORT PATH="<path-to-dir-with-packer>:$PATH"

##3. Install power shell
Depending on your distro chose your way:
https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux

##4. Install azure deps in powershell
pwsh
Install-Module -Name Az -AllowClobber

##5. Run Generation of VHD
pwsh
Import-Module .\helpers\GenerateResourcesAndImage.ps1
GenerateResourcesAndImage -SubscriptionId {sub-guid} -ResourceGroupName {rg-name} -ImageGenerationRepositoryRoot "$pwd" -ImageType {image-type} -AzureLocation {location} -GithubFeedToken 'REDACTED'

image-type is one of github virtual environments (same are used on Azure DevOps Microsoft-hosted agents).
