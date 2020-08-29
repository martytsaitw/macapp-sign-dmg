# macapp-sign-dmg

Prepare your <font color=#FF0000>YourApplication.app</font>

Sign the app
===============
yarn electron-osx-sign --platform=darwin --type=distribution --entitlements=./entitlements.mac.plist --entitlements-inherit=./entitlements.mac.plist  --hardened-runtime --no-gatekeeper-assess <font color=#FF0000>YourApplicationPath.app</font>

Notarize the app
===============
yarn electron-notarize --bundle-id <font color=#FF0000>YourBundleID</font> --username <font color=#FF0000>YourAppleID</font> --password <font color=#FF0000>YourAppSpecificPassword</font> <font color=#FF0000>YourApplicationPath.app</font>

Browse to https://appleid.apple.com/account/manage, scroll to Security > App-Specific Password, and generate an App-Specific password for an app named your-notarizing-name. Copy the password that it gives you.

DMG creation
===============
./dmg/create-dmg --eula <font color=#FF0000>YourLicenseFileInTxt</font> --background templates/background.tiff --window-pos 200 120 --window-size 540 380 --icon-size 100 --app-drop-link 400 220 --icon <font color=#FF0000>YourApplication.app</font> 100 220 --hide-extension <font color=#FF0000>YourApplication.app</font> <font color=#FF0000>YourOutput.dmg</font>  <font color=#FF0000>YourApplicationPath.app</font>
