# R-RStudio-CDS101
How to setup R and R Studio for CDS101 on Mac, Linux, and Windows

## Table of Contents

i. [Setting Up R/R-Studio for Windows](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-windows)

ii.[Setting Up R/R-Studio for Mac OSX](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-mac-osx)

iii. [Setting Up R/R-Studio for Linux](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#setting-up-rr-studio-for-linux)

iv: [Sources](https://github.com/jbond8/R-RStudio-CDS101/edit/main/README.md#troubleshooting)

## Setting Up R/R-Studio for Windows

### Step 1: Installing R
  
i. Go to https://cran.r-project.org/bin/windows/base/

ii. Click on "Download R 4.1.2 for Windows (86 megabytes, 32/64 bit)"
  
iii. Once the download is finished, you will obtain a file named "*R-4.1.2-win.exe*" or similar depending on the version of R that you download.

iv. Open up the *R-4.1.2-win.exe* file and click the button 'Next' until the process is complete. It is best to stick with the defaults for installation.

### Step 2: Installing R-Studio
  i. Download the RStudio Free Version for Windows from their official web link at: https://www.rstudio.com/products/rstudio/download/#download

  ii. Once the download is complete, you will get a file named "RStudio-2022.02.0-443.exe" or similar depending on the version of R-Studio that you download.
  
  iii. Open up the *RStudio-2022.02.0-443.exe* file and click the button 'Next' until the process is complete. It is best to stick with the defaults for installation.

### Step 3: Installing the Required Packages
i. Open up R-Studio and click on the console tab in the bottom left.

ii. Proceed to separately install the packages listed below using the ```install.packages("package-name")``` command:

* bookdown
* dplyr
* ggplot2 
* infer
* kableExtra
* knitr
* readr
* rmarkdown
* tinytex
* tidyverse

iii. Once you have installed the packages, click on the packages tab on the bottom right pane to see that packages are there.

### Step 4: Setting up Git

**ADAPTED FROM:** *Introduction to Computational and Data Sciences* by James K. Glasbrenner, Ajay Kulkarni, and Dominic White

**SOURCE: https://book.cds101.com/initial-set-up.html**
  
**NOTE: The adaptation from *Introduction to Computational and Data Sciences* uses a UNIX based system, instead of Windows. I have altered the commands below to work with Windows Command Prompt, the Windows equivalent to the UNIX Terminal**
  
i. Check if you have "git" installed on your computer
  
You can do this by running the command below in the "Terminal" tab of the bottom left pane in R-Studio.
  ```{}
  git --version
  ```

* If git is not found on your computer, proceed to **ONLY** follow the instructions in Step 1 [here](https://medium.com/devops-with-valentine/2021-how-to-install-git-on-windows-10-step-by-step-guide-1c9db500e734)

* If git is found on your computer, proceed to the next step below.
  
ii. Create a Personal Access Token on GitHub

A personal access token is essentially a temporary password that you can create to use with your GitHub account instead of your main account. It is much more secure than using your main GitHub password when working on GitHub projects.

Login to your account at GitHub account and follow steps 1-9 [here](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) under the section Creating a Token.

A few notes:

* In step 7, give your token a long enough expiration so that it will last past the end of the semester.
* In step 8, you only need to check the box that says repo.
* In step 9, make sure you store a copy of the token that is generated for you (e.g. copy-and-paste it into a text file). You will never be able to view this token again on GitHub, so if you lose it, you will need to create a new token by repeating steps 1-9 all over again…

Once you have created the token, return to RStudio, and move onto the next section:
4.4.3 Configure RStudio for use with Git

Take a look in the bottom-left pane of RStudio. You should see a tab called Console which is open by default, and another one called Terminal. Switch to the Terminal tab. (If you do not see a Terminal, create one from the top menu in RStudio by going to Tools > Terminal > New Terminal.)

It may take a few seconds for the Terminal to load, but once it has done so you will see a line that ends with a dollar symbol $ and a flashing black cursor.

Copy-and-paste the following command into the Terminal and then press Enter to run it:

```{}
git config --global credential.helper store
```
Note that:

* You will not see any response in the Terminal if the line runs successfully. However you can check if it was successful by running this line git config credential.helper - you should get the response store.
* To paste copied text into the Terminal with a keyboard shortcut, use Ctrl+Shift+v on your keyboard instead of just Ctrl+v (and if you are using a Mac, use the Cmd key instead of Ctrl).

Next we need to run two more lines in the Terminal:
```{}
git config --global user.name "FirstName LastName"
git config --global user.email "netID@gmu.edu"
```

You should obviously replace the values inside the quotation marks with your name on the first line, and your GMU email address on the second line (which should match the email address you used to sign up for your GitHub account).

Next, switch back to the Console tab of the bottom left pane (next to the Terminal tab).

Copy-and-paste the following lines three lines of R code into the Console and hit <Enter>.
  
```{}
install.packages("gitcreds")
library(gitcreds)
gitcreds_set()
```

Note that in the Console you can use Ctrl+v to paste instead of Ctrl+Shift+v (or just Cmd+v on a Mac).

You will be prompted to enter the token that you just created above on GitHub.com. You should copy-and-paste the token from where you saved it to prevent any spelling errors, and then press <Enter> again.

Now you should be all set up!
  
## Setting Up R/R-Studio for Mac OSX

***Note: Before moving to the R and RStudio installation, we need to make sure of some basic things for the smooth run. You need to have your Linux system ready with a user with sudo rights along with access to the internet for getting the required packages.***
  
### Step 1: Installing R

i. Go to https://cran.r-project.org/bin/macosx/

ii. Click on "R-4.1.2.pkg", it will be the first option listed.
  
iii. Once the download is finished, you will obtain a file named "*R-4.1.2.pkg*" or similar depending on the version of R that you download.

iv. Open up the *R-4.1.2.pkg* file and proceed with the installation process. It is best to stick with the defaults for installation.

### Step 2: Installing R-Studio
  i. Download the RStudio Free Version for macOS 10.14+ from their official web link at: https://www.rstudio.com/products/rstudio/download/#download

  ii. Once the download is complete, you will get a file named "RStudio-2022.02.0-443.dmg" or similar depending on the version of R-Studio that you download.
  
  iii. Open up the *RStudio-2022.02.0-443.dmg* file and proceed with the instlalation process. It is best to stick with the defaults for installation.
  
### Step 3: Installing the Required Packages
i. Open up R-Studio and click on the console tab in the bottom left.

ii. Proceed to separately install the packages listed below using the ```install.packages("package-name")``` command:

* bookdown
* dplyr
* ggplot2 
* infer
* kableExtra
* knitr
* readr
* rmarkdown
* tinytex
* tidyverse

iii. Once you have installed the packages, click on the packages tab on the bottom right pane to see that packages are there.

### Step 4: Setting up Git

**ADAPTED FROM:** *Introduction to Computational and Data Sciences* by James K. Glasbrenner, Ajay Kulkarni, and Dominic White

**SOURCE: https://book.cds101.com/initial-set-up.html**

i. Create a Personal Access Token on GitHub

A personal access token is essentially a temporary password that you can create to use with your GitHub account instead of your main account. It is much more secure than using your main GitHub password when working on GitHub projects.

Login to your account at GitHub account and follow steps 1-9 [here](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) under the section Creating a Token.

A few notes:

* In step 7, give your token a long enough expiration so that it will last past the end of the semester.
* In step 8, you only need to check the box that says repo.
* In step 9, make sure you store a copy of the token that is generated for you (e.g. copy-and-paste it into a text file). You will never be able to view this token again on GitHub, so if you lose it, you will need to create a new token by repeating steps 1-9 all over again…

Once you have created the token, return to RStudio, and move onto the next section:
4.4.3 Configure RStudio for use with Git

Take a look in the bottom-left pane of RStudio. You should see a tab called Console which is open by default, and another one called Terminal. Switch to the Terminal tab. (If you do not see a Terminal, create one from the top menu in RStudio by going to Tools > Terminal > New Terminal.)

It may take a few seconds for the Terminal to load, but once it has done so you will see a line that ends with a dollar symbol $ and a flashing black cursor.

Copy-and-paste the following command into the Terminal and then press Enter to run it:

```{}
git config --global credential.helper store
```
Note that:

* You will not see any response in the Terminal if the line runs successfully. However you can check if it was successful by running this line git config credential.helper - you should get the response store.
* To paste copied text into the Terminal with a keyboard shortcut, use Ctrl+Shift+v on your keyboard instead of just Ctrl+v (and if you are using a Mac, use the Cmd key instead of Ctrl).

Next we need to run two more lines in the Terminal:
```{}
git config --global user.name "FirstName LastName"
git config --global user.email "netID@gmu.edu"
```

You should obviously replace the values inside the quotation marks with your name on the first line, and your GMU email address on the second line (which should match the email address you used to sign up for your GitHub account).

Next, switch back to the Console tab of the bottom left pane (next to the Terminal tab).

Copy-and-paste the following lines three lines of R code into the Console and hit <Enter>.
  
```{}
install.packages("gitcreds")
library(gitcreds)
gitcreds_set()
```

Note that in the Console you can use Ctrl+v to paste instead of Ctrl+Shift+v (or just Cmd+v on a Mac).

You will be prompted to enter the token that you just created above on GitHub.com. You should copy-and-paste the token from where you saved it to prevent any spelling errors, and then press <Enter> again.

Now you should be all set up!
  
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

Alternatively, you can run the rstudio command in the terminal to open R-Studio
```{}
rstudio
```


### Step 5: Installing the Required Packages
i. Open up R-Studio and click on the console tab in the bottom left.

ii. Proceed to separately install the packages listed below using the ```install.packages("package-name")``` command:

* bookdown
* dplyr
* ggplot2 
* infer
* kableExtra
* knitr
* readr
* rmarkdown
* tinytex
* tidyverse

iii. Once you have installed the packages, click on the packages tab on the bottom right pane to see that packages are there.

### Step 6: Setting up Git

**ADAPTED FROM:** *Introduction to Computational and Data Sciences* by James K. Glasbrenner, Ajay Kulkarni, and Dominic White

**SOURCE: https://book.cds101.com/initial-set-up.html**

i. Create a Personal Access Token on GitHub

A personal access token is essentially a temporary password that you can create to use with your GitHub account instead of your main account. It is much more secure than using your main GitHub password when working on GitHub projects.

Login to your account at GitHub account and follow steps 1-9 [here](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) under the section Creating a Token.

A few notes:

* In step 7, give your token a long enough expiration so that it will last past the end of the semester.
* In step 8, you only need to check the box that says repo.
* In step 9, make sure you store a copy of the token that is generated for you (e.g. copy-and-paste it into a text file). You will never be able to view this token again on GitHub, so if you lose it, you will need to create a new token by repeating steps 1-9 all over again…

Once you have created the token, return to RStudio, and move onto the next section:
4.4.3 Configure RStudio for use with Git

Take a look in the bottom-left pane of RStudio. You should see a tab called Console which is open by default, and another one called Terminal. Switch to the Terminal tab. (If you do not see a Terminal, create one from the top menu in RStudio by going to Tools > Terminal > New Terminal.)

It may take a few seconds for the Terminal to load, but once it has done so you will see a line that ends with a dollar symbol $ and a flashing black cursor.

Copy-and-paste the following command into the Terminal and then press Enter to run it:

```{}
git config --global credential.helper store
```
Note that:

* You will not see any response in the Terminal if the line runs successfully. However you can check if it was successful by running this line git config credential.helper - you should get the response store.
* To paste copied text into the Terminal with a keyboard shortcut, use Ctrl+Shift+v on your keyboard instead of just Ctrl+v (and if you are using a Mac, use the Cmd key instead of Ctrl).

Next we need to run two more lines in the Terminal:
```{}
git config --global user.name "FirstName LastName"
git config --global user.email "netID@gmu.edu"
```

You should obviously replace the values inside the quotation marks with your name on the first line, and your GMU email address on the second line (which should match the email address you used to sign up for your GitHub account).

Next, switch back to the Console tab of the bottom left pane (next to the Terminal tab).

Copy-and-paste the following lines three lines of R code into the Console and hit <Enter>.
  
```{}
install.packages("gitcreds")
library(gitcreds)
gitcreds_set()
```

Note that in the Console you can use Ctrl+v to paste instead of Ctrl+Shift+v (or just Cmd+v on a Mac).

You will be prompted to enter the token that you just created above on GitHub.com. You should copy-and-paste the token from where you saved it to prevent any spelling errors, and then press <Enter> again.

Now you should be all set up!

## Sources

* [How to Install R on Windows, Mac OS X, and Ubuntu Tutorial](https://www.datacamp.com/community/tutorials/installing-R-windows-mac-ubuntu) by Francisco Javier Carrera Arias
  
* [Introduction to Computational and Data Sciences](https://book.cds101.com/) by James K. Glasbrenner, Ajay Kulkarni, and Dominic White
  
* [[2021] How to install Git on Windows 10 (step by step guide)](https://medium.com/devops-with-valentine/2021-how-to-install-git-on-windows-10-step-by-step-guide-1c9db500e734) by Valentin Despa
