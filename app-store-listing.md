# App Store listing — Starting with Christ

> **Status: DRAFT for Neptune/Avery review.** Everything in this file is what gets pasted into App Store Connect when you submit. Edit anything that doesn't sound right; nothing is locked in until you click submit.

## Identity

| Field | Value | Notes |
|---|---|---|
| **App name** (max 30 chars) | `Starting with Christ` | 20 chars — fits |
| **Subtitle** (max 30 chars) | `Bible study, read together` | 26 chars |
| **Bundle ID** | `com.averyscove.startingwithchrist` | Set in Capacitor + Xcode |
| **Primary category** | Lifestyle | Apple has a Religion sub-cat under Lifestyle |
| **Secondary category** | Books | Optional, but good for discovery |
| **Age rating** | 12+ | See "Age rating answers" below |
| **Pricing** | Free | No in-app purchases at launch |

## Promotional text (max 170 chars — editable any time without resubmission)

```
Read through the Gospel with intention. Take notes, hide verses in your heart,
and connect with people walking the same passages. New: small-group community.
```
(167 chars)

## Description (max 4,000 chars)

```
Starting with Christ is a quiet, intentional Bible-reading app built around a
five-phase plan that begins where the Christian story begins — with Jesus.

Read the Gospel of John to meet him, Romans to understand what his death and
resurrection accomplished, Luke to follow his life, Acts to see the church
born, and selected Old Testament passages to see how the whole story was
pointing here all along. Memorize the eight verses the New Testament keeps
returning to. Reflect on what stood out, what's confusing, and what you want
to pray about — privately, on a page that's just for you and the chapter.

After every chapter, a Reading Companion gives you a short summary, two or
three key lessons, and a "Hold in Tension" — a counterweight to keep you
honest, modeled on the way the best teachers help you avoid easy conclusions.

Listen to chapters read aloud. Track your reading streak. Bookmark the verses
that matter, with one tap. Everything works fully offline once installed —
no cellular signal required.

Optional community.

You can join one of six small groups built around the reading plan: Meeting
Jesus through John, the Romans deep-dive, Luke, Acts, Old Testament
Foundations, or Memory Verse Practice. Each group has a slow-paced
discussion thread with conversation starters, plus a real-time chat for
quick thoughts and prayer requests.

When something stands out in your reading, you can share a reflection
directly to a group — pre-filled with the chapter you're on and the note
you wrote. You stay in control: nothing is shared automatically, ever.

Privacy first.

• Sign-in is only needed for the community. The reading plan and your
  personal notes work fully without an account.
• Display names are pseudonyms by default. Real names not required.
• You can flag content, block users, and delete your account from inside
  the app at any time.
• We don't sell or share your data. We don't run ads.

Bible text: World English Bible (public domain). For NLT, ESV, NKJV, the
chapter pages link out to Bible.is for streaming audio.

Made with care, for one quiet hour at a time.
```

## Keywords (max 100 chars total, comma-separated)

```
bible,gospel,jesus,john,romans,devotional,prayer,christian,reflection,memory verses,study,reading
```
(99 chars)

## What's New in this version (for the first release, optional)

```
The first release. Read the Bible, take notes, memorize the verses that
hold up, and — if you want — read alongside other people in small,
focused groups. Welcome.
```

## Support URL

```
https://github.com/Averyscove/bible-study-v2/issues
```
(Or your own support email — Apple just wants a working URL.)

## Marketing URL (optional)

```
https://averyscove.github.io/bible-study-v2/
```

## Privacy Policy URL (required)

```
https://averyscove.github.io/bible-study-v2/privacy.html
```

## Terms / EULA URL (optional but recommended for UGC apps)

```
https://averyscove.github.io/bible-study-v2/terms.html
```

---

## Age rating answers

When you fill out the age-rating questionnaire in App Store Connect, here are the honest answers based on what's actually in the app. Apple uses these to compute the final rating.

| Question | Answer | Why |
|---|---|---|
| Cartoon or fantasy violence | None | — |
| Realistic violence | None | — |
| Sexual content or nudity | None | — |
| Profanity or crude humor | Infrequent / mild | The Bible uses words like "hell" and "damn" in religious context. Defensible as "mild." |
| Alcohol, tobacco, drug use | Infrequent / mild | Bible references to wine. |
| Mature/suggestive themes | None | — |
| Horror/fear themes | None | — |
| Medical/treatment information | None | — |
| Gambling | None | — |
| Unrestricted web access | **No** | We only link to Bible.is for audio; that's a curated link, not a browser. |
| Gambling and contests | None | — |
| **User-generated content** | **Yes — moderated** | Group posts, replies, chat. We have flag, block, delete, account deletion. |
| Frequent/intense user-generated content | Yes | This is what gets us to 12+ |

**Result:** 12+ is the right rating. Apps with public UGC almost always end up 12+ minimum because of the unmoderated-strangers risk, even with our flag/block tools.

## Required answers when submitting (App Store Connect questionnaire)

