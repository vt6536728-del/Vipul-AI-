# VIPUL AI – PERSONAL ASSISTANT
## Motorola G67 Power 5G (Android 16 / Hello UI) Build & Setup Guide

### Target Device Profile:
- **Device**: Motorola G67 Power 5G
- **Chipset**: Qualcomm Snapdragon 7s Gen 2
- **OS**: Android 16 (Target SDK 35/36, compileSdk 35)
- **UI Skin**: Motorola Hello UI

---

### Step 1: Open and Compile APK in Android Studio
1. Extract `VIPUL_AI_Motorola_G67_APK_Project.zip`.
2. Open Android Studio (Ladybug or newer with JDK 17).
3. Select **Open** and select the extracted folder.
4. Run in Terminal:
```bash
./gradlew assembleDebug
```
The APK will be generated at:
`app/build/outputs/apk/debug/app-debug.apk`

To build the optimized release APK:
```bash
./gradlew assembleRelease
```

---

### Step 2: Install via ADB on Motorola G67 Power 5G
1. Enable USB Debugging on your Motorola G67:
   - Go to **Settings > About Phone > Tap 'Build Number' 7 times**.
   - Go to **Settings > System > Developer Options > Enable USB Debugging**.
2. Connect your phone via USB and run:
```bash
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

---

### Step 3: Required Android 16 Permissions Setup
1. **Microphone**: Allow runtime microphone permission for continuous voice commands.
2. **Phone & Contacts**: Allow for zero-touch contact searches and dialing.
3. **Background Wake Word Service**:
   - Turn ON the **WAKE** toggle in the top bar.
   - On Motorola Hello UI, go to **Settings > Battery > Background App Management** and set VIPUL AI to **Unrestricted** so Motorola does not terminate the background listener.
4. **WhatsApp Automation (Accessibility Service)**:
   - Go to **Settings > Accessibility > Downloaded Apps > VIPUL AI Accessibility Service > Turn ON**.
   - This allows VIPUL AI to type and send your dictated messages after you confirm.
5. **Telecom Incoming Call Management**:
   - If prompted, allow VIPUL AI as a call assistant / companion service to enable voice commands like *"Hey Vipul, incoming call uthao"* and *"call reject karo"*.
6. **Hindi Voice Pack**:
   - Go to **Settings > System > Languages & Input > Text-to-speech output > Google Speech Services > Install voice data > Hindi (India) > Voice 1 (Female)**.
