Electrum NavCoin - Lightweight NavCoin client
=====================================



On first launch Electrum NavCoin will be unable to connect the electrum servers until it has downloaded the blockchain headers (Currently 42MB).

NavCoin is a Proof-Of-Stake Coin, currently Electrum NavCoin is unable to spend staked coins.



Prebuilt Windows Executables
===============

    Portable Windows executable: https://www.navcoin.org/downloads

    Windows Installer: https://www.navcoin.org/downloads



Getting started
===============

Electrum is a pure python application. However, if you want to use the
Qt interface, then you need to install the Qt dependencies::

    sudo apt-get install python-pip python-qt4


If you downloaded the official package (tar.gz), then you can run
Electrum from its root directory, without installing it on your
system. To run Electrum from this directory, just do::

    ./electrum-navcoin

If you cloned the git repository, then you need to compile extra files
before you can run Electrum. Read the next section, "Development
Version".



Development version
===================

Check out the code from Github::

    git clone git://github.com/navcoindev/electrum-navcoin.git
    cd electrum-navcoin

Compile the icons file for Qt::

    sudo apt-get install pyqt4-dev-tools
    pyrcc4 icons.qrc -o gui/icons_rc.py

Compile the protobuf description file::

    sudo apt-get install protobuf-compiler
    protoc --proto_path=lib/ --python_out=lib/ lib/paymentrequest.proto

Create translations::

    sudo apt-get install python-pycurl gettext
    ./contrib/make_locale



Install on Linux systems
========================

If you install Electrum on your system, you can run it from any
directory.

    sudo python setup.py install



Creating Binaries
=================


In oder to creating binaries, you must create the 'packages' directory::

    ./contrib/make_packages


Mac OS X
--------

    # On port based installs
    sudo python setup-release.py py2app

    # On brew installs
    ARCHFLAGS="-arch i386 -arch x86_64" sudo python setup-release.py py2app --includes sip

    sudo hdiutil create -fs HFS+ -volname "Electrum" -srcfolder dist/Electrum.app dist/electrum-VERSION-macosx.dmg


Windows
-------

see contrib/build-wine/README


Android
-------

see gui/kivy/Readme.txt