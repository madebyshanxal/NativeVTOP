# VIT-B VTOP Native — Changelog

Versioning is **Version.Revision**. Each release lives in its own folder, named with its stage: V0 to V7 are **alpha** (`V0-alpha` … `V7-alpha`), V8 onward **beta** (`V8-beta`, `V9-beta`, …); each folder's APK carries the same suffix (e.g. `build-output/VTOP-Native-V9-beta.apk`).
A version bump resets the revision to 0.

## V10-beta — 2026-10-29
Major version: V8's look back, and double-tap to reload.
- **Light and dark mode look as they did in V8.** V9's blue, green, aqua and indigo-violet gradients behind every screen are removed: screens use the theme's plain background again, and the sign-in page has V8's soft drifting blobs of the theme's own colours behind its frosted card. Frosted bars, the login glass and all motion are unchanged.
- **Double-tap a tab to reload its page.** Tapping the same tab in the bottom bar (or the slim landscape bar, or the tablet side rail) twice in quick succession reloads that page from VTOP, with a light haptic tick: Time Table, Attendance and Marks fetch their current semester again, Home reloads everything on it (dashboard widgets, photo, sections), and Menu re-reads the portal's sidebar. A single tap still just opens the tab; double-tapping a tab you're not on opens it and reloads it.
- Version stays stage-suffixed: `10.0-beta`, shown in the app as "Version: V10-beta".
- **Release signing**: the V8-beta, V9-beta and V10-beta APKs are now signed with the app's own release key (certificate SHA-256 `70:09:39:69:C0:6F:73:12:B7:5B:A1:E6:3C:D0:54:42:CB:EE:9D:97:30:F6:4F:AF:A9:44:52:E5:88:41:41:10`) instead of the local test (debug) key, and were replaced on GitHub. Their contents are unchanged. Android only updates an app with an APK signed by the same key, so a test-key install (any alpha, or a beta downloaded before this change) must be uninstalled once before installing a release-signed APK; from then on, updates install normally.

## V9-beta — 2026-10-28
Major version: colour behind the glass, everywhere.
- **Blue, green, aqua and indigo-violet gradients** now drift slowly behind every screen (Home, the tabs, Menu, every VTOP module, System status) and the sign-in page, in dark and light mode alike: deeper and richer in dark mode, lighter in light mode so text on the background stays readable. The frosted top and bottom bars, the sign-in card and toggle, and the blur behind sheets and dialogs all show them through the glass.
- One shared drift drives every screen, so the colours carry on where they were when you change screens instead of jumping back to the start; only the backdrop's drawing updates each frame. When the phone's animations are turned off (Developer options › Animator duration scale off), the gradients stay still.
- The sign-in page's backdrop (V8: blobs of the theme's own colours) now uses the same gradients as the rest of the app.
- **Stage in the version**: folders and APKs are now named with their stage (V0–V7 `-alpha`, V8 onward `-beta`). From this build the app itself carries it too: version name `9.0-beta`, and the version chip on the sign-in page and Menu reads "Version: V9-beta". It's set by `appStage` in `app/build.gradle.kts`, next to `appVersion` and `appRevision`, so every future version gets its suffix.

## V8-beta — 2026-10-28
Major version (bug fixes): landscape layout and the Profile page jumping by itself.
- **Profile no longer scrolls up and down by itself in landscape.** VTOP's profile is one big card holding everything; in landscape it sat in the left column of a two-column grid beside an empty one, and the grid kept re-placing it, jumping back and forth with no touch. The card is now opened up: the photo, name and key details form an intro card across the width (photo beside the details when there's room), and Personal, Educational, Family, Proctor and Hostel information flow into two columns. Any page whose only card would sit beside an empty column now gives it the full width (VTOP modules and the generic page layout alike).
- **Landscape top bar**: one row, 8 dp shorter, with "Session Timer:" and its chip inline just before the refresh / sign-out buttons, on every screen (portrait keeps the line under the title).
- **Landscape bottom bar**: a slim bar (64 dp instead of 80) with each icon beside its label, items grouped in the middle on wide screens and spread evenly on narrower ones; landscape phones also use the phone side margin instead of the tablet one.
- **Rotation keeps your place**: rotating or resizing no longer rebuilds the app, so an open VTOP page (and its in-page view), a sheet or the payment gateway page stays exactly as it was instead of reloading or closing.
- Content and the top bar stay clear of a camera cutout or side navigation buttons in landscape.
- **Sign-in page**: a light/dark toggle at the top right (Menu › Appearance still offers "follow the system"); in landscape the brand and the form sit side by side, each scrolling on its own.
- **Sign-in page glass and motion** (portrait and landscape): soft blobs of the theme's colours drift slowly behind the page; the form sits on a frosted glass card that blurs them, and the toggle on a small frosted disc (real blur on Android 12+, a translucent tint below). The logo, form, links and footer rise in one after another; a new captcha fades in over the old one; errors slide in and out; the Sign in label cross-fades to a spinner while VTOP answers; the OTP step slides in; the card resizes smoothly. Only the backdrop's drawing updates each frame, so the page isn't rebuilt while it drifts.
- *Fix (same V8):* the toggle floated over the page, so in landscape the fields scrolled underneath it. It now has its own row above the form (the form scrolls below it, never under it); in portrait it sits at the top of the page and scrolls away with it.
- **Stat tiles**: the label now sits at the bottom of the tile, so a one-line label lines up with the last line of two-line labels beside it; tiles stay the same height everywhere.
- **Full time table grid**: Week grid shows VTOP's whole slot table, every period including the lunch break, every slot named (free ones dimmed), registered classes highlighted with course, type and venue, today's row marked, and separate Theory/Lab tables when VTOP has both. Test: `*TimetableGridTest*`.

