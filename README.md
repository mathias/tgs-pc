# Important Stuff!

## Module Dependencies
TGS requires the following python modules:
- [configobj](http://www.voidspace.org.uk/python/configobj.html)
- [M2Crypto](http://chandlerproject.org/Projects/MeTooCrypto)
- [netifaces](http://alastairs-place.net/projects/netifaces/)
- [PyQt4](http://www.riverbankcomputing.com/software/pyqt/download)
(also requires [Qt 4.x libraries](http://qt-project.org/downloads))
- [sip](http://www.riverbankcomputing.com/software/sip/download)

## OS X Notes
1. The version of python that comes with OS X will probably not work. Download and install
an official python build such as 2.7.3 per [this page](http://www.python.org/getit/mac/).
2. You may need to link /Library/Frameworks/Python.framework/Versions/Current/bin/python
to /usr/bin/python.
3. The PyQtX installer may be missing pyrcc4 which means tgs_pc/build_resources.sh will
not work. PyQt4 must be built from source at this time.
4. The version of sqlite3 that comes with OS X may not support the FTS4 extension.
Download and install [homebrew](http://mxcl.github.com/homebrew/), then
`brew install sqlite`
5. The tgs.osx script will tell OS X to find the homebrew version of libsqlite3.dylib and
then execute the normal tgs script.

## Building The UI
Before starting the app, you will need to execute tgs_pc/build_resources.sh once
and every time any file in the ui/ dir gets updated by you or by a git pull.

Cheers.

# Some info that may be interesting to you fellow developer...

## Extract from a chat with eviy:
	192707     +eviy  the community/community.py file (in the chat-demo) is kinda the main code for handling the messages that dispersy disseminates
	192811     +eviy  this file has a method called _initialize_meta_messages where all supported messages are defined
	192825     +eviy  in the demo only one message exists 'text'
	192911     +eviy  there are appropriate 'create' 'chec' and 'on_incoming' methods to handle the 'text' message, each is given as a parameter in _initialize_meta_messages
	192934     +eviy  if you want to play around, you can add some messages that may or may not be usefull
	193028     +eviy  there are several message policies that describe how dispersy should disseminate the message and to who'm.  also if someone needs permission to create it, etc
	193126     +eviy  http://www.scribd.com/doc/81170037/Boudewijn-Dispersy-Documentation-DRAFT-2010
	193158     +eviy  this is a a year old document that gives the basics of these policies
	193204     +eviy  but it is outdated :(
	193222     +eviy  but it may give an idea of what is and what isn't possible
	
	193516     +eviy  dispersy is from the QLectives project.  soon there will be a new deliverable document that is much more up to date
	193531     +eviy  but it hasn't been released yet :(

## About crypto keys:
	175753  +eviy  whirm: you can run 'python dispersy/crypto.py' to create fresh public/private pairs
	175851  +eviy  whirm: you copy the public key (they are HEX encoded) and put it in ChatCore.dispersy
	175904  +eviy  whirm: replace 'public_key = "3081a7301006072a8648ce3d020...' with the new key

# Notes about the icons used
The icons used in this app are copied from the Oxygen's [KDE icon set](http://www.oxygen-icons.org).
