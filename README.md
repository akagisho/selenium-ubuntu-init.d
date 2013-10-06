selenium-ubuntu-init.d
================

INTRODUCTION
-------------

init.d scripts for selenium server.

SETUP
-------------

download jar file:

    $ sudo wget -O /var/lib/selenium-server-standalone-2.35.0.jar \
    https://selenium.googlecode.com/files/selenium-server-standalone-2.35.0.jar
    $ sudo ln -s /var/lib/selenium-server-standalone-2.35.0.jar \
    /var/lib/selenium-server-standalone.jar

install required packages:

    $ sudo apt-get install xvfb openjdk-7-jre git-core cpanminus
    $ sudo cpanm Daemon::Control

save init.d scripts:

    $ git clone https://github.com/akagisho/selenium-ubuntu-init.d.git
    $ sudo cp selenium-ubuntu-init.d/etc/init.d/* /etc/init.d

set services to start automatically:

    $ sudo update-rc.d xvfb defaults
    $ sudo update-rc.d selenium defaults

start services:

    $ sudo service xvfb start
    $ sudo service selenium start
