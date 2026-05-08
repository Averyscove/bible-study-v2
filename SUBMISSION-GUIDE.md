# Submission guide — what's left between you and the App Store

> **Read this top to bottom once before doing anything.** Then come back and check things off.

I've finished everything that doesn't require your Apple ID password, your Mac password, or you tapping a real iPhone. What's below is the human-in-the-loop part. Total time, if everything goes smoothly: **~2 hours of your active attention spread across 1–4 days** (the calendar time stretches because of Apple's review queue).

## Where everything is right now

| Asset | Status | Location |
|---|---|---|
| Web app | ✅ Live | https://averyscove.github.io/bible-study-v2/ |
| iOS Xcode project | ✅ Ready | `v2/ios/App/App.xcworkspace` |
| App icon (all 18 iOS sizes) | ✅ Generated | `v2/ios/App/App/Assets.xcassets/AppIcon.appiconset/` |
| Splash screen (all variants) | ✅ Generated | `v2/ios/App/App/Assets.xcassets/Splash.imageset/` |
| Reading-flow screenshots (4 of 8) | ✅ Captured | `v2/screenshots/01-04` |
| Community-flow screenshots (4 of 8) | ⏳ Need from you | See Step 2 below |
| Privacy Policy | ✅ Live | https://averyscove.github.io/bible-study-v2/privacy.html |
| Terms of Service | ✅ Live | https://averyscove.github.io/bible-study-v2/terms.html |
| App Store listing copy | ✅ Drafted | `v2/app-store-listing.md` |

## Step 1 — Confirm Apple Developer Program is active (5 min)

You should have started this earlier. Verify:

1. Go to https://developer.apple.com/account
2. Click **Membership** in the left sidebar
3. You should see status **Active** and a **Team ID** (10 characters, starts with letters/numbers)
4. Copy the Team ID — you'll paste it into Xcode in Step 3

If status is "Pending" or you haven't enrolled yet, do that now: https://developer.apple.com/programs/enroll/. Choose Individual ($99/yr). Approval typically takes 24–48 hours.

## Step 2 — Capture the 4 community screenshots (5 min)

The 4 reading-flow screenshots in `v2/screenshots/` are done. We need 4 more from the community side. Easiest method:

**On your iPhone:**

