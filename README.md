# acsm-to-kindle
a simple GUI script to quickly send an ACSM Ebook to a Kindle through email.

## Installation

### !! WARNING !!
#### At the moment this script is only for Linux with X or Wayland.

1. first, install the dependencies: `kdialog, gourou, ebook-convert, mailutils, and ssmtp.`
the steps here may vary depending on your system.

2. next, we need to edit the config files for SSMTP.
run `sudo` with your favorite text editor to edit `/etc/ssmtp/ssmtp.conf`
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
where `foo` is your email prefix and `bar` is the website.

for this example, i'll be using a Gmail address.

3. you might have to go to [this link](https://www.amazon.com/myk) to whitelist your main email address so we can use it to send files from.

4. we need to find the kindle's email address.
on the kindle, swipe down from the top of the screen to bring up the menu and go to "All Settings"
here, go to "Your Account", then copy down the "Send-to-Kindle" email address

5. now edit the `acsm-to-kindle` script from this repo. and change
````
EMAIL="user@kindle.com"
````
to your kindle's email address (as we found in the last step)