**Encryption export compliance:** No. (We don't use encryption beyond standard HTTPS/TLS, which is exempt.)

**Content rights:** Yes — we have rights to all content shipped in the app. The Bible text is public domain (World English Bible). The reading-companion commentary is original. The community content is generated by users, who agree to our Terms of Service and grant us a display license.

**Advertising identifier (IDFA):** No. We do not collect IDFA.

**Data collection (Privacy Manifest answers):**

| Data type | Collected? | Linked to user? | Used for tracking? | Purpose |
|---|---|---|---|---|
| Email address | Yes | Yes | No | Account management |
| Name (display name) | Yes | Yes | No | App functionality (showing post authors) |
| User content (posts, messages) | Yes | Yes | No | App functionality |
| Other user content (notes, bookmarks) | Yes | Yes | No | App functionality |
| Crash data | No | — | — | (We don't use Crashlytics) |
| Performance data | No | — | — | — |
| Product interaction | No | — | — | — |
| Advertising data | No | — | — | — |
| Location | No | — | — | — |
| Health & Fitness | No | — | — | — |
| Financial info | No | — | — | — |
| Sensitive info | No | — | — | — |
| Contacts | No | — | — | — |
| Photos / videos | No | — | — | — |
| Audio | No | — | — | — |
| Search history | No | — | — | — |
| Browsing history | No | — | — | — |

This produces the iOS 14+ Privacy Nutrition Label that shows on the App Store.

## Screenshots — required sizes

Apple requires at least one set; you can submit more sets to look polished.

| Device | Required? | Required size | What I've already captured |
|---|---|---|---|
| 6.9" iPhone (iPhone 17 Pro Max) | **Yes** | 1320 × 2868 | ✅ 4 screenshots in `screenshots/` |
| 6.5" iPhone (iPhone 11 Pro Max) | Optional | 1242 × 2688 | Auto-generated by Apple if 6.9" provided |
| 5.5" iPhone (iPhone 8 Plus) | Optional | 1242 × 2208 | Skip — Apple no longer requires this |
| iPad Pro 12.9" | Optional | 2048 × 2732 | Skip unless you want iPad-on-day-one |

**Captured so far** (in `v2/screenshots/`):

1. `01-welcome.png` — Auth/welcome screen with the J monogram
2. `02-chapter.png` — Reading view, John 1, drop cap, listen button
3. `03-companion.png` — Reading Companion with summary and lessons
4. `04-reflection.png` — Reflection prompts ("about Jesus", "what stood out")

**Recommended additional screenshots** (community-side):

5. Community list — six groups visible
6. Inside a group — Discussions tab with posts
7. Inside a group — Chat tab with messages
8. Share to a group — the panel open under a chapter

I can capture these from Simulator on retry, or you can grab them on your real iPhone (System Screenshot, transfer via AirDrop). Apple accepts both.

## Suggested screenshot captions (the small text Apple shows above each screenshot)

| # | Screenshot | Caption |
|---|---|---|
| 1 | Welcome | "Begin where the gospel begins" |
| 2 | Reading | "Read with intention" |
| 3 | Companion | "Insight after every chapter" |
| 4 | Reflection | "Slow down. Take notes that matter." |
| 5 | Community | "Six small groups, one for each part of the plan" |
| 6 | Discussions | "Wrestle with the hard questions together" |
| 7 | Chat | "Quick check-ins, prayer, presence" |
| 8 | Share | "Take a thought from your reading straight to a group" |

## Reviewer notes (private — only Apple reviewers see this)

```
Hello reviewer,

This app is a personal Bible study and small-group community. The Bible
text used throughout is the World English Bible, a public-domain
translation; we have full rights to ship it.

To test the community features:
1. Tap the people icon in the top-right of the home screen.
2. Sign up with any test email/password (Firebase email/password auth).
3. Set a display name and choose any level. The app shows a list of
   six pre-made study groups.
4. Tap any group, then "Join group". Discussions and Chat tabs become
   active.

Moderation tools available on every post and message:
- Flag: reports content to the group owner. (App Store Guideline 1.2)
- Block: hides everything the user has posted. (App Store Guideline 1.2)
- Delete-own: authors can delete their own content within 5 minutes.

Account deletion: Settings → Account → Delete. Requires password
re-confirmation. (App Store Guideline 5.1.1(v))

Thank you for your time.
```

## Final pre-submission checklist

These are things only you can do (the human-in-the-loop steps).

- [ ] Apple Developer Program enrollment is **complete and active** (https://developer.apple.com/account → Membership)
- [ ] Apple Developer Team ID is in hand (10-character string from Membership page)
- [ ] Xcode is signed in with the same Apple ID (Xcode → Settings → Accounts)
- [ ] In `ios/App/App.xcodeproj`, set **Signing & Capabilities → Team** to your team
- [ ] Build number bumped (Capacitor sets it to 1 — fine for first release)
- [ ] Marketing version is `1.0.0` in `ios/App/App.xcodeproj` (matches what we'll list)
- [ ] All required screenshots captured (6.9" iPhone minimum)
- [ ] Privacy Policy URL works publicly (you can verify: https://averyscove.github.io/bible-study-v2/privacy.html)
- [ ] App Store Connect listing created at https://appstoreconnect.apple.com/apps
- [ ] Listing fields populated from this document
- [ ] Build uploaded via Xcode (Product → Archive → Distribute App → App Store Connect)
- [ ] Build attached to listing in App Store Connect
- [ ] Submit for review

After submit: Apple's review queue averages 1–3 days for a first submission. They sometimes ask for clarifications via the Resolution Center; respond within 24 hours and the review continues.
