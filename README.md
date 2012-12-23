Install a Linux Server for mapshup
==================================

A step by step installation and configuration guide to run GIS application in general and mapshup in particular within a linux box

Prerequisites
=============

A server with a fresh Ubuntu 12.10 server distribution installed

Installation
============

Add Ubuntu GIS unstable repository
----------------------------------

    apt-get install python-software-properties
    apt-get install software-properties-common
    add-apt-repository ppa:ubuntugis/ubuntugis-unstable
    apt-get update
    apt-get upgrade
    
Apache and PHP
--------------

    apt-get install apache2
    apt-get install php5
    apt-get install php5-curl
    apt-get install php5-pgsql

PostgreSQL and PostGIS
----------------------

    apt-get install postgresql-9.1
    apt-get install postgresql-9.1-postgis
    
GDAL and OGR
------------

    apt-get install gdal-bin
    
mapserver and mapcache
----------------------

    apt-get install mapserver-bin
    apt-get install cgi-mapserver
    apt-get install libapache2-mod-mapcache
    
Usefull packages
----------------

    apt-get install git
    apt-get install postfix
    apt-get install fail2ban
    

Configuration
=============

mapcache
--------

Create mapcache directory

    mkdir /home/mapcache
    chown -R www-data:www-data /home/mapcache
    
Edit file /etc/apache2/mod-available/mapcache.conf

    <IfModule mapcache_module>
        <Directory "/home/mapcache/">
            Order Allow,Deny
            Allow from all
        </Directory>
        MapCacheAlias /mapcache "/home/mapcache/mapcache.xml"
    </IfModule>

Restart apache

    ln -s /etc/apache2/mods-available/mapcache.conf /etc/apache2/mods-enabled
    /etc/init.d/apache2 restart
    
    

    
    
