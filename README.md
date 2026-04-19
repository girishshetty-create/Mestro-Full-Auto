MikoMaestroMobile/

├── config/                       # Environment & device configurations

├── tests/                        # Test suites (sanity, smoke, regression, deeplink)

├── pageObjects/                  # Page Object Model (POM) files

├── utils/                        # Helper utilities & reusable functions

├── reports/                      # Test execution reports (HTML/JSON)

├── data/                         # Test data files

├── docs/                         # Documentation & setup guides

├── package.json                  # Project dependencies

└── README.md                     # Project documentation
# MikoMaestroMobile — Maestro Automation Framework


1. What is Maestro?
Maestro is an open-source mobile UI testing framework built for Android and iOS. It lets you write human-readable YAML test flows — no coding required — that simulate real user interactions on a device or emulator.

Key strengths: YAML syntax, fast execution, deep-link support, built-in retry/wait, and a cloud runner (Maestro Cloud).

Feature	Details
Language	YAML (no code needed)
Platforms	Android & iOS
Execution	Local device / emulator or Maestro Cloud
Retry logic	Built-in animation waits & optional steps
Deep links	Supported natively via openLink command

2. Prerequisites
2.1  System Requirements
Requirement	Details
Operating System	macOS, Linux, or Windows (WSL2 recommended)
Java	JDK 11 or later  (java -version to verify)
Node.js (optional)	v16+ if using Maestro Studio or JS scripts
Android device/emulator	Android 7+ with USB debugging enabled
iOS device (macOS only)	iOS 15+ with Developer Mode on
ADB	Included in Android Studio / Platform-tools

2.2  Install Maestro CLI
Run the one-line installer in your terminal:

curl -Ls 'https://get.maestro.mobile.dev' | bash

After install, reload your shell and verify:

maestro --version

✅ TIP	If the command is not found, add ~/.maestro/bin to your PATH:   export PATH="$PATH:$HOME/.maestro/bin"

2.3  Android Setup
1.	Install Android Studio from developer.android.com/studio
2.	Enable USB Debugging: Settings → Developer Options → USB Debugging
3.	Connect device via USB or start an emulator
4.	Verify ADB sees the device:
  adb devices
5.	You should see your device listed as 'device' (not 'unauthorized')

⚠️ NOTE	If the device shows 'unauthorized', tap 'Allow USB Debugging' on the phone screen and run adb devices again.

2.4  iOS Setup  (macOS only)
6.	Install Xcode from the Mac App Store
7.	Enable Developer Mode on iPhone: Settings → Privacy & Security → Developer Mode
8.	Trust the Mac: Settings → General → VPN & Device Management → Trust
9.	Install ios-deploy: npm install -g ios-deploy
10.	Connect via USB and verify: idevice_id -l

4.1  Run the Full Suite
Navigate to the maestro/ folder and execute:

maestro test All1Beta_PageModules.yaml

This runs all 5 flows in sequence. Because each flow is marked optional: true, a failure in one flow will not block the rest from running.

4.2  Run a Single Flow
You can run any individual flow independently:

maestro test flows/test_login.yaml
maestro test flows/test_child_profile.yaml
maestro test flows/test_city_dunk.yaml
maestro test flows/test_intermediate.yaml
maestro test flows/test_mikonnect.yaml

6. Troubleshooting
Device Not Found
ERROR	'No connected devices found'  →  Run adb devices (Android) or idevice_id -l (iOS) to confirm connection. For Android, ensure USB Debugging is on.

•	Android: unplug and replug the USB cable, then accept the trust dialog on the phone
•	Emulator: open Android Studio → Device Manager → start an AVD



## 🔑 Test Accounts

| Owner    | Account                           | Region   | Passcode | Device    |
|----------|-----------------------------------|----------|----------|-----------|
| Aslam    | girish.shetty+betaaind01@miko.ai  | IND      | 0000     | Miko Mini |
| Aslam    | girish.shetty+betaase01@miko.ai   | ASE/Beta | —        | —         |
| Aslam    | aditya.kamble+apr16@miko.ai       | IND      | 1111     | Miko Mini |
| Vishakha | Vishakha+betaus0407@miko.ai       | US/ROW   | 1111     | —         |
| Vishakha | Vishakha+spanishmex0106@miko.ai   | US/ROW   | —        | —         |


## 🚫 Why Certain Tests Are Manual Only

- **Physical BOT required** — Mikonnect calls, obstacle/charger detection, StoryMaker from BOT
- **VPC Consent** — Signup/Onboarding (IN/US/ROW/AUS) requires manual parental consent
- **Payment gateway** — Chargebee cannot be automated (TC_131, TC_134–TC_138)
- **KidsZone** — Navigation 2.0, Talents, Learning Adventure, Munchy's World not yet scripted
- **Fresh account state** — Introduction videos and first-time Login Bonus require a clean account
