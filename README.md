# VTOP Native (VIT Bhopal Campus)

An unofficial, **fully native** Android app for VIT Bhopal's VTOP portal ([vtop.vitbhopal.ac.in](https://vtop.vitbhopal.ac.in/vtop)), **for VIT Bhopal University students only**. Sign in with your normal VTOP login and captcha, and see attendance, time table, marks, grades, exams, curriculum and every other VTOP module in clean native screens that load fast and still work offline.

**Latest version:** V10-beta · [Changelog](CHANGELOG.md)

> This repository hosts the app's releases, this README and the changelog. The app is **closed source**; its source code is not published here.

## Download and install

1. Open the [latest release](https://github.com/madebyshanxal/NativeVTOP/releases/latest) on your phone and download `VTOP-Native-V<version>.apk` (for example `VTOP-Native-V10-beta.apk`).
2. Open the downloaded file. If Android asks, allow your browser or Files app to **install unknown apps**.
3. Tap **Install**, then open **VTOP Native**.

**Updating:** install the newer APK over the old one; your settings and theme are kept. You sign in again only when VTOP has ended your session.

**Requirements:** Android 8.0 or newer, an internet connection, and a VIT Bhopal VTOP account.

## What it does

| | |
|---|---|
| **Sign-in** | The same as the website: registration number, password and VTOP's own captcha, plus the OTP step when VTOP asks for one. Nothing is remembered; the fields are always empty when you open the app or sign out. |
| **Home** | Your photo, name, register number and programme; VTOP's system status; the portal's own dashboard widgets (course registration, CGPA and credits, proctor message, Spot-light notices); then Attendance, Time Table, Marks, Grades, Exam Schedule and Curriculum at a glance. |
| **Attendance** | Per semester: overall %, a ring per course, how many classes you can skip or must attend to stay at 75 %, debar status, and a day-wise sheet (present, absent, on duty). |
| **Time Table** | Today's classes with the one in progress highlighted, the full week grid exactly like VTOP's (every period including lunch, every slot named, your classes highlighted, today marked), and your registered courses with credits, faculty and status. |
| **Marks and grades** | Every assessment with max, weightage, scored, weighted and class average; per-semester grades with credits; an estimated GPA; Grade History with CGPA and curriculum progress. |
| **Exams and curriculum** | Exam schedule with the nearest exam first and a countdown, venue and seat; curriculum credits per category, earned against required, and the curriculum PDF. |
| **Profile** | Your full VTOP profile with photo; on wide screens and in landscape the sections sit side by side. |
| **Every other module** | Every module in VTOP's menu opens natively: forms, file uploads, tables, receipts, gate passes, QR codes, confirmations and downloads (saved to Downloads/VTOP). New modules VTOP adds show up on their own. |
| **Fee payments** | *Pay Now* opens VIT's payment gateway inside the app; UPI, Paytm and bank apps open as usual. This is the only web page in the app; VTOP itself is never shown as a web page. |
| **System Status** | Checks whether VTOP's portal, login, captcha and student data are up, with 30-day uptime, response times, incidents, and optional notifications when something goes down. |
| **Session timer** | Shows the minutes left before VTOP's 20-minute idle sign-out, like the portal's header; tap it to restart the countdown. |
| **Offline** | Pages you've opened are saved on your phone, so they open instantly and still show (marked "Offline") when VTOP can't be reached. |
| **Reload** | Pull down on any page, or **double-tap its tab** in the bottom bar, to fetch it from VTOP again. |
| **Look and feel** | Material 3 Expressive design with VTOP's navy colours, light and dark mode (or follow the system), optional wallpaper colours, frosted glass bars, and smooth animations. Works in portrait and landscape, on phones, foldables and tablets. Back always returns to the previous screen. |

## Privacy and security

- The app talks **only to VIT Bhopal's servers**: VTOP, and VIT's payment gateway when you pay fees. There are no analytics, no ads and no third-party servers.
- Your **password is never saved**. Your VTOP session is kept in the app's encrypted storage, and saved pages stay in the app's private storage; both are deleted when you sign out.
- Permissions: **Internet**, and **Notifications** (optional, only for System Status alerts).

## Versions

Versions are numbered **Version.Revision** with a stage suffix: V0 to V7 were **alpha**; V8 onward are **beta** (for example V10-beta, shown in the app as "Version: V10-beta · Build: DDMMYYYY"). Every change is listed in the [changelog](CHANGELOG.md).

## Known limits

- The captcha is typed by you; the app doesn't solve it.
- Features that need a full browser engine (canvas charts, browser printing) aren't reproduced.
- System Status measures VTOP from your own phone's connection.
- The GPA on the Grades screen is an estimate from letter grades; your official CGPA is shown as VTOP publishes it.

## Disclaimer

VTOP Native is an **unofficial** app. It is not made, endorsed or supported by VIT Bhopal University or its Software Development Cell. VTOP, VIT and their logos belong to their owners. All data in the app comes live from VTOP and is shown as VTOP serves it.

---

© 2026 madebyshanxal. All rights reserved.