## V7-alpha — 2026-10-28
Major version (bug fixes): Back navigation and Online Payments › Pay Now.
- **Back returns to the previous screen, everywhere.** Tabs used to reset the history to Home (e.g. Menu → Time Table → Back went to Home); now every screen opens on top of the one it came from, for the Back button and gesture alike. Inside VTOP modules, Back also undoes views the portal swaps in place (details replacing a list, results replacing a form) before leaving the module.
- **Pay Now opens the payment gateway.** VTOP's response submits a form to the gateway (apps.vitbhopal.ac.in/webapi/webapi/finance/vtopPaymentProcess) and then reloads the portal's dashboard; the app showed that dashboard instead. The gateway now opens in an in-app web page with VTOP's form data (the one place a web page is used), UPI/Paytm/bank-app links open their apps, and you stay on the Payments module.
- **Session timer** moved from the title bar to its own "Session Timer:" line under the title, so the Home header (seal, name, refresh, sign-out) is no longer squeezed.
- **Sign-in page footer**: "VTOP Native", "An unofficial, fully native, Android VTOP client for VIT Bhopal Students.", "(vtop.vitbhopal.ac.in)" and a "Version: V7 · Build: DDMMYYYY" chip (the build date is stamped at build time). The **Menu footer** is the same, with "Signed in as <name> (<registration number>)" above the chip.
- **Frosted glass UI**: the top bar (with the session line) and the bottom navigation bar are frosted glass that content scrolls beneath (real backdrop blur on Android 12+, a translucent tint below); a hairline edge fades in once content is under the bar; screens blur behind sheets, dialogs and the payment page.
- **Smoother, consistent motion**: theme and wallpaper-colour switches fade every colour across; the session timer's seconds roll like a counter and its colour eases to red near the end; the payment page rises in and sinks away; pull-to-refresh and the loading strip sit just under the frosted bar; predictive Back (Android 14+) previews the previous screen.
- **Pay Now, found with the trace:** VTOP answers with a "Merchant Check Out Page" whose form `f1` is submitted by `document.f1.submit()`; the engine didn't support forms by name on `document` (or `document.forms['name']`), so the hand-over silently stopped. Both now work.
- **Equal tile sizes everywhere**: stat tiles (CGPA and credits, attendance, grades, curriculum, time table) all keep room for a two-line label, so tiles side by side — and across screens — are the same height (widths were already equal).
- **Payments › Check Status**: an empty Transaction Details table now lists its columns one per line instead of one run-on line, and the sheet no longer repeats its "TRANSACTION DETAILS" title. Applies to every empty VTOP table with three or more columns.
- In-app web page: if its renderer process dies (low memory), the page closes with a message instead of taking the app down.
- Payment hand-over made sturdier: gateway links are never fetched in the background first (they can be single-use), and hand-over pages that move on via `<body onload>`, `window.onload` or a meta refresh are followed too. Debug builds log module traffic (logcat tag `VtopTrace`) for diagnosing pages.

