# 📱 Mobiscan - Remote Device Security Platform

A privacy-focused Android security application for **remote device tracking, location retrieval, and SIM card monitoring** via SMS commands. Works completely offline without internet connectivity.

---

## 🎯 Core Features - Device Security & Tracking

### Remote Phone Finder
- **SMS-Triggered Alarm** - Loud alarm and vibration activated via SMS
- **Maximum Volume Override** - Bypasses silent mode and volume settings
- **Background Operation** - Works even when app is closed
- **Auto-Stop Timer** - Automatically stops after 45 seconds
- **No Internet Required** - Pure SMS-based communication

### GPS Location Tracking
- **Real-Time Coordinates** - Instant GPS location via SMS
- **Google Maps Integration** - Direct map link in SMS response
- **High Accuracy Mode** - Uses best available location provider
- **Multiple Fallbacks** - Last known location if GPS unavailable
- **Location History** - Optional Firebase cloud storage

### Remote Device Lock
- **Instant Lock** - Lock device immediately via SMS
- **Device Admin Integration** - Enhanced security features
- **Emergency Protection** - Quick security mode activation
- **No Physical Access Needed** - Complete remote control

### SIM Card Monitoring
- **Change Detection** - Automatic SIM card change alerts
- **Alternate Number Notification** - SMS alerts to trusted contact
- **Boot Monitoring** - Checks SIM status on device restart
- **Theft Prevention** - Immediate notification if SIM replaced

---

## 🚀 Quick Start

### Install the Application

**Option 1: Install APK (Recommended)**
```bash
adb install app-debug.apk
```

**Option 2: Build from Source**
```bash
cd Mobiscan-via-SMS/Mobiscan_Demo2
./gradlew assembleDebug
adb install app/build/outputs/apk/debug/app-debug.apk
```

Then launch the app and grant permissions.

---

## 📖 How to Use

### Initial Setup

1. **Launch Mobiscan** on your Android device
2. **Grant Permissions** - Tap "REQUEST PERMISSIONS"
   - Location (Allow all the time)
   - SMS (Allow)
   - Phone State (Allow)
   - Notifications (Allow)
3. **Enable Device Admin** - Tap "LOCK DEVICE" → Activate
4. **Set Alternate Number** - Enter trusted contact for SIM alerts
5. **Test Features** - Use in-app buttons to verify functionality

### Find Your Phone via SMS

1. From another phone, send SMS: **`MOBI RING`**
2. Your device will ring at maximum volume
3. Alarm plays for 45 seconds
4. You receive confirmation SMS
5. Done! Follow the sound to find your phone

### Track Location via SMS

1. From another phone, send SMS: **`MOBI LOCATION`**
2. Your device gets GPS coordinates
3. You receive SMS with:
   - Latitude & Longitude
   - Accuracy in meters
   - Google Maps link
   - Timestamp
4. Click the link to see location on map
5. Done! You know exactly where your device is

### Lock Device Remotely

1. From another phone, send SMS: **`MOBI LOCK`**
2. Your device locks immediately
3. You receive confirmation SMS
4. Device is now secured
5. Done! Your data is protected

### Monitor SIM Changes

1. Configure alternate number in app
2. If SIM card is changed:
   - App detects change automatically
   - Sends alert SMS to alternate number
   - Includes new SIM information
   - Attempts to send location
3. Done! You're notified of unauthorized changes

---

## 📁 Project Structure

```
Mobiscan-via-SMS/
├── Mobiscan_Demo2/              # Main Android Project
│   ├── app/
│   │   ├── src/main/
│   │   │   ├── java/com/example/mobiscan_demo2/
│   │   │   │   ├── MainActivity.kt              # Main UI
│   │   │   │   ├── PhoneFinderService.kt        # Alarm service
│   │   │   │   ├── SimTrackingService.kt        # SIM monitoring
│   │   │   │   ├── SmsReceiver.kt               # SMS command processor
│   │   │   │   ├── SimChangeReceiver.kt         # SIM change detector
│   │   │   │   ├── MyDeviceAdminReceiver.kt     # Device admin
│   │   │   │   └── SecurityUtils.kt             # Security utilities
│   │   │   ├── res/
│   │   │   │   ├── layout/                      # UI layouts
│   │   │   │   ├── drawable/                    # Graphics
│   │   │   │   └── values/                      # Strings, colors
│   │   │   └── AndroidManifest.xml              # App configuration
│   │   ├── build.gradle.kts                     # App dependencies
│   │   └── google-services.json                 # Firebase config
│   ├── gradle/                                  # Gradle wrapper
│   ├── build.gradle.kts                         # Project config
│   ├── settings.gradle.kts                      # Project settings
│   └── gradlew                                  # Gradle wrapper script
├── .idea/                                       # Android Studio config
├── BUILD_INSTRUCTIONS.md                        # Build guide
├── DEMO_GUIDE.md                               # Demo walkthrough
└── README.md                                    # This file
```

