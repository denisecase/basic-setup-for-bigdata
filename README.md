# Basic Setup for Big Data

> Download, install, update, and manage basic Big Data tools on Windows.

- [Webpage](https://denisecase.github.io/basic-setup-for-bigdata/)
- [Source](https://github.com/denisecase/basic-setup-for-bigdata)

## Recommended Prerequisites

- [Windows Setup for Developers](https://github.com/denisecase/windows-setup)
- [Windows File Management](https://github.com/denisecase/windows-file-management)
- Add 'Open PowerShell here as Administrator' to your Windows folder context (right-click) menu. If you don't have this yet, see [the ten forumns option](https://www.tenforums.com/tutorials/60177-add-open-powershell-window-here-administrator-windows-10-a.html).

## Read about Windows Software Automation

Installing software on Windows by typing simple commands with [Chocolatey](https://chocolatey.org/), a software automation tool for Windows.

## Install Chocolatey

Install Chocolatey, the Windows Package Manager from <https://chocolatey.org/> by following the directions on the website.

## Basic chocolatey

- Chocolatey makes it easy to keep your software up-to-date.
- It's safe to install software you already have (e.g., Chrome).
- The -y flag is optional and automatically answers 'yes' to install questions.
- Use 'refreshenv' to update ennviroment variables as needed.
- You can combine multiple packages into a single 'choco install' command - just separate each package with a space.
- See available packages at <https://chocolatey.org/packages>.
- See local software at <C:\ProgramData\chocolatey>.
- See local install log at <C:\ProgramData\chocolatey\logs\chocolatey.log>.
- See also <C:\tools>

## Install Common Big Data Tools using Chocolatey

No need to reinstall programs you already have. Doing so can add them to your path multiple times. 

If your path has multiple JAVA entries, Java will simiply fail. Monitor your path variables and know where your software installs. 

```PowerShell
choco install miniconda3 -y
choco install openjdk -y
choco install 7zip -y
choco install curl -y
choco install git -y
choco install gradle -y
choco install maven -y
choco install notepadplusplus -y
choco install putty -y
choco install tortoisegit -y
choco install vscode -y
choco install wget -y
refreshenv
choco list -local
```

### Verify

After installing, even if you run refreshenv, it can be a good idea to close that PowerShell window and reopen a new PowerShell window. (This is especially needed to complete the OpenJDK installation. 

In a new PowerShell window, run:

```PowerShell
choco list -local
```

Inspect software. The default location is 'C:\ProgramData\chocolatey'.

Inspect Windows environment variables. Hit Win key and type env. Select "Edit System Environment Variables". From System Properties window Advanced tab, click "Environment Variables".

```PowerShell
git --version
java --version
python --version

```

**Troubleshooting**: If a version command does not work, be sure you have closed your PowerShell window, and opened a new PowerShell window. You may also try restarting your machine. 

### Upgrade Periodically

```Powershell
choco upgrade chocolatey -y
choco upgrade all -y
refreshenv
```

## Install Without Chocolatey

Alternatively, each tool can be installed in the traditional manner. Just go to the website for the software and follow instructions to download, install, and configure tools using provided installers.

## Activating Python Environment

- [Managing Environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
- [Activating Environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#activating-an-environment)

You may receive a warning message if you have not activated your Conda environment:

```
Warning: 
This Python interpreter is in a conda environment, but the environment has
not been activated. Libraries may fail to load. To activate this environment
please see https://conda.io/activation.
```

If you receive this warning, you need to activate your environment. To do so on Windows, run: `c:\Anaconda3\Scripts\activate base` in Anaconda Prompt.

## Terms

- automation tools
- web browser
- Chocolatey
- editor
- environment variables
- package manager
- upgrade (get the latest version)
- Windows (operating system)
