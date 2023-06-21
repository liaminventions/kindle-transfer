# acsm-to-kindle
a simple GUI script to quickly send an ACSM Ebook to a Kindle through email.

## Installation

### !! WARNING !!
#### At the moment this script is only for Linux with X or Wayland.

1. first, install the dependencies: `kdialog, gourou, ebook-convert, mailutils, and ssmtp.`
the steps here may vary depending on your system.

2. if you do happen to be using a gmail address, you'll have to enable 2FA and add an app password
   
   to do this, first go the [google account security page](https://myaccount.google.com/security) and search for "2-Step Verification" and follow the prompts to enable 2FA.

   next, go back to the security page and search for "App Passwords"

   add an "Other" app like so:
   
   ![image](https://github.com/liaminventions/acsm-to-kindle/assets/33787286/05a06911-c35e-4dca-b06a-3c2eefe2be33)

   once you name it to anything you like, hit "GENERATE".

   ![20230620-195528](https://github.com/liaminventions/acsm-to-kindle/assets/33787286/303b34ee-ca50-4cef-b1c3-0102100558b6)

   now copy the generated password. we'll use it as our password in the next step.

4. we need to edit the config files for SSMTP.
run `sudo` with your favorite text editor to edit `/etc/ssmtp/ssmtp.conf`

for example, `sudo vim /etc/ssmtp/ssmtp.conf`

what we need to do here is change the lines here as follows:
````
root=foo@bar
mailhub=smtp.bar:587
AuthUser=foo@bar
AuthPass=password
UseTLS=YES
TLS_CA_File=/etc/ssl/certs/ca-certificates.crt
UseSTARTTLS=YES
FromLineOverride=YES
````
where `foo` is your email prefix and `bar` is the website and password is your password.


4. you might have to go to [this link](https://www.amazon.com/myk) to whitelist your main email address so we can use it to send files from.

5. we need to find the kindle's email address.

on the kindle, swipe down from the top of the screen to bring up the menu and go to "All Settings"

here, go to "Your Account", then copy down the "Send-to-Kindle" email address

6. now edit the `acsm-to-kindle` script from this repo. and change
````
EMAIL="user@kindle.com"
````
to your kindle's email address (as we found in the previous step)

7. also change this line
````
EBOOK="~/ebook"
````
to the location on your computer where you store ebooks.

this will also be where they will be saved.

8. you should be all set to run `acsm-to-kindle`!

## Usage

WIP
