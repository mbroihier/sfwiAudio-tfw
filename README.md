# sfwiAudio - Test Framework

This repository contains a test framework for the Android app sfwiAudio, a very simple podcast app.

https://sfwiAudio-tfw.herokuapp.com runs a deployment of the sfwiAudio-tfw repository recording the current state of app testing.

How this repository was created:

```
git clone https://github.com/mbroihier/tfw-template.git
mkdir sfwiAudio-tfw
cp -pr tfw-template/* sfwiAudio-tfw/
cd sfwiAudio-tfw
git init
```

Then a copy of the requirements was put into the directory and converted to text.  I use LibreOffice and the file name for the sfwiAudio requirements was sfwiAudioRequirements.odt.  In LibreOffice, converting to text is done by:

```
file --> save as --> Text(.txt)
```

The requirements database, REQ.SFWIAUDIO is made by running:

```
bin/buildReqDb.py sfwiAudioRequirements.txt
```

An empty book of test categories is then created.  This is just a text file (I used 'book' as the file name) that is a list of category names all in upper case.  I used:
```
STARTUP
SELECT
FINISH
CONTROLS
PERFORMANCE
```

I then used System Test Procedure Specification initialize, stpsInitialize to build the initial empty test database and then built the initial procedure book.

```
./bin/stpsInitialize.py book
./buildHTMLTraceTables book
./buildHTMLBook book
```

I then edited the names package.json to match my project and installed npms used.

```
npm install
```

The following starts the editing server locally so that test cases can be added.

```
node editor-server.js
```

By editing index.html, you can tailor the main page to your project specifics.  The files *.testDbCategoryTitle and *.testCategoryDescription can be edited to provide titles and descriptions for each test category.
