# Password Policy in Linux with PAM and Cracklib

## <img src="https://media.giphy.com/media/W5eoZHPpUx9sapR0eu/giphy.gif" width="30px" alt="Git"/>&nbsp;<i><b>Description</b></i></p> 

In Linux systems we also have the possibility of applying password policies focused on their complexity and robustness, improving the security of the system.

## <img src="https://media.giphy.com/media/W5eoZHPpUx9sapR0eu/giphy.gif" width="30px" alt="Git"/>&nbsp;<i><b>Environment</b></i></p> 
We are going to explain this configuration in two different environments:

Debian 10.
Fedora 34 beta.
In this way we cover the two variants on which the most widespread Linux distributions are based.

## <img src="https://media.giphy.com/media/W5eoZHPpUx9sapR0eu/giphy.gif" width="30px" alt="Git"/>&nbsp;<i><b> Installation</b></i></p>
Debian
In the case of Debian we must install the library:
```Shell
 sudo apt-get install libpam-cracklib
```
Fedora
In the Centos, RedHat and Fedora distributions the PAM Cracklib module comes by default in the installation, so we will not have to do anything.


There are different ways, but in our case we will use the PAM (Pluggable Authentication Modules) module together with the Cracklib library.

In turn, there are also many different parameters and configurations to apply in this module, but we will show a robust base configuration, from which it can be modified and/or expanded.

## <img src="https://media.giphy.com/media/W5eoZHPpUx9sapR0eu/giphy.gif" width="30px" alt="Git"/>&nbsp;<i><b> Files involved</b></i></p>
The following files will be involved in the configuration.

Debian
/etc/pam.d/common-password: where the rules to be applied to passwords are configured.
/etc/login.defs: where the password expiration period is defined.
Fedora
/etc/security/pwquality.conf: where the rules to be applied to passwords are configured.
/etc/pam.d/system-auth: we will indicate the last passwords, which will not be reusable.
/etc/login.defs: where the password expiration period is defined.
Configuration
We are going to apply the configuration to the different systems in order to achieve the following policy:<br>

* Minimum length of 10 characters.<br>
* At least one uppercase value.<br>
* At least one lowercase value.<br>
* At least one numeric character.<br>
* At least one special character.<br>
* The last 5 passwords cannot be repeated.<br>
* At least 3 characters must be changed in the new password compared to the previous one.<br>
* Block when the credential is entered incorrectly 3 times.<br>
* Expiration every 90 days.<br>
* Warning 15 days before expiration.<br>

## <h2> Technology stack  <img src = "https://media2.giphy.com/media/QssGEmpkyEOhBCb7e1/giphy.gif?cid=ecf05e47a0n3gi1bfqntqmob8g9aid1oyj2wr3ds3mg700bl&rid=giphy.gif" width = 32px> </h2>

![Shell Scrip](https://img.shields.io/badge/bash_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)


![Image](https://github.com/user-attachments/assets/77286517-6b9e-4c58-bc8a-e6315863736a)






