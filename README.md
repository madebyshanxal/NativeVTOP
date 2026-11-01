<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img src="assets/banner-light.svg" alt="VTOP Native (VIT Bhopal Campus): the VIT seal, the app's name and the VIT Bhopal logo" width="100%">
</picture>

**VTOP, rebuilt as a real Android app.** VTOP Native is an unofficial, fully native app for VIT Bhopal's VTOP portal ([vtop.vitbhopal.ac.in](https://vtop.vitbhopal.ac.in/vtop)). It signs in with your own VTOP login and VTOP's own captcha, talks directly to the official VTOP backend, and shows everything in fast, clean Material 3 Expressive screens instead of a desktop site squeezed onto your phone. It's **for VIT Bhopal University students only**.

- **Your day at a glance**: today's classes with the one in progress highlighted, attendance with "can skip / must attend" counts, marks, grades, exam countdowns and curriculum progress
- **The whole portal, natively**: every module in VTOP's menu opens as a native screen, with forms, uploads, receipts, gate passes and downloads; VTOP is never shown as a web page
- **Always in step with VTOP**: the menu and dashboard are read live, so when the SDC team adds or moves something, the app follows
- **Fast and offline-ready**: pages open instantly from what the app has saved and stay readable when VTOP is down; pull down or **double-tap a tab** to reload
- **System Status**: tracks VTOP's uptime and can notify you when it goes down, without mistaking your own bad signal for a VTOP outage
- **Made for every screen**: dark and light themes, frosted-glass bars, smooth motion, and layouts for phones, foldables, tablets and laptops

Not affiliated with VIT. Your credentials go only to `vtop.vitbhopal.ac.in`.

> [!IMPORTANT]
> **We don't collect any user or VTOP data, and none of the students' data is visible to us.** VTOP Native is only an Android-native VTOP client: it runs on your phone and talks to VIT Bhopal's own servers (and to GitHub, for app updates). The only things that ever reach us are what you choose to send: feedback and bug reports you write, and app crash reports if you turn them on (app errors only, never VTOP data or cookies). There's no account, analytics or tracking.

**Latest version:** V12.2-release · **Status: Stable** · [Changelog](CHANGELOG.md)

> This repository hosts the app's releases (APKs), this README, the changelog, the [licence](LICENSE) and [third-party notices](NOTICE). The app is **closed source**; its source code is not published here.

## Project status: Stable

**V11-release is the first stable release.** After the alpha series (building the app) and the beta series (polish and fixes, ending in system stability), every version from V11 on is a stable release with the `-release` suffix, and the app now keeps itself up to date from this page.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/version-timeline-dark.svg">
  <img src="assets/version-timeline-light.svg" alt="Version timeline: V0 to V7 alpha (27–28 Oct 2026), V8 to V10.2 beta (28–29 Oct 2026), V11 to V12.2 release (1 Nov 2026, V12.2 latest, stable)." width="100%">
</picture>

| Stage | Versions | What it meant |
|---|---|---|
| **Alpha** | V0 – V7 | Building the app: sign-in, native screens for every module, offline caching, System Status, the design system |
| **Beta** | V8 – V10.2 | Polish and fixes on a complete app; release-signed APKs from V8 on; ended in system stability |
| **Release** | V11 onward (latest: V12.2) | Stable versions, named `V<n>-release`, with in-app updates |

## Download and install