## V6-alpha — 2026-10-28
Major version (bug fixes): APAAR ID viewing, stuck refreshing / sign-out, plus the requested additions.
- **APAAR ID: "View" now opens your uploaded APAAR PDF.** VTOP was returning the file, but the "Saved · Open" prompt was cancelled the moment it appeared, so nothing seemed to happen. Files VTOP serves for viewing (inline PDFs and images) now open straight in the phone's viewer, with a *Save* option; downloads still go to Downloads/VTOP with an *Open* prompt (this also fixes the prompt for every other module).
- **Never stuck refreshing; sign out always works.** Sign out is instant from Home and Menu (VTOP is told in the background). Requests have a 90-second limit, and Back on a module page leaves it even while a request is still running (it used to wait behind it).
- **Session time**, as on VTOP: a countdown pill on every signed-in screen, restarted by every request VTOP answers; at zero the app signs out for inactivity like the portal.
- **Login**: "Remember password on this device" removed; registration number, password and captcha are always empty after opening the app or signing out (credentials saved by older versions are wiped on update).
- **"made by shanxal"** mark at the bottom centre of the Login, Home and Menu pages (vector, follows the theme).
- **Spot-light** reads notices from wherever VTOP adds them (side-panel categories including new ones, the dashboard block, other lists), with links and VTOP documents; shown near the top of Home, hidden when empty.
- **Contact Us** laid out like VTOP: centred title, card with a coloured header bar, centred body.
- **Profile**: student name centred, large and bold under the photo; the sub-headings inside sections (Current/Permanent Address, School/College Address, Father/Mother Details) now appear as centred bands in a different colour.
- **Credentials and all module pages**: links stay inside their sentence (no stray "." after "Click here", e-mail links no longer jump to the end), bold words are kept, no extra space before punctuation ("per user."), line breaks kept; mailto and bare e-mail links open the mail app.
- Grammar and punctuation pass over the app's own messages; menu label "AAPAR ID Upload" shown as "APAAR ID Upload"; readable "Can't reach VTOP" errors on the login page.
- **Splash and icon**: the seal now sits on a white rounded square (clear on the dark splash) and is rendered from a 1280 px source (no more pixelation); the launcher icon is slightly smaller so no launcher shape crops it.

