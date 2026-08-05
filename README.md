# Mollywood Imposter

A pass-and-play "imposter" party game themed entirely around Malayalam movies. One phone,
one room, everyone in a circle.

## How it plays
1. Set the number of players (3–10) and optionally rename them.
2. Pass the phone around — each player taps their card to reveal it, then hides it and
   passes it on. Everyone sees the movie name **except** the imposter, who only sees a
   vague clue about it.
3. Everyone takes turns saying one clue/sentence about "the movie" out loud. The imposter
   has to bluff convincingly without knowing the title.
4. Use the built-in discussion timer, then vote out loud (no app needed for voting) on
   who you think the imposter is.
5. Tap "reveal" to see who it actually was, then start a new round.

No backend, no database, no build step — it's a single static HTML file.

## Deploy to Vercel

### Option A — Vercel CLI (fastest)
```bash
npm install -g vercel
cd mollywood-imposter
vercel --prod
```
Follow the prompts (log in, confirm project name). When asked about framework, choose
**Other** — it's a static site, no build command needed. You'll get a live `.vercel.app`
URL in under a minute.

### Option B — GitHub + Vercel dashboard
```bash
cd mollywood-imposter
git init
git add .
git commit -m "Mollywood Imposter game"
git branch -M main
git remote add origin https://github.com/<your-username>/mollywood-imposter.git
git push -u origin main
```
Then on [vercel.com](https://vercel.com):
1. **Add New → Project**
2. Import the `mollywood-imposter` GitHub repo
3. Framework preset: **Other**
4. Leave Build Command and Output Directory empty
5. Click **Deploy**

Either way you'll get a shareable link that works great on mobile — add it to your home
screen for a near-native feel.

## Customizing
- Add/edit movies in the `MOVIES` array near the top of the `<script>` block in
  `index.html` — each entry just needs a `title` and a `hint` that doesn't give away the
  title.
- Change the round timer defaults in the `durationChips` buttons (`data-secs`).