1. Open https://averyscove.github.io/bible-study-v2/ in Safari (or open the home-screen icon if you've added it).
2. Tap the **community icon** (people icon, top right of the header), sign in if needed, set up a profile.
3. **Screenshot 5 — Community list:** Take iPhone screenshot (side button + volume up).
4. Tap any group → join it. **Screenshot 6 — Discussion thread:** screenshot.
5. Tap the **Chat** tab. Type one or two messages. **Screenshot 7 — Chat:** screenshot.
6. Go back to the home screen, open John 3 (or any chapter you've read), scroll past the reflection notes, tap the **"Share something with a group"** panel to expand it. **Screenshot 8 — Share to a group:** screenshot.

7. AirDrop those 4 screenshots to your Mac, drop them in `/Users/b0ngz/Documents/Claude/Projects/Bible Study/v2/screenshots/` named `05-community.png`, `06-discussion.png`, `07-chat.png`, `08-share.png`.

8. Tell me when they're in place and I'll commit them.

iPhone Pro Max screenshots are 1290 × 2796, which Apple accepts for the 6.9" required slot. (Different resolution from the simulator's 1320 × 2868, but Apple accepts both as long as they're consistent within a set. To be safe, either capture all 8 from your real phone, or commit the mixed set and let Apple normalize.)

## Step 3 — Configure code signing in Xcode (10 min)

1. In Terminal, run: `cd "/Users/b0ngz/Documents/Claude/Projects/Bible Study/v2" && npm run ios:open` — this opens the iOS project in Xcode.
2. In Xcode's left sidebar, select the **App** project (the topmost blue icon).
3. In the editor, select the **App** target (under "TARGETS").
4. Click the **Signing & Capabilities** tab.
5. Make sure **Automatically manage signing** is checked.
6. Set **Team** to your Apple Developer team (the one from Step 1).
7. Verify **Bundle Identifier** reads `com.averyscove.startingwithchrist`. If you want a different bundle ID, change it here AND in `capacitor.config.json`.
8. Wait for the spinner to settle. If Xcode says "Failed to register bundle identifier," click **Try Again** — sometimes Apple needs a few seconds to provision the new ID.

## Step 4 — Build a release archive (10 min)

In Xcode:

1. Top toolbar — click the device selector (next to the Run button) and choose **Any iOS Device (arm64)** under "iOS Devices". You can NOT archive while a simulator is selected.
2. Menu: **Product → Archive**.
3. Build runs for ~5–10 minutes. Xcode opens the **Organizer** window when done with your archive listed at the top.
4. If the build fails, screenshot the error and send it to me — most build errors at this stage are signing-related and have specific fixes.

## Step 5 — Upload to App Store Connect (10 min)

In the Organizer (still in Xcode after Step 4):

1. With your archive selected, click **Distribute App**.
2. Choose **App Store Connect**.
3. Choose **Upload**.
4. Click through the defaults:
   - Strip Swift symbols: yes
   - Upload your app's symbols: yes (helps Apple show better crash reports)
   - Manage Version and Build Number: yes
5. Sign with **Automatic signing**.
6. Click **Upload**. Takes a few minutes. When it's done, the build is in App Store Connect's "build processing" queue (~10–30 min for Apple to scan it).

## Step 6 — Create the App Store Connect listing (30 min)

1. Go to https://appstoreconnect.apple.com/apps and sign in.
2. Click **+** → **New App**.
3. Fill in:
   - Platform: iOS
   - Name: **Starting with Christ**
   - Primary language: English (U.S.)
   - Bundle ID: `com.averyscove.startingwithchrist`
   - SKU: `starting-with-christ-ios` (any unique string, doesn't show publicly)
   - User access: Full access
4. Click **Create**.

5. On the new app's page, fill in every section using the values from `v2/app-store-listing.md`:
   - **App Information** → Subtitle, Categories, Content Rights answer
   - **Pricing and Availability** → Free, all territories
   - **App Privacy** → click **Edit**, then go through the data-collection questionnaire using the table in the listing draft
   - **Age Rating** → click **Edit**, answer using the table in the listing draft (lands at 12+)
   - **App Review Information** → contact name, email, phone (the developer's, since reviews are sent to you), then **Notes** field — paste the "Reviewer notes" block from the listing draft
   - **Version Information**:
     - Promotional Text (optional) — paste from listing draft
     - Description — paste from listing draft
     - Keywords — paste from listing draft
     - Support URL — `https://github.com/Averyscove/bible-study-v2/issues` (or your support email)
     - Marketing URL (optional) — `https://averyscove.github.io/bible-study-v2/`
     - **Build** — click **+** and pick the build you uploaded in Step 5 (it'll appear once Apple finishes scanning it)
     - **Screenshots** — drag in the 8 screenshots from `v2/screenshots/`. Add captions (one per screenshot — I've suggested captions in the listing draft).

6. **App Privacy → Privacy Policy URL**: paste `https://averyscove.github.io/bible-study-v2/privacy.html`. This is required.

## Step 7 — Submit for review (2 min)

1. Top right of the version page: click **Add for Review**.
2. Confirm. Status changes to **Waiting for Review**.
3. Apple's queue currently averages 24–48 hours for first submissions. Sometimes faster, sometimes longer.

## Step 8 — Respond if Apple has questions (varies)

Apple may use the **Resolution Center** to ask for clarifications. Common issues for an app like this:

- **"Your app contains user-generated content but doesn't appear to have a EULA."** → reply that the Terms of Service are linked from inside the app at Settings → Legal → Terms of Service, and from the App Store listing's Privacy Policy URL.
- **"We could not test the community features."** → paste the test-account credentials from your Reviewer Notes, or create a fresh test account and update the notes.
- **"Your app appears to be a wrapper of a website."** → reply that the app uses Capacitor for native iOS integration (offline reading, background audio for chapters, native share sheet, push notifications planned), and the same content is available offline once installed.

For each: reply within 24 hours, in plain English, addressing the specific concern. Don't argue. Apple reviewers are usually reasonable when you explain.

## Step 9 — Approval and release (1–3 days from Submit)

When Apple approves:
- Status changes to **Pending Developer Release** (if you set "manually release" — the default) or **Ready for Sale** (if "automatic release").
- Tap **Release This Version** in App Store Connect.
- Within 24 hours the app is live in the App Store.

🎉

## Things to bookmark

| Where | Why |
|---|---|
| https://developer.apple.com/account | Team ID, signing certs, devices |
| https://appstoreconnect.apple.com | App Store listing, builds, sales, reviews |
| https://averyscove.github.io/bible-study-v2/ | The live web app |
| https://github.com/Averyscove/bible-study-v2 | The code, the privacy policy, the screenshots |
| Xcode → Organizer | Archives, validation, distribution |

## What I'm watching for

When you're ready, tell me:
1. The community screenshots are in place → I'll commit them.
2. The Xcode signing/archive errors (if any) → I'll diagnose and fix.
3. The Apple Resolution Center asks something → I'll draft your reply.

Until then, this is on your court. Take your time. We're close.
