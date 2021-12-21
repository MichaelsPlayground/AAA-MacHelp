# AAA-MacHelp

```plaintext
Show Desktop: fn + F11

Show hidden files: cmd shift .

Screenshot komplett: cmd shift 3

Screenshot bereich: cmd shift 4

Ordner mit Tag versehen:
Finder ctrl + Klick auf den gewünschten Ordner, Tag auswählen, fertig

Start XCode with or without Rosetta (to run code evtl., e.g. 
https://github.com/backslash-f/aescryptable
https://newbedev.com/aes-encryption-in-swift

use finder, go back to Programme / rechts click auf XCode, Haken bei Start mit/ohne Rosetta, fertig


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
find . -type d -name flutter_build -prune -exec rm -rf {} \;
```

list directories with size:
```plaintext
find . -maxdepth 1 -mindepth 1 -type d -exec du -hs {} \;

sorted:
find . -maxdepth 1 -mindepth 1 -type d -exec du -s {} \; | sort -n;

find . -maxdepth 1 -mindepth 1 -type d -exec du -s * | sort -n;

find . -maxdepth 1 -mindepth 1 -type d -exec du -hs {} \; | sort -n;

https://support.apple.com/de-de/guide/terminal/apdd100908f-06b3-4e63-8a87-32e71241bab4/mac
in te
delete_builds.sh
chmod 755 delete_builds.sh

Nachdem du aus der Shell-Skript-Datei eine ausführbare Datei gemacht hast, kannst du diese durch Eingeben des Pfadnamens ausführen. Zum Beispiel:
% ~/Documents/Dev/YourScriptName.sh
oder
% cd ~/Documents/Dev/ 
% ./YourScriptName.sh
./delete_builds.sh

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

**Flutter doctor**:
```plaintext
/Users/michaelfehr/flutter/bin/flutter doctor -v

new version 2.8.0 updated 15.12.2021:
/Users/michaelfehr/flutter/bin/flutter upgrade
michaelfehr@MinivonMichael AAA-MacHelp % /Users/michaelfehr/flutter/bin/flutter upgrade
Upgrading Flutter to 2.8.0 from 2.5.3 in /Users/michaelfehr/flutter...
Downloading Dart SDK from Flutter engine 40a99c595137e4b2f5b2efa8ff343ea23c1e16b8...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
  0  205M    0  463k    0     0   735k      0  0:04:46 --:--:--  0:04:46  733k
...
100  205M  100  205M    0     0  1997k      0  0:01:45  0:01:45 --:--:-- 2003k
Building flutter tool...

Upgrading engine...
Downloading android-arm-profile/darwin-x64 tools...              1.652ms
Downloading android-arm-release/darwin-x64 tools...              1.330ms
Downloading android-arm64-profile/darwin-x64 tools...            1.517ms
Downloading android-arm64-release/darwin-x64 tools...            1.343ms
Downloading android-x64-profile/darwin-x64 tools...              1.508ms
Downloading android-x64-release/darwin-x64 tools...              1.331ms
Downloading android-x86 tools...                                   11,6s
Downloading android-x64 tools...                                   11,8s
Downloading android-arm tools...                                    5,4s
Downloading android-arm-profile tools...                            3,1s
Downloading android-arm-release tools...                         2.001ms
Downloading android-arm64 tools...                                  5,9s
Downloading android-arm64-profile tools...                          3,4s
Downloading android-arm64-release tools...                       2.276ms
Downloading android-x64-profile tools...                            3,5s
Downloading android-x64-release tools...                         2.353ms
Downloading android-x86-jit-release tools...                        3,8s
Downloading ios tools...                                           27,6s
Downloading ios-profile tools...                                   21,9s
Downloading ios-release tools...                                  115,9s
Downloading Web SDK...                                             18,1s
Downloading CanvasKit...                                            3,7s
Downloading package sky_engine...                                  615ms
Downloading flutter_patched_sdk tools...                         1.923ms
Downloading flutter_patched_sdk_product tools...                 1.824ms
Downloading darwin-x64 tools...                                    17,1s
Downloading ios-deploy...                                           57ms
Downloading darwin-x64/font-subset tools...                        659ms

Flutter 2.8.0 • channel stable • https://github.com/flutter/flutter.git
Framework • revision cf44000065 (vor 7 Tagen) • 2021-12-08 14:06:50 -0800
Engine • revision 40a99c5951
Tools • Dart 2.15.0

Running flutter doctor...
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 2.8.0, on macOS 11.6.1 20G224 darwin-arm, locale de-DE)
[✓] Android toolchain - develop for Android devices (Android SDK version 31.0.0)
[✓] Xcode - develop for iOS and macOS (Xcode 13.1)
[✓] Chrome - develop for the web
[✓] Android Studio (version 2020.3)
[✓] IntelliJ IDEA Community Edition (version 2021.2.2)
[✓] Connected device (1 available)

• No issues found!



15.12.2021:
result:
[✓] Flutter (Channel stable, 2.5.3, on macOS 11.6.1 20G224 darwin-arm, locale de-DE)
    • Flutter version 2.5.3 at /Users/michaelfehr/flutter
    • Upstream repository https://github.com/flutter/flutter.git
    • Framework revision 18116933e7 (vor 9 Wochen), 2021-10-15 10:46:35 -0700
    • Engine revision d3ea636dc5
    • Dart version 2.14.4

[✓] Android toolchain - develop for Android devices (Android SDK version 31.0.0)
    • Android SDK at /Users/michaelfehr/Library/Android/sdk
    • Platform android-31, build-tools 31.0.0
    • Java binary at: /Applications/Android Studio.app/Contents/jre/Contents/Home/bin/java
    • Java version OpenJDK Runtime Environment (build 11.0.10+0-b96-7249189)
    • All Android licenses accepted.

[✓] Xcode - develop for iOS and macOS
    • Xcode at /Applications/Xcode.app/Contents/Developer
    • Xcode 13.1, Build version 13A1030d
    • CocoaPods version 1.11.2

[✓] Chrome - develop for the web
    • Chrome at /Applications/Google Chrome.app/Contents/MacOS/Google Chrome

[✓] Android Studio (version 2020.3)
    • Android Studio at /Applications/Android Studio.app/Contents
    • Flutter plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/6351-dart
    • Java version OpenJDK Runtime Environment (build 11.0.10+0-b96-7249189)

[✓] IntelliJ IDEA Community Edition (version 2021.2.2)
    • IntelliJ at /Applications/IntelliJ IDEA CE.app
    • Flutter plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/6351-dart

[✓] Connected device (1 available)
    • Chrome (web) • chrome • web-javascript • Google Chrome 96.0.4664.93

```

**SWIFT code online formatter:**

https://swift-format.com


**FlutterCrypto bplaced anmelden**:

http://fluttercrypto.bplaced.net/wp-login.php


Anker nutzen:
```plaintext
Die Textstelle, zu der gesprungen werden soll (Ziel) markieren, 
drei Punkte untereinander, Als HTML bearbeiten
rechts erweitert HTML-Anker anker01
Ursprung: Text markieren, Linksymbol, #anker01 eintragen, internal, fertig.
```



