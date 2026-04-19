# MikoMaestroMobile — Maestro Automation Framework

Maestro automation test suite for the **Miko App** (`com.miko3.app`).
Covers 29 Maestro scripts mapped across 147 sanity test cases (TC_001–TC_147).

---

## 📊 Coverage Summary

| Type                                  | Count | % of Total |
|---------------------------------------|-------|------------|
| Total TCs                             | 147   | 100%       |
| 🟢 Fully Automatable                  | 55    | 37%        |
| 🟡 Semi-Automatable                   | 27    | 18%        |
| 🔴 Manual Only                        | 65    | 44%        |
| ⚠️ Pending (automatable, not scripted) | 4    | 3%         |

---

## 🔑 Test Accounts

| Owner    | Account                           | Region   | Passcode | Device    |
|----------|-----------------------------------|----------|----------|-----------|
| Aslam    | girish.shetty+betaaind01@miko.ai  | IND      | 0000     | Miko Mini |
| Aslam    | girish.shetty+betaase01@miko.ai   | ASE/Beta | —        | —         |
| Aslam    | aditya.kamble+apr16@miko.ai       | IND      | 1111     | Miko Mini |
| Vishakha | Vishakha+betaus0407@miko.ai       | US/ROW   | 1111     | —         |
| Vishakha | Vishakha+spanishmex0106@miko.ai   | US/ROW   | —        | —         |

---

## ⚠️ Known Issues

| Issue                                           | Script                          | Status       |
|-------------------------------------------------|---------------------------------|--------------|
| Country search doubleTapOn fails                | Signup_page.yaml                | ❌ FAILING   |
| Blog longPressOn id_blog_what_is_miko_max fails | Explore_and_Blogs.yaml          | ❌ FAILING   |
| Banner tap fails due to animation               | Homepage_Banner_and_Checklist   | ⚠️ SKIPPED  |
| id_scrollable_bar longPress broken              | ProfileandTuneListeningMiko     | ⚠️ KNOWN BUG|
| Daily Rewards toggle longPressOn 86%,10% fails  | Miko_Shield.yaml                | ❌ FAILING   |
| doubleTapOn PM saves alarm as AM                | Set_Alarm.yaml                  | ⚠️ KNOWN BUG|
| Help icon has no element ID                     | Help_Section_Nonmax_user.yaml   | ⚠️ Fragile  |
| Coordinate taps 91%,88% are resolution-dependent | Daily_Login_Bonus.yaml         | ⚠️ Fragile  |

---

## 🚫 Why Certain Tests Are Manual Only

- **Physical BOT required** — Mikonnect calls, obstacle/charger detection, StoryMaker from BOT
- **VPC Consent** — Signup/Onboarding (IN/US/ROW/AUS) requires manual parental consent
- **Payment gateway** — Chargebee cannot be automated (TC_131, TC_134–TC_138)
- **KidsZone** — Navigation 2.0, Talents, Learning Adventure, Munchy's World not yet scripted
- **Fresh account state** — Introduction videos and first-time Login Bonus require a clean account
