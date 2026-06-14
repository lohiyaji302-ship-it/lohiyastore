# App Hub - Android WebView App

Website URL: https://app-hub--lohiyaji302.replit.app

## Features
- WebView with full website loading
- Splash Screen (2 seconds)
- Back button navigates web history
- File upload & download support
- Pull-to-refresh (swipe down)
- Internet & storage permissions
- Progress bar while loading

---

## Android Studio में APK कैसे बनाएं (Step-by-Step)

### Step 1: Android Studio Install करें
1. https://developer.android.com/studio पर जाएं
2. Android Studio download और install करें

### Step 2: Project Open करें
1. Android Studio खोलें
2. **File → Open** पर click करें
3. इस folder को select करें: `android-apk/`
4. **OK** click करें
5. Gradle sync होने दें (2-3 मिनट लग सकते हैं)

### Step 3: App Icon बदलें (Optional)
1. `app/src/main/res/` folder पर right-click करें
2. **New → Image Asset** select करें
3. अपना icon image upload करें
4. **Next → Finish** click करें

### Step 4: Debug APK Build करें (Testing के लिए)
1. Menu में जाएं: **Build → Build Bundle(s) / APK(s) → Build APK(s)**
2. Build complete होने पर नीचे notification आएगी
3. **"locate"** पर click करें
4. APK यहाँ मिलेगी: `app/build/outputs/apk/debug/app-debug.apk`

### Step 5: Release APK Build करें (Play Store के लिए)
1. **Build → Generate Signed Bundle / APK** पर click करें
2. **APK** select करें → Next
3. **Create new...** पर click करें (Keystore बनाएं)
   - Key store path चुनें
   - Password डालें
   - Alias नाम दें
   - Fill करें: First and Last Name, Organization, Country Code (IN)
4. **Next** → **release** select करें → **Finish**
5. APK यहाँ मिलेगी: `app/build/outputs/apk/release/app-release.apk`

---

## Phone पर Install कैसे करें

### USB से (सबसे आसान)
1. Phone में **Developer Options** enable करें
   - Settings → About Phone → Build Number पर 7 बार tap करें
2. **USB Debugging** enable करें
3. Phone को USB से connect करें
4. Android Studio में Run button (▶) दबाएं

### APK file से directly
1. APK file को phone में copy करें
2. File Manager से APK खोलें
3. **"Install from unknown sources"** allow करें
4. Install करें

---

## Project Structure
```
android-apk/
├── app/
│   ├── src/main/
│   │   ├── java/com/apphub/webview/
│   │   │   ├── SplashActivity.java    ← Splash screen
│   │   │   └── MainActivity.java     ← WebView + all features
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_splash.xml
│   │   │   │   └── activity_main.xml
│   │   │   ├── values/
│   │   │   │   ├── strings.xml
│   │   │   │   ├── colors.xml
│   │   │   │   └── themes.xml
│   │   │   └── xml/file_paths.xml
│   │   └── AndroidManifest.xml
│   ├── build.gradle
│   └── proguard-rules.pro
├── build.gradle
└── settings.gradle
```

## URL बदलना है?
`MainActivity.java` में line 28 पर URL change करें:
```java
private static final String WEBSITE_URL = "https://app-hub--lohiyaji302.replit.app";
```

## Push Notifications जोड़ना है?
1. Firebase Console (https://console.firebase.google.com) पर project बनाएं
2. `google-services.json` file download करें और `app/` folder में रखें
3. `app/build.gradle` में add करें:
   ```
   implementation 'com.google.firebase:firebase-messaging:23.4.0'
   ```
4. `FirebaseMessagingService` class बनाएं
