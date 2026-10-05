### Matthew "Hew" Suber

Product and design leader in Atlanta. I design and I ship: 17 years across Meta, Pinterest,
Opendoor and CNN Mobile, and now I build my own products end to end, from the first HTML
prototype to the production database.

[matthewsuber.com](https://matthewsuber.com) · [hewdoes.xyz](https://hewdoes.xyz)

---

#### Presence · [joinpresence.app](https://joinpresence.app)

A privacy-first iOS app that lets a close friend know when you show up. It is rule-based
location sharing, built against always-on trackers: friends see an outcome ("Hew is at Teeth
Bar"), never a map, a trail or a live feed.

Built solo: product, design, the SwiftUI client and the Supabase backend.

- **Consent enforced by the server, not the app.** Every rule waits for the other person to
  accept it. Postgres Row Level Security and a dedicated safety schema gate every notification on
  friendship, blocks and pause.
- **Privacy by construction.** Positions are rounded to about 110 m on the phone before they leave
  it. The server keeps one overwritten position per person and no location history. Match records
  are deleted after 30 days.
- **Production discipline.** Every database migration is rehearsed against production inside a
  transaction that always rolls back, then applied by hand. Nightly invariant checks run on the
  live database. 475 tests and a privacy lint (no unrounded coordinate or other person's ID reaches
  a third party) run before every Swift commit, and secret scanning runs before every commit.
- **Stack:** Swift 6.3, SwiftUI, SwiftData, CoreLocation, MapKit · Supabase (Postgres 17,
  pg_cron, pg_net, Deno edge functions) · APNs · Google Places.

In private testing, not yet in the App Store. The code is private; I'm glad to walk through it.

#### Chronicles of Sage Orange · [sageorange.fm](https://sageorange.fm)

A fact-grounded interactive audio drama. A streaming story engine on Claude writes each scene,
ElevenLabs voices it, and the listener can steer the story while it plays.

- **Mechanism over persuasion.** Hard story rules are enforced in code, not by ever-stronger prompt
  wording.
- **The story canon is bundled into a cached system prompt** that stays byte-stable per deploy;
  everything that changes per turn goes in the user message.
- **Stack:** TanStack Start, React 19, TypeScript · Anthropic API · ElevenLabs · Supabase · Vercel.

535 commits since January 2025.

---

#### How I work

- **Design in HTML, judged in motion.** Prototypes are real, animated pages in light and dark
  before anything is built natively.
- **AI-native engineering.** Claude Code agents write and verify code alongside me. I keep the
  decisions and every production change.
- **Verify against reality.** A green build proves nothing; the database row or the device does.
