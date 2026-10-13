# Loan EMI Calculator – installable app (PWA)

## Put it online (free)
1. Netlify: go to app.netlify.com/drop and drag this whole folder in. You get an https link in seconds.
   (Vercel or GitHub Pages also work. It must be served over https.)
2. Open the link on your phone.
   - Android Chrome: menu > Install app
   - iPhone Safari: Share > Add to Home Screen

## Turn it into a Play Store / App Store app (Capacitor)
Requires Node.js. Android Studio for Android, Xcode (Mac) for iOS.

    mkdir emi-app && cd emi-app
    npm init -y
    npm i @capacitor/core @capacitor/cli @capacitor/android @capacitor/ios
    mkdir www && cp -r ../<this-folder>/* www/
    npx cap init "Loan EMI Calculator" com.yourname.emicalc --web-dir=www
    npx cap add android
    npx cap add ios
    npx cap sync
    npx cap open android     # builds the Android app in Android Studio
    npx cap open ios         # builds the iOS app in Xcode

Then in Android Studio: Build > Generate Signed Bundle (AAB) and upload to Google Play Console ($25 one time).
For iOS: Product > Archive and upload to App Store Connect ($99/year).

## Before you publish
- Change com.yourname.emicalc to your own ID.
- Add a short privacy policy page (this app stores no data).
- Prepare screenshots and a short description.
