# Bible Study v2 — community edition

> **In development. Not deployed. v1 is the production app.**

This is the parallel build that adds community / groups / discussion to the Bible Study app. v1 at `../index.html` continues to ship unchanged.

## What's different from v1

- Public profiles (display name, bio, favorite books, study level)
- Groups: create, discover, join, leave (Phase B)
- Posts, replies, reactions inside groups (Phase C — not yet)
- Sharing reflections from the reading flow into a group (Phase D — not yet)
- Same Bible reading + notes + bookmarks experience as v1 underneath

## Files

```
v2/
├── index.html         starts as a verbatim copy of v1; community layer added incrementally
├── sw.js              separate service worker, cache name = bible-study-v2-*
├── firestore.rules    full security rules (covers v1 + v2 collections)
└── README.md          this file
```

The first commit of `v2/index.html` is identical to v1. Each subsequent commit lays in a piece of the community layer (auth gating, profile model, profile screens, groups list, etc.).

## Firebase setup

v2 uses the **same Firebase project as v1** (`bible-study-25f61`) but writes to new collections only:

| Collection | Read | Write |
|---|---|---|
| `/users/{uid}` *(v1)* | owner | owner |
| `/profiles/{uid}` *(v2)* | any signed-in user | owner |
| `/groups/{gid}` *(v2)* | any signed-in user | creator + owners |
| `/groups/{gid}/members/{uid}` *(v2)* | any signed-in user | self (join/leave) + owners (kick) |

Before v2 first works against the live database, paste `firestore.rules` into the Firebase Console (Firestore → Rules → Edit → Publish). The rules file preserves the existing v1 rule verbatim and adds the v2 rules — do not strip the v1 block.

## Local development

Open `v2/index.html` directly in a browser. Firebase auth requires a real domain or `localhost` for some flows; for serious testing run a local server from this folder:

```bash
cd v2
python3 -m http.server 8080
# then open http://localhost:8080/
```

## Deployment plan

When v2 alpha (Phase A + B) is ready, the leading plan is:

1. Push `v2/` contents to a new repo `bible-study-v2`.
2. Enable Pages on that repo → `https://averyscove.github.io/bible-study-v2/`.
3. v1 stays at `https://averyscove.github.io/bible-study/`.

Why a separate repo: v1's service worker is registered at `/` and could intercept requests under `/v2/` if we shipped them to the same Pages site. Separate origins / paths avoid the collision.

We could also use a custom subdomain later if Neptune wants `community.bible-study.app` or similar.

## Build phases

See `../docs/community-feature-proposal.md` for the full plan and `../docs/decisions.md` for the design decisions.

- **Phase A**: profiles + auth gate. *(next)*
- **Phase B**: group discovery + join/leave (no posts).
- **Phase C**: posts, replies, reactions.
- **Phase D**: sharing from reading flow.
- **Phase E**: moderation tools.

## Current build status

What's working now (community shell — read-only):

- ✅ A "Community" icon in the top bar (next to search/settings)
- ✅ A Community screen showing all 6 launch groups as cards
- ✅ Each group has its own page with:
  - Description and level tag
  - Tabbed view: Discussions / Chat
  - The pinned welcome post (Discussions tab)
  - The 2 starter conversation prompts (Discussions tab)
  - The opening chat message (Chat tab)
- ✅ Styled to match the rest of the app
- ✅ Firestore rules drafted for the full v2 schema (not yet pushed to Firebase)

What's NOT working yet (intentionally):

- ❌ Sign-in gate for community features
- ❌ Profile screen (display name, bio, level)
- ❌ Joining / leaving groups
- ❌ Posting in chat or discussions
- ❌ Replies on discussion posts
- ❌ Reactions
- ❌ Real-time updates
- ❌ Moderation (flag, mute, edit, delete)

The seeded group content (`seed-content.md`) is hardcoded into `index.html` as the `SEED_GROUPS` constant. The 6 groups will appear in v2 even without any Firestore writes ever happening — they're config, not data. Only user-generated content (chat messages, replies, memberships) needs Firestore.

## Author name on seed posts

The seed welcome posts and chat openers are attributed to **"Avery"** (matching the GitHub username). Change the `COMMUNITY_TEAM_NAME` constant in `index.html` if you want a different name to appear on the pinned content.
