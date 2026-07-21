# Introduction
This note will contains practical skills for ethical hacking.

# Reference
- [Overview of Kali Linux](#overview-of-kali-linux)

- [Credits](#credits)


# Overview of Kali Linux
[GO BACK TO REFERENCE](#reference)

### Setting up VirtualBox
- Download VirtualBox [here](https://www.virtualbox.org/wiki/Downloads).
### Setting up Kali Linux
- Download Kali Linux [here](https://www.kali.org/get-kali/#kali-platforms)

*Options Explained:*
- ***Virtual Machines***
> It's pre-built. You can open it right away after unzipe it.

**Install:**

*In VirtualBox -> Click Open button or `Ctrl + A` to open the unzipped file -> Kali Linux is running(Done).*

- ***Installer Images***
> It provides complete control over the hardware access. You have to configure hardware settings.

*Requirements*

| Level | Description | RAM | Storage |
| :---- | :---------: | :-: | ------: |
| Minimal | Basic Secure Shell (SSH) server without a desktop | 128 MB | 2 GB |
| Standard | Default Xfce4 desktop environment | 2 GB | 20 GB |
| Advanced | Better performance at resource-intensive tools | 8 GB | 20 GB |

**Install:**

*In VirtualBox -> Click on New button or `Ctrl + N` to create new virtual machine -> Fill out the highlighted portion:*
- `VM Name` PC name, 
- `VM Folder` place to store data, 
- `ISO Image` system to install with the installer file.

![virtual_machine_setup_step1](./images/virtual_machine_setup_1.png)

*Continue, `Right click` the created VM(virtual machine) -> slect `settings` -> select `System` tab -> do the following the changes:*
- change the `Base memory` to a compatibale number according to requirements, 



# Credits
[GO BACK TO REFERENCE](#reference)

- Tech-FireFish, Contributor, [Profile_URL](https://github.com/Tech-FireFish)
- IBM Ethical Hacking with Open Source Tools Professional Certificate instructed by IBM Skills Network Team, Dee Dee Collette, Christo Oehley on Coursera platform, 2024, [URL](https://www.coursera.org/professional-certificates/ibm-ethical-hacking-with-open-source-tools).
