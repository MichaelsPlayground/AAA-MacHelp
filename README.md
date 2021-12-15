# AAA-MacHelp

```plaintext
Show Desktop: fn + F11

Show hidden files: cmd shift .

Screenshot komplett: cmd shift 3

Screenshot bereich: cmd shift 4
```

Download all repositories of a user, maximum is 100 reps per run
```plaintext
Johannes Milke 493 repositories Stand 27.11.2021
curl -s 'https://api.github.com/users/JohannesMilke/repos?page=1&per_page=100' | grep \"clone_url\" | awk '{print $2}' | sed -e 's/"//g' -e 's/,//g' | xargs -n1 git clone
curl -s 'https://api.github.com/users/JohannesMilke/repos?page=2&per_page=100' | grep \"clone_url\" | awk '{print $2}' | sed -e 's/"//g' -e 's/,//g' | xargs -n1 git clone
```

delete all build directories for flutter apps:
```plaintext
Finder - Go to folder - Right click - open terminal in folder
find . -type d -name build -prune -exec rm -rf {} \;
```

**Rename Flutter Apps**

```plaintext
/Users/michaelfehr/flutter/bin/flutter pub global activate rename
/Users/michaelfehr/flutter/bin/flutter pub global run rename --bundleId de.fluttercrypto.sym_encrypt_playground_libsodium
/Users/michaelfehr/flutter/bin/flutter pub global run rename --appname "Libsodium symmetric encryption"
```


**run Flutter App on real device**

https://stackoverflow.com/questions/54444538/how-do-i-run-test-my-flutter-app-on-a-real-device

```plaintext
For Android, this is pretty easy:

Enable Developer options and USB debugging on your device. This varies slightly by Android version, but the short version is you tap on the Device Build Number 7 times. Then a "Developer Options" option comes up and you can click "enable USB Debugging." See the linked Android documentation for the most up-to-date instructions.
Then plug your phone into your computer with a USB cable. You'll probably see some popup on your phone asking if you want to allow USB debuggng with that computer. Say "yes".
Run Flutter just like you would if you had a simulator running.
For iOS this is a little more complicated because you need an Apple ID or to sign up for a "Developer Account":

Open XCode, then open "Preferences>Accounts". Sign in with your ID.
"Manage Certificates" > click on the "+" sign and select "iOS Development".
Plug your device into your machine. Find your device in the drop down (Window > Organizer).
Below the Team pop-up menu, click Fix Issue.
In Xcode, click the Run button.
(in subsequent runs, you can deploy to the iOS device with Android Studio, VS Code, or any other IDE of choice, you just need to set up that certificate the first time with Xcode. Here's Apple's documentation on setting up Xcode to run a physical device.)

Die App wird aber nicht starten, da sie nicht von einem vertrauenswürdigen Entwickler stammt:
Einstellungen - Geräteverwaltung - Entwickler-App Apple Development ... anklicken - auf den Namen klicken - vertrauen - fertig, 
Nun startet die App
```

**overflow by xx pixels vermeiden:**
```plaintext
bei DropdownButtonFormField diese Zeile einfügen:
isExpanded: true,
```


**FlutterCrypto bplaced anmelden**:

http://fluttercrypto.bplaced.net/wp-login.php


Anker nutzen:
```plaintext
Die Textstelle, zu der gesprungen werden soll (Ziel) markieren, 
drei Punkte untereinander, Als HTML bearbeiten
rechts erweitert HTML-Anker anker01
Ursprung: Text markieren, Linksymbol, #anker01 eintragen, internal, fertig.
```



