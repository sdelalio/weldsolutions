WELD SOLVER ON THE IPHONE
=========================

WHAT THIS IS
An installable version of the calculator. It gets a home screen icon, opens
full screen with no browser bars, and runs with no signal once installed.
Not an App Store app. See the note at the bottom for why that matters.

FILES
  index.html      the calculator, with the app layer added
  manifest.json   name, icon and colours
  sw.js           offline cache
  icon-*.png      home screen icons

DEPLOY
Drag this whole folder onto the Netlify Deploys tab. Not the files one at a
time, the folder. All of it has to sit in the same place as index.html.

INSTALL ON THE PHONE
  1. Open tools.weldsolutions.com on the phone.
  2. The Install Weld Solver helper appears automatically.
  3. On iPhone: use Share > Add to Home Screen. If "Open as Web App" is
     shown, leave it on, then tap Add.
  4. On supported Android/Chromium browsers: tap the Install Weld Solver
     button when the native install prompt is available.

You now have a Weld Solver icon. Opening it gives the tool full screen with
no address bar, and it works on a plane or in a shielded bay.

UPDATING
Change index.html, then open sw.js and bump the version:

    var CACHE = 'weld-solver-v11';   ->    'weld-solver-v12'

Redeploy the folder. Without the bump, installed phones keep serving the old
cached copy and will not see the change. This is the one step that is easy to
forget.

WHY NOT THE APP STORE
An app that only wraps a web page normally fails Apple review under guideline
4.2, minimum functionality. Getting through would mean a Mac with Xcode, a
99 dollar a year developer account, a rebuild in Capacitor or similar, and a
review cycle for every change. In exchange you would get the same calculator,
a listing, and the ability to charge for it.

Installed this way there is no review, no fee, no Mac, and updates are a drag
onto Netlify. The only real differences are that customers install from a link
rather than searching the store, and there is no push notification. For a
process tool used by you and by people you send it to, the link is better.


INSTALL HELPER ADDED IN V11
The browser version now shows a customer-friendly Install Weld Solver panel
on phones. Installed copies do not show it. If the user closes the panel, a
small Install Weld Solver button remains at the lower-right so it can be
reopened. Android uses the native install prompt when the browser provides it.