---

## 🔧 Setup & Installation

### Requirements
- **Android Studio** Hedgehog (2023.1.1) or later
- **JDK** 8 or higher
- **Android SDK** API 34
- **Google Play Services** for location
- **Physical Device** or Emulator with SMS capability

### Installation Steps

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/mobiscan-via-sms.git
cd mobiscan-via-sms
```

2. **Open in Android Studio**
   - Launch Android Studio
   - File → Open
   - Navigate to `Mobiscan-via-SMS/Mobiscan_Demo2`
   - Click OK

3. **Configure Firebase (Optional)**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Create new project
   - Add Android app with package: `com.example.mobiscan_demo2`
   - Download `google-services.json`
   - Place in `app/` directory

4. **Build the Project**
```bash
cd Mobiscan-via-SMS/Mobiscan_Demo2
./gradlew build
```

5. **Install on Device**
```bash
./gradlew installDebug
```

---

## 📨 SMS Commands - Complete Reference

### 🔊 Phone Finder Commands

| Command | Action | Response |
|---------|--------|----------|
| `MOBI RING` | Play loud alarm | "🔊 Ring activated!" |
| `MOBI BUZZ` | Sound + vibration | "🔊 Ring activated!" |
| `MOBI SOUND` | Trigger alarm | "🔊 Ring activated!" |
| `MOBI ALARM` | Maximum volume | "🔊 Ring activated!" |
| `MOBI FINDME` | Full finder mode | "🔊 Ring activated!" |

### 📍 Location Commands

| Command | Action | Response |
|---------|--------|----------|
| `MOBI LOCATION` | Get GPS coordinates | Coordinates + Map link |
| `MOBI WHERE` | Quick location | Coordinates + Map link |
| `MOBI LOCATE` | Fetch GPS | Coordinates + Map link |
| `MOBI GPS` | GPS with accuracy | Coordinates + Map link |
| `MOBI TRACK` | Google Maps link | Coordinates + Map link |

### 🔒 Security Commands

| Command | Action | Response |
|---------|--------|----------|
| `MOBI LOCK` | Lock device now | "� Device locked" |
| `MOBI SECURE` | Security mode | "🔒 Device locked" |
| `MOBI PROTECT` | Emergency lock | "🔒 Device locked" |
| `MOBI EMERGENCY` | Lock + warning | "🔒 Device locked" |

### 📱 SIM & Info Commands

| Command | Action | Response |
|---------|--------|----------|
| `MOBI SIM` | Check SIM status | SIM card information |
| `MOBI SIMSTATUS` | SIM details | SIM card information |
| `MOBI SIMINFO` | SIM information | SIM card information |
| `MOBI HELP` | List commands | All available commands |
| `MOBI INFO` | App information | App details |

---

## 🌐 Access Points

**Main Application:**
- Launch from app drawer: "Mobiscan"
- Package: `com.example.mobiscan_demo2`

**Testing:**
- In-app buttons for local testing
- SMS commands for remote testing

---

## 🔒 Security & Privacy Features

- ✅ **SMS-Based Control** - No internet required
- ✅ **Local Processing** - All data stays on device
- ✅ **Encrypted Storage** - SIM serials hashed with SHA-256
- ✅ **Permission Validation** - Runtime permission checks
- ✅ **No Cloud Dependency** - Works completely offline
- ✅ **Secure Logging** - Sensitive data masked in logs
- ✅ **Device Admin Protection** - Enhanced security features
- ✅ **Background Operation** - 24/7 monitoring

---

## 💡 Technical Details

### Technology Stack
- **Language**: Kotlin
- **Build System**: Gradle (KTS)
- **Min SDK**: 24 (Android 7.0)
- **Target SDK**: 34 (Android 14)
- **Architecture**: Service-based with Broadcast Receivers

### Key Components

**1. SmsReceiver**
- Intercepts incoming SMS messages
- Parses and validates commands
- Triggers appropriate actions
- Sends confirmation responses

**2. PhoneFinderService**
- Foreground service for alarm
- Maximum volume control
- Vibration pattern management
- Auto-stop timer (45 seconds)
- Location retrieval and SMS response

**3. SimTrackingService**
- Monitors SIM card changes
- Detects SIM removal/insertion
- Sends alerts to alternate number
- Includes device location

**4. LocationService**
- FusedLocationProviderClient integration
- Multiple location strategies
- High accuracy mode
- Fallback to last known location
- Google Maps link generation

**5. DeviceAdminReceiver**
- Device administrator privileges
- Remote lock capability
- Enhanced security features

### How It Works

**SMS Command Flow:**
```
1. SMS Received → SmsReceiver intercepts
2. Command parsed and validated
3. Appropriate service started
4. Action performed (ring/locate/lock)
5. Confirmation SMS sent back
```

**Location Tracking Flow:**
```
1. MOBI LOCATION command received
2. PhoneFinderService starts
3. FusedLocationClient requests location
4. GPS coordinates obtained
5. Google Maps link generated
6. SMS sent with location data
7. Optional: Upload to Firebase
```

**SIM Change Detection Flow:**
```
1. SIM card changed/removed
2. SimChangeReceiver detects change
3. SimTrackingService starts
4. Device location obtained
5. Alert SMS sent to alternate number
6. New SIM information included
```

---

## 🛡️ Permissions Required

### Location Permissions
```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_BACKGROUND_LOCATION" />
```

### SMS Permissions
```xml
<uses-permission android:name="android.permission.RECEIVE_SMS" />
<uses-permission android:name="android.permission.READ_SMS" />
<uses-permission android:name="android.permission.SEND_SMS" />
```

### Phone State Permissions
```xml
<uses-permission android:name="android.permission.READ_PHONE_STATE" />
<uses-permission android:name="android.permission.READ_PHONE_NUMBERS" />
```

### System Permissions
```xml
<uses-permission android:name="android.permission.VIBRATE" />
<uses-permission android:name="android.permission.WAKE_LOCK" />
<uses-permission android:name="android.permission.FOREGROUND_SERVICE" />
<uses-permission android:name="android.permission.FOREGROUND_SERVICE_LOCATION" />
<uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />
```

---

## 🧪 Testing

### Test Phone Finder

1. **Local Test:**
```
- Open app
- Tap "🔊 RING" button
- Verify alarm sounds
- Verify vibration works
- Alarm stops after 30 seconds
```

2. **SMS Test:**
```
- From another phone, send: MOBI RING
- Verify device rings
- Verify confirmation SMS received
- Verify alarm stops after 45 seconds
```

### Test Location Tracking

1. **Local Test:**
```
- Open app
- Enable GPS
- Tap "📍 GET LOCATION" button
- Verify coordinates displayed
- Verify Google Maps link works
```

2. **SMS Test:**
```
- From another phone, send: MOBI LOCATION
- Wait 5-10 seconds
- Verify SMS received with:
  ✓ Latitude & Longitude
  ✓ Accuracy
  ✓ Google Maps link
  ✓ Timestamp
