# R-RStudio-CDS101
How to setup R and R Studio for CDS101 on Mac, Linux, and Windows

## Table of Contents

  i. [Setting Up R/R-Studio for Linux](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-linux)
  
  ii.[Setting Up R/R-Studio for Mac](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-mac)
  
  iii.[Setting Up R/R-Studio for Windows](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-windows)

## Setting Up R/R-Studio for Linux

***Note: Before moving to the R and RStudio installation, we need to make sure of some basic things for the smooth run. You need to have your Linux system ready with a user with sudo rights along with access to the internet for getting the required packages.***

### Step 1: Installing R

Those using RHEL based OS can use the yum command below.
```{}
$ yum install R
```
Those using Ubuntu can use the apt-get command as below.

```{}
$ apt-get install r-base
```

### Step 2: Verifying R
Check to see if R is installed
```{}
# R --version
```

### Step 3: Installing R-Studio
  i. Download the RStudio Free Version for your OS from their official web link at: https://www.rstudio.com/products/rstudio/download/
    
***NOTE: MAKE SURE TO CHOOSE THE RIGHT PACKAGE FOR YOUR OS***

  ii. Once downloaded, install it using the ‘rpm’ command in the case of RHEL based OS and use ‘dpkg’ if you are using Ubuntu.

RHEL:
```{}
# rpm -ivh rstudio-1.4.1717-x86_64.rpm
```

Ubuntu:
```{}
# dpkg -i rstudio-1.4.1717-amd64.deb
```

### Step 4: Verifying R-Studio
If you use GNOME, you should be able to hit the SUPER key *[Typically the Windows Key on Your Keyboard]* to go into your Activties tab. From there you should find the R-Studio Icon. Click it and the R-Studio applciation should open.

Alternativly, you can run the rstudio command in the terminal to open R-Studio
```{}
rstudio
```


### Step 5: Installing the Required Packages
