*****Installation Guide for Nextcloud*****

***On Mac***

**Install Node**
https://nodejs.org/en/

**Install homebrew**
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install --with-openssl curl
brew install --with-homebrew-curl --with-apache php71

**Download Nextcloud**
https://nextcloud.com/install/#

**Go to a File Manager and unzip the file nextcloud-13.0.0.zip.**

**Go back to the terminal and go to the folder where you just unzipped the file to:**
$ cd ~/Downloads/nextcloud

**run server**
$ php -S localhost:3000

Now you can visit the browser at localhost:3000 and fill up the form with an admin username and password (pick one as you like, usually for develpment I always use admin/admin).
About the storage, pick the sqlite option because at this point, it is the easiest to work with. Now just click "Finish setup". If everything went smooth now you should have Nextcloud up and running!


**set up ssh key**
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

**add ssh key to GitHub**
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

**clone contacts app into nextcloud/app folder**
git clone git@github.com:nextcloud/contacts.git

**Building the app**
The app can be built by using the provided Makefile by running:
make
This requires the following things to be present:
- make
- which
- tar: for building the archive
- curl: used if phpunit and composer are not installed to fetch them from the web
- npm: for building and testing everything JS

**Running tests**
You can use the provided Makefile to run all tests by using:
make test
This will run the PHP unit and integration tests and if a package.json is present in the js/ folder will execute npm run test
Of course you can also install PHPUnit and use the configurations directly:
phpunit -c phpunit.xml
or:
phpunit -c phpunit.integration.xml
for integration tests

---------------------------------------------------------------------------------------------------------------------------


More notes are available here: https://cloud.nextcloud.com/s/G4nxXSaRj6RJ9Dn

To put things into perspective and to organize it, this is how far
we got :)

[x] Install Virtual Box.
[x] Set up an virtual machine with Ubuntu.
A virtual machine is essentially emulating an operational system
inside your existing system - in your cases: you are running
Windows/MAC OS and emulating an Ubuntu machine.

[x] Install PHP and PHP modules needed to run Nexcloud.


https://docs.nextcloud.com/server/13/admin_manual/installation/source_installation.html#example-installation-on-ubuntu-16-04-lts-server
[2]
[3]

At this point you should exit your root user by running:

$ exit

Now you are again your normal user.

Go to a File Manager and unzip the file nextcloud-13.0.0.zip.

[x] Run Nextcloud

Go back to the terminal and go to the folder where you just unzipped
the file to:

$ cd ~/Downloads/nextcloud

In Linux the symbol ~ means your home directory: /home/yourusername
cd is the command to go to a folder. Now let's run Nextcloud:

$ php -S localhost:3000

Now you can visit the browser at localhost:3000 and fill up the form
with an admin username and password (pick one as you like, usually
for develpment I always use admin/admin).

About the storage, pick the sqlite option because at this point, it
is the easiest to work with. Now just click "Finish setup". If
everything went smooth now you should have Nextcloud up and running!

[x] Generate an app

This is easy :D
https://apps.nextcloud.com/developer/apps/generate [4]

[x] "Install" the app in Nextcloud

Again, go to the file manager, unzip the file and copy the unzipped
folder to
nextcloud/apps/

Go back to the browser, go to Settings (top right 'engine' icon),
click in the sub menu 'Apps'. Now to your left there is a link to
'Disabled apps', click on it. And your right you should see your
newly generated app. Now you can enable it.

Yesterday we run into the problem that the app version max version
was wrong - it was 12 and we had to change it to 13. To do so you
have to change it in:

nextcloud/apps/thenameofyourapp/appinfo/info.xml

Next steps:

[ ] Read the documentation

https://docs.nextcloud.com/server/13/developer_manual/index.html [5]

[ ] Understand the basics on how applications in Nextcloud works

The apps folders:
appinfo/: app metadata and configuration
css/: the CSS
js/: JavaScript files
lib/: PHP class files (Controller)
templates/: the templates (View)
tests/: the tests

A bit about MVC model:
https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
[6]

MVC means: Model View Controller. In very short term it means:
Model: the database (mysql, sqlite...)
View: the interface (JS, CSS..)
Controller: the logic (PHP, Node.js, anything that will run in the
server - to be simple)

The function of the Routes in the app is to connect the view with
the controller. You are basically telling your application that when
the user access, e.g.
http://localhost/nextcloud/index.php/apps/files/ [7] your controller
will execute e.g. the listFiles() function.

We can talk more about that later.

[ ] Pick an app issue on Github to start to work on

http://github.com/nextcloud [8] or

the list in
https://teams.railsgirlssummerofcode.org/projects/200-nextcloud [9]

[ ] Work on the issue
[ ] Create a pull request