- Click link to verify location
```

### Test Remote Lock

1. **Local Test:**
```
- Open app
- Tap "🔒 LOCK DEVICE"
- Activate Device Admin if prompted
- Tap button again
- Verify device locks
```

2. **SMS Test:**
```
- From another phone, send: MOBI LOCK
- Verify device locks immediately
- Verify confirmation SMS received
- Unlock device normally
```

### Test SIM Monitoring

1. **Setup:**
```
- Open app
- Enter alternate phone number
- Tap "SAVE ALTERNATE NUMBER"
- Tap "REFRESH SIM STATUS"
- Note current SIM serial
```

2. **Test SIM Change:**
```
- Power off device
- Remove SIM card
- Insert different SIM
- Power on device
- Wait 30-60 seconds
- Check alternate number for alert SMS
```

---

## 🆘 Troubleshooting

**App won't install:**
- Check Android version (need 7.0+)
- Enable "Install from Unknown Sources"
- Verify APK is not corrupted

**Permissions not granted:**
- Go to Settings → Apps → Mobiscan → Permissions
- Manually enable all permissions
- For background location: Select "Allow all the time"

**SMS commands not working:**
- Verify SMS permissions granted
- Check device has cellular signal
- Ensure command format is correct (e.g., "MOBI RING")
- Try restarting the app

**Location not available:**
- Enable GPS in device settings
- Grant location permissions
- Move to area with better GPS signal
- Wait longer for GPS fix (up to 30 seconds)

**Device won't lock:**
- Enable Device Administrator:
  - Open app → Tap "LOCK DEVICE"
  - Tap "Activate" on Device Admin screen
- Check no other admin apps conflict

**SIM change not detected:**
- Verify alternate number is saved
- Check phone permissions granted
- Ensure device has signal with new SIM
- Wait up to 2 minutes for detection

**Alarm not loud enough:**
- Check device not in silent mode
- Increase alarm volume in system settings
- Disable Do Not Disturb mode
- Test with different ringtone

---

## 📝 Important Notes

### Critical Information
- **Save SMS Commands** - Keep a list of commands handy
- **Test Before Emergency** - Verify all features work
- **Alternate Number** - Must be a trusted contact
- **Device Admin** - Required for remote lock
- **Battery** - Keep device charged for tracking
- **Cellular Network** - Required for SMS functionality

### Limitations
- Requires active cellular network
- GPS accuracy varies by location
- Some features need Device Admin
- Background location restricted on Android 10+
- SMS commands must match exact format
- Maximum 45-second alarm duration

### Best Practices
- Test all features after installation
- Keep alternate number updated
- Enable all permissions
- Keep device charged
- Test in different locations
- Save encryption keys securely

---

## 🎯 Use Cases

### Personal Security
- **Lost Phone Recovery** - Find misplaced device at home
- **Theft Prevention** - Lock device if stolen
- **Location Sharing** - Share location in emergency
- **SIM Monitoring** - Detect unauthorized SIM changes

### Family Safety
- **Child Safety** - Track family member's device
- **Elderly Care** - Locate elderly family members
- **Emergency Response** - Quick location in emergencies

### Research & Education
- **Android Development** - Learn service architecture
- **Security Research** - Study SMS-based security
- **Location Services** - Understand GPS integration
- **Broadcast Receivers** - Learn event handling

---

## 🚀 Quick Commands

```bash
# Build the project
cd Mobiscan-via-SMS/Mobiscan_Demo2
./gradlew build

