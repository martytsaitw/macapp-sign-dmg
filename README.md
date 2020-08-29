# macapp-sign-dmg

Prepare your **YourApplication.app**

Sign the app
===============
yarn electron-osx-sign --platform=darwin --type=distribution --entitlements=./entitlements.mac.plist --entitlements-inherit=./entitlements.mac.plist  --hardened-runtime --no-gatekeeper-assess **YourApplicationPath.app**

Notarize the app
===============
yarn electron-notarize --bundle-id **YourBundleID** --username **YourAppleID** --password **YourAppSpecificPassword** **YourApplicationPath.app**

Browse to https://appleid.apple.com/account/manage, scroll to Security > App-Specific Password, and generate an App-Specific password for an app named your-notarizing-name. Copy the password that it gives you.

DMG creation
===============
./dmg/create-dmg --eula **YourLicenseFileInTxt** --background templates/background.tiff --window-pos 200 120 --window-size 540 380 --icon-size 100 --app-drop-link 400 220 --icon **YourApplication.app** 100 220 --hide-extension **YourApplication.app** **YourOutput.dmg** **YourApplicationPath.app**
