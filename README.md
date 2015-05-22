# Ruby 2.2.x RPM for Centos 6

## Install the rpm package

On an Centos 6 machine simply rpm install:

    $ rpm -iv https://github.com/fareoffice/ruby-rpm-el6-centos/raw/master/build/ruby-2.2.2-1.el6.x86_64.rpm

Or even better: put the .rpm in your repository and yum install. :) 

## Build the rpm package

If package needs to be rebuilt for a new ruby version, create a new .spec file based on latest existing ruby2.x.x.spec and update it accordingly. 

On a Centos 6 machine (or virtual machine):

    # Install rpm-build
    $ yum install rpm-build redhat-rpm-config rpmdevtools
    # Sets up a build folder structure in you home folder
    $ rpmdev-setuptree

Download ruby version source from:
https://ftp.ruby-lang.org/pub/ruby/

Move ruby source tar.gz to ~/rpmbuild/SOURCES

Move the new .spec file to ~/rpmbuild/SPECS

Build (change to right .spec filename):

    $ rpmbuild -ba ~/rpmbuild/SPECS/ruby2.x.x.spec

Build will take about 5 - 10 minutes and the output can be found in ~/rpmbuild/RPMS