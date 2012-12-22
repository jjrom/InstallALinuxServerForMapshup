Install a Linux Server for mapshup
==================================

A step by step installation and configuration guide to run GIS application in general and mapshup in particular within a linux box

Prerequisites
=============

A server with a fresh Ubuntu 12.10 server distribution installed

Installation
============

Add Ubuntu GIS unstable repository

    apt-get install python-software-properties
    apt-get install software-properties-common
    add-apt-repository ppa:ubuntugis/ubuntugis-unstable
    apt-get update
    apt-get upgrade
    
Apache and PHP

    apt-get install apache2
    apt-get install php5
    apt-get install php5-curl

PostgreSQL and PostGIS

    apt-get install postgresql-9.1
    apt-get install postgresql-9.1-postgis
    
GDAL and OGR

    apt-get install gdal-bin
    
mapserver and mapcache

    apt-get install mapserver-bin
    apt-get install cgi-mapserver
    apt-get install libapache2-mod-mapcache
    
  
    
    
    