## V5-alpha — 2026-10-28
Major version (bug fix): sign-in reliability.
- **Fixed "Login failed" with a correct captcha and "Captcha unavailable".** VTOP randomly gives each visit either its image captcha or Google's invisible reCAPTCHA; the reCAPTCHA can't load (VTOP's own security policy blocks it) and that session rejects every typed captcha. The app now recognises those pages and silently restarts the handshake until VTOP serves an image captcha, for the first load, the refresh button and the retry after a failed attempt. It never submits a typed captcha to a reCAPTCHA session.
- Sign in stays disabled until a real captcha image is shown; the empty captcha box says to tap refresh.
- Captcha and page images now decode with `java.util.Base64` (works on-device and in tests).

## V4.1-alpha — 2026-10-28
Revision (UI/UX): branding, fonts, spacing and table styling. App ID unchanged (`dev.shanxal.vtop`), so it upgrades V4 in place.
- Renamed to **VTOP Native**, with "(VIT Bhopal Campus)" under the name on the login and dashboard pages.
- **VIT seal** as the app icon everywhere (launcher, round, themed/monochrome, notification, splash) and on the dashboard header and navigation rail; **VIT Bhopal logo** on the login page.
- Intel One Mono removed; **JetBrains Mono** now covers numbers, codes and tables.
- Text formatting: "LABEL: value" blocks (e.g. Profile's register number / email / programme / school) now show as separate rows instead of one run-on paragraph; bold VTOP text stays bold; comfortable line heights for body and label text; consistent medium spacing.
- **Tables**: boxed cells where VTOP uses bordered tables — the timetable week grid (with class cells highlighted, like VTOP's grid), curriculum, CGPA details and bordered tables in every module; column widths follow the longest line so grids stay even.
- Login form: the register-number hint no longer leaves an empty gap between fields.

## V4-alpha — 2026-10-28
Major version: the app is now fully native — no web view anywhere.
- **Native page engine** replaces the in-app portal view: every VTOP module's page is parsed, its scripts run in a built-in JavaScript-subset interpreter, all requests go from Kotlin to the VTOP backend, and everything is drawn with Compose — forms (incl. date pickers and file uploads), tables, images, buttons, dialogs, modals, downloads and in-page navigation. Tested against all 66 modules of a live account.
- **All data shown**: images on VTOP pages now appear (proctor photo, student photo, signatures, gate-pass barcodes); Profile shows every section; Login History added (Menu › System & account).
- Session cookies moved from the WebView cookie manager to the app's own encrypted store; `androidx.webkit` removed.
- Fixes: a dropped VTOP session (dashboard loads but every module returns 404) is now detected as expired instead of showing errors; pages whose path contains "login" (e.g. login history) were wrongly treated as the sign-in page.
- Home Marks card decluttered (course, score, code, slim bar); larger, consistent spacing throughout.
- VIT Bhopal only: login says so and checks the register number format (e.g. 25BCY10197).

## V3-alpha — 2026-10-28
Major version: data caching fix plus a full design-system and layout overhaul.
- **Caching (fix):** going back to a page no longer reloads it. Screen data is kept in the view model, parsed results in memory, and every VTOP response on disk (app-private, no backup, cleared on sign-out). Saved data shows instantly; it refreshes in the background only when older than 10 minutes, or on pull-to-refresh. When VTOP is unreachable the saved copy stays visible with an "Offline" note, and the app can start offline.
- **Fonts:** Cal Sans (titles/headings), Outfit (body/labels), JetBrains Mono (numbers), Intel One Mono (codes, slots, venues, tables), bundled with their OFL licences.
- **Consistency:** one set of spacing/shape tokens and shared components everywhere — top bars with an eyebrow label, section headers with an accent bar, VTOP cards, compact semester dropdown, one page loader and one inline loader, code chips and mono numbers.
- **Smaller controls:** wavy bars/rings slimmed to the text size; pills, chips, buttons, badges and icons sized to their text.
- **Animations:** page transitions, press feedback on cards, smooth expand/collapse, fade-and-rise for content, animated progress and numbers, cards gliding to new places on width changes.
- **Dark/Light/System theme switch** (Menu › Appearance); status-bar icons follow it. Header uses a softer colour in dark mode.
- **Responsive:** bottom bar on phones, side rail on tablets/foldables/laptops (bottom bar kept on short landscape phones), 1/2/3+ column adaptive grid, centred login form, tables that fill wide cards.
- System Status now re-probes the Student Data Backend once a session exists, so module-page outages show as degraded.
- Clearer messages when VTOP returns an error page (e.g. HTTP 404/5xx); acronyms like CGPA kept in widget titles.

## V2-alpha — 2026-10-28
Major version: rebuilt layout around the VTOP web app, and the app now follows portal changes on its own.
- **Home = VTOP dashboard**: student header with photo, the portal's own dashboard widgets (CGPA & credit status, current-semester course registration, proctor message, spot-light), and key sections for Attendance, Time Table, Marks, Grades, Exam Schedule and Curriculum showing their data.
- **Menu tab mirrors VTOP's sidebar**: group icons, accordion groups, nested sub-menus, search.
- **Follows portal changes**: menu and dashboard widgets are re-read on every start/resume/refresh; native screens are matched to the live menu by path then title; semester endpoints are read from each page; tables are read by column header; unparseable pages fall back to a native rendering of VTOP's page.
- New screens: Curriculum (credit split, earned vs required, full course lists, PDF download), separate Marks, Grades, Exam Schedule and Grade History screens.
- All columns VTOP serves are shown (registration/attendance dates, course option, class average, L/P/J/C credits, …) under *All details*.
- VTOP-style UI: navy palette by default (Material You optional), navy-accented cards, navy table headers, semester dropdown, week grid.
- Fixes: tapping "All VTOP modules" on Home crashed the app (route didn't exist); marks showed Class Average as the Remark; exam schedule could pick the wrong table; pull-to-refresh and loading indicators sat behind the top bar; captcha image was cropped; timetable opened on an empty day on Sundays; "-" placeholders shown as values; long text overflowing pills/rows; status metrics overflowing on narrow screens; a failed refresh replaced loaded data with an error; the day-wise attendance sheet couldn't scroll, hiding older entries; narrow table columns wrapped mid-word.
- Portal view: plain download forms (e.g. "Download Curriculum as PDF") now save natively too.

## V1-alpha — 2026-10-27
Major version: the app ID changed, so V1 installs as a separate app alongside V0 rather than upgrading it (uninstall V0 if you don't want both).
- App ID and Kotlin package renamed `com.vitbnative.vtop` → `dev.shanxal.vtop`.
- Fixed downloads in the portal view. VTOP's `window.open` downloads, hidden-form POST downloads (`PostDownload.js`) and `blob:` links are now saved through a native downloader that uses the signed-in session. Files land in Downloads/VTOP with an *Open* action; an expired session prompts you to sign in again.
- External links (e.g. payment gateways) open in the system browser.

## V0-alpha — 2026-10-27
- First release: native Kotlin/Compose app with Material 3 Expressive, running against the official VTOP backend.
- Login with the official captcha (+ OTP step if VTOP asks for one); session shared between the native screens and the portal view.
- Native screens: Home dashboard, Timetable, Attendance (+ detail), Exam schedule, Marks, Grades, Grade history/CGPA, Profile, read-only info modules.
- Every other VTOP module (all ~67 sidebar entries) reachable through the in-app portal view.
- New System Status page: component health, 30-day uptime bars, uptime %, latency, incidents, outage notifications.