1. Open the [latest release](https://github.com/madebyshanxal/NativeVTOP/releases/latest) on your phone and download `VTOP-Native-V<version>.apk` (for example `VTOP-Native-V12.2-release.apk`).
2. Open the downloaded file. If Android asks, allow your browser or Files app to **install unknown apps**.
3. Tap **Install**, then open **VTOP Native**.

**Updating:** from V11 on, the app updates itself. Every time it starts, and in the background twice a day (with an "Update available" notification that opens the update), it checks this page for a newer version and shows what's new with **Download & install**; the download is checked (checksum, and that it's signed with the app's release key) and Android asks you to confirm. Afterwards the app reopens by itself on the new version. On Android 14 and newer that needs one optional permission, **Display over other apps** (turn on **Reopen after updating** in Settings › App updates, or tap **Allow** in the update popup); without it, a "VTOP Native updated · Tap to open" notification takes you straight back. The first time, Android asks you to allow VTOP Native to install apps. You can also check any time in Menu › Updates & Feedback or Settings. Updating keeps your settings; you sign in again only when VTOP has ended your session. Coming from V10.2-beta or older, install V11 once by hand (download it from the releases page).

**Coming from an alpha, or a beta downloaded before 29 Oct 2026?** Those builds were signed with a temporary test key, and Android only updates an app with an APK signed by the same key. Uninstall the old app first, then install the new one (this clears its saved data; just sign in again).

**Checking the APK is genuine:** every release from V8-beta on is signed with the app's release key, certificate SHA-256
`70:09:39:69:C0:6F:73:12:B7:5B:A1:E6:3C:D0:54:42:CB:EE:9D:97:30:F6:4F:AF:A9:44:52:E5:88:41:41:10`.
Any APK with a different certificate didn't come from this page.

**Requirements:** Android 8.0 or newer, an internet connection, and a VIT Bhopal VTOP account.

## What it does

| Feature | What you get |
|---|---|
| **Sign-in** | The same as the website: registration number, password and VTOP's own captcha, plus the OTP step when VTOP asks for one. Nothing is remembered; the fields are always empty when you open the app or sign out. VTOP's **Forgot Password**, **Forgot LoginId** and **Login Issue** are under the Sign in button as native pages, with the same steps, fields and messages as on the website and **Back to login** on each. |
| **Home** | Your photo, name, register number and programme; VTOP's system status; the portal's own dashboard widgets (course registration, CGPA and credits, proctor message, Spot-light notices, whose links to VIT Bhopal's other sites, like the end-semester feedback forms, open inside the app); then Attendance, Time Table, Marks, Grades, Exam Schedule and Curriculum at a glance. |
| **Attendance** | Per semester: overall %, a ring per course, how many classes you can skip or must attend to stay at 75 %, debar status, and a day-wise sheet (present, absent, on duty). |
| **Time Table** | Today's classes with the one in progress highlighted, the full week grid exactly like VTOP's (every period including lunch, every slot named, your classes highlighted, today marked), and your registered courses with credits, faculty and status. |
| **Marks and grades** | Every assessment with max, weightage, scored, weighted and class average; per-semester grades with credits; an estimated GPA; Grade History with CGPA and curriculum progress. |
| **Exams and curriculum** | Exam schedule with the nearest exam first and a countdown, venue and seat; curriculum credits per category, earned against required, and the curriculum PDF. |
| **Profile** | Your full VTOP profile with photo; on wide screens and in landscape the sections sit side by side. |
| **Every other module** | Every module in VTOP's menu opens natively: forms, file uploads, tables, receipts, gate passes, QR codes, confirmations and downloads (saved to Downloads/VTOP). New modules VTOP adds show up on their own. |
| **Fee payments** | *Pay Now* opens VIT's payment gateway inside the app; UPI, Paytm and bank apps open as usual. Only pages from other sites (this gateway, and VIT Bhopal sites linked from Spot-light) ever open as web pages, each with **Reload** and a **Desktop site** switch; VTOP itself is never shown as a web page. |
| **System Status** | Checks whether VTOP's portal, login, captcha and student data are up, with 30-day uptime, response times, incidents, and optional notifications when something goes down. When you're offline or on a weak signal, it says so instead of reporting VTOP as down. |
| **Session timer** | Shows the minutes left before VTOP's 20-minute idle sign-out, like the portal's header; tap it to restart the countdown. |
| **Offline** | Pages you've opened are saved on your phone, so they open instantly and still show (marked "Offline") when VTOP can't be reached. |
| **Settings** | Theme (system, light, dark) with a smooth cross-fade when you switch, wallpaper colours, app updates (and reopening after them), System Status and outage alerts, Refresh (reloads everything and shows its progress and result), offline copies, opt-in crash reports, feedback and About. In Menu, and on the sign-in page. |
| **Feedback & bug reports** | Send feedback (with a star rating), report a bug (with an optional screenshot) or request a feature, on a native page built into the app (no web page inside it). App version, Android version and device model are filled in, and you can leave them out. In Menu › Updates & Feedback and in Settings. |
| **Crash reports** | Off unless you turn them on in Settings. No user/VTOP data or cookies are collected; only app crash/bug/error data (app version, Android version, device model and where in the app's code it crashed), for fixing bugs. Opting in really helps: see the note below. |
| **Updates** | Checks for a new version every time the app starts (and in the background, with a notification) and shows what's new; downloads, checks and installs it in-app. "What's new" shows once after each update. |
| **Reload** | Pull down on any page, or **double-tap its tab** in the bottom bar, to fetch it from VTOP again. Double-tapping **Menu** scrolls it back to the top. |
| **Look and feel** | Material 3 Expressive design with VTOP's navy colours, light mode and a dark mode in deep steel shades on a minimal gradient (or follow the system), optional wallpaper colours, frosted glass bars, and smooth animations. Works in portrait and landscape, on phones, foldables and tablets. Back always returns to the previous screen. |

## Privacy and security

**We don't collect any user or VTOP data, and none of the students' data is visible to us.** This is only an Android-native VTOP client: everything you see comes straight from VTOP to your phone and stays on your phone. Nothing reaches us unless you send it.

- **Your credentials go only to `vtop.vitbhopal.ac.in`.** The app talks to VIT Bhopal's servers: VTOP; VIT's payment gateway when you pay fees; VIT Bhopal's other sites (such as `apps.vitbhopal.ac.in`) when you open a Spot-light notice that links to them; and VIT Bhopal's main website (`vitbhopal.ac.in`, an empty request) when System Status needs to tell a weak connection from a VTOP outage. It also contacts **GitHub** (this page) to check for and download app updates, and VTOP Native's own **feedback portal** (`vtop-native-feedback.pages.dev`, on Cloudflare) only when you send feedback, or crash reports if you turned them on. Nothing about you or your VTOP account is ever sent.
- **Feedback and bug reports** contain only what you type, an optional screenshot you pick, an optional email (if you'd like a reply), and the app version, Android version and device model (which you can leave out). Spam is kept out natively (the app proves it's the real app and does a moment of work on the phone for each report) and by an hourly limit; your IP address isn't stored.
- **Crash reports** are off unless you turn them on in Settings. A report holds the app version, Android version, device model and where in the app's own code it crashed; error messages, VTOP data and cookies are never included. Turning them off deletes any that haven't been sent.

> **A note from the developer:** Heyy, Shanzal here, developer of this app. I am requesting you as a developer to please Opt-In for Crash Reports as it helps me to find out and fix all the unexpected bugs, errors, and crashes much more quicker so you can get a much more smooth, lag-free, & intuitive experience while using the app. I don't collect any user or VTOP data or cookies, only the app-related data. Thanx for reading by, hope you understand :)
- Your **password is never saved**. Your VTOP session is kept in the app's encrypted storage, and saved pages stay in the app's private storage; both are deleted when you sign out.
- Permissions: **Internet**, and **Notifications** (optional, only for System Status alerts).

## Versions

Versions are numbered **Version.Revision** with a stage suffix: V0 to V7 were **alpha**; V8 to V10.2 were **beta**; from V11 every version is a stable **release** (`V11-release`, `V11.1-release`, …; shown in the app as "Version: V11-release · Build: DDMMYYYY"; a revision such as .1 means small fixes and UI tweaks). Every change is listed in the [changelog](CHANGELOG.md).

## Known limits

- The captcha is typed by you; the app doesn't solve it.
- Features that need a full browser engine (canvas charts, browser printing) aren't reproduced.
- System Status measures VTOP from your own phone; checks made with no or a poor connection are skipped rather than counted as outages.
- The GPA on the Grades screen is an estimate from letter grades; your official CGPA is shown as VTOP publishes it.

## Disclaimer

VTOP Native is an **unofficial** app. It is not affiliated with, endorsed by, or connected to VIT Bhopal University or its Software Development Cell. "VTOP" and "VIT" and their logos belong to their respective owners. All data in the app comes live from VTOP and is shown as VTOP serves it.

## License

The app is distributed free of charge as a compiled APK only, for personal, non-commercial use; copying, modifying, decompiling, repackaging or redistributing it needs written permission. See [LICENSE](LICENSE) for the full terms and [NOTICE](NOTICE) for the third-party components it uses.

---

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/madebyshanxal-dark.svg">
    <img src="assets/madebyshanxal-light.svg" alt="made by shanxal" width="200">
  </picture>
  <br>
  <sub>© 2026 Shanzal Firoz. All rights reserved.</sub>
</p>
