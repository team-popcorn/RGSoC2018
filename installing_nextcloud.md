****Installation Guide for Nextcloud & setting up the contacts app****

***On Mac***

**Install Node**
https://nodejs.org/en/

**Install homebrew & PHP 7.2 (latest stable release)**
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install --with-openssl curl
brew install --with-homebrew-curl --with-apache php71

**Download Nextcloud**
https://nextcloud.com/install/#

**Go to a File Manager and unzip the file nextcloud-13.0.0.zip.**

**Go back to the terminal and go to the folder where you just unzipped the file to:**
$ cd ~/Downloads/nextcloud

**set up ssh key**
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

**add ssh key to GitHub**
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

**clone contacts app into nextcloud/apps folder**
git clone git@github.com:nextcloud/contacts.git

**Building the app**
Go into the Contacts folder.
*depreciated - only true for angular version of App*
The app can be built by using the provided Makefile by running:
*make*

 - *updated make command*
The app can be built by using the provided Makefile by running:
*make watch-js*
or
*make build-js*

**run server**
$ php -S localhost:3000

Now you can visit the browser at localhost:3000 and fill up the form with an admin username and password (pick one as you like, usually for develpment I always use admin/admin).
About the storage, pick the sqlite option because at this point, it is the easiest to work with. Now just click "Finish setup". If everything went smooth now you should have Nextcloud up and running!

**Enable the app**
Click settings gear in upper right corner of Nextcloud and go to Apps, scroll down to contacts and click enable.


**Install Vue.js plugin in Chrome Devtools**
https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd

---------------------------------------------------------------------------------------------------------------------------


More notes are available here: https://cloud.nextcloud.com/s/G4nxXSaRj6RJ9Dn