# Install on device
./gradlew installDebug

# Uninstall from device
adb uninstall com.example.mobiscan_demo2

# View logs
adb logcat | grep Mobiscan

# Check installed version
adb shell pm list packages | grep mobiscan

# Clear app data
adb shell pm clear com.example.mobiscan_demo2
```

---

## 📚 Documentation

- **README.md** (this file) - Main documentation
- **BUILD_INSTRUCTIONS.md** - Detailed build guide
- **DEMO_GUIDE.md** - Step-by-step demo walkthrough
- **DEMO_CHECKLIST.md** - Testing checklist

---

## 🔐 Privacy & Security

This application is designed with privacy in mind:

- ✅ No telemetry or tracking
- ✅ No data sent to third parties
- ✅ All processing happens on device
- ✅ No cloud storage by default
- ✅ SIM serials hashed before storage
- ✅ Sensitive data masked in logs
- ✅ Open source - verify the code yourself
- ✅ No ads or monetization

### Data Collection
**What we collect:**
- GPS location (only when commanded)
- SIM card status (for change detection)
- Device status (for security features)

**What we DON'T collect:**
- Personal messages or calls
- Contacts or photos
- Browsing history
- App usage data
- Any data without your command

---

## ⚠️ Legal Disclaimer

### Authorized Use Only
- ✅ Use only on devices you own
- ✅ Get explicit permission before tracking others
- ✅ Comply with local privacy laws
- ❌ Don't use for unauthorized surveillance
- ❌ Don't use for stalking or harassment
- ❌ Don't violate privacy rights

### Developer Responsibility
- This app is for legitimate security purposes
- Users are responsible for legal compliance
- Developer not liable for misuse
- Intended for anti-theft and device recovery

---

**Built with Kotlin, Android SDK, and Google Play Services**

**For device security, anti-theft protection, and educational purposes**

---

## Core Focus: Device Security & Tracking ⭐
## Additional: SIM Card Monitoring & Remote Control

**Version:** 1.0.0 (Phase 1)  
**Last Updated:** December 2024  
**License:** MIT

---

### 🔜 Coming Soon (Phase 2)
- 📸 Remote camera capture
- 🎤 Audio recording
- 📊 Activity monitoring
- 🌐 Web dashboard
- 🔔 Advanced notifications
- 📱 Multi-device support
