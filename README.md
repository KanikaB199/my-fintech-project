**Live site:** https://kanikab199.github.io/my-fintech-project/
**Repository:** https://github.com/KanikaB199/my-fintech-project

## Question

Can the least powerful person on a restaurant team see how the tip rule counts their hours, and raise a concern safely?

*Fictional teaching case (NCI, H9LOCHFFT CA2): Sciar, Halloran's, their people and every figure are invented.*

## Part 1: The people

**Internal: Aoife Rennick (CEO, Sciar).** Needs a phone-first alpha: "Make it work on a phone. Nearly all restaurant staff only have phones." (04-aoife.md)

**External: Rafael (kitchen porter, Halloran's).** Needs to understand his pay and question it without being exposed: "i dont understand how they count it." and "please dont say it was me who ask" (01-rafael.md)

**Accessibility and culture.** Rafael's first language is Portuguese and "my phone screen is broken" (01-rafael.md). So the build puts the answer on the first screen in big plain English, adds a Português switch and one-tap concern options, and needs no long link.

| Design choice in `app.html` | Comes from (Part 1) |
|---|---|
| One column, big tap targets, bottom tabs, answer on the first screen | Aoife: "Make it work on a phone." |
| Plain English first, Português switch, no long link | Rafael: "i dont understand how they count it." and "my phone screen is broken" |
| Concern is private by default and does not go through a manager | Rafael: "please dont say it was me who ask" |

## Part 4a: Theory behind the build

**Leadership: leader-member exchange (Graen & Uhl-Bien, 1995).** It explains why Rafael stays quiet. His standing rests on a personal favour, "he is good to me with my visa letter", and his one question ended at "is the system, is fair for everybody" (01-rafael.md). It misses the rule itself: hours after 23:00 earn no points, so Rafael got €1.29 in tips per hour worked against €7.67 for servers (payouts.csv, 12 weeks).

**Culture: organisational silence (Morrison & Milliken, 2000).** Niamh reads "Nobody has ever complained" (03-niamh.md) as satisfaction. But Rafael did ask once, in September, and now writes privately to a new colleague. The silence is the evidence, not the reassurance.

**Design choice.** Because of this, concerns bypass line managers, default to Sciar only, and give the person a reference they can see.

**Competitive advantage (inferred).** Sciar sells trust in how money is split. Staff do not pay but decide whether the tool is believed, so building for the least powerful makes it more credible, at some cost to owner comfort.

**Limit.** Both theories describe relationships and climate. Neither was built for a six-person firm with a language barrier and visa dependence, and neither can say whether the rule is fair.

## Part 4b: Decision record

**Decision 1: request changed (Aoife, 04-aoife.md): "lose the 'raise a concern' idea".** Options: (a) remove it; (b) an open wall, or one routed to the floor manager; (c) a private, structured channel to Sciar first. Criteria: safe for the least powerful, tolerable to owners. I chose (c): Rafael's message shows that no channel means silence. I would change my mind if owners would not buy with any channel present; then it becomes a per-customer setting. Underlying needs: Aoife wants owners reassured, so the owner sees a concern only if the person chooses; Niamh fears a "moaning wall", so there is no wall and only the raiser sees the list.

**Decision 2: AI suggestion rejected (05-market-scan.md): lead with "34% longer" retention and "only tip platform fully compliant".** Options: use as written; hedge it; leave out. Criteria: traceable to the pack; the brief bans unsourced statistics and legal claims. "No sources were attached", so neither can be checked. I used the pilot's own figures. A primary source and a legal view would change my mind.

**Bias: I almost submitted the report without cross checking the figures that the AI agent used in making the landing page and I believed it, trusting the AI too readily was my bias but before submitting I was cross checking the assignment and noticed I hadn't checked that part, so I opened the data folder and from there I cross checked all the figures that AI used and they were correct. Commit hash - 03aa4b986750dc8913e5e72d63e03f5d414ebe63**

## Part 4c: The Struggle, without AI

**I tried to understand the whole assignment and tried to create a workflow, but the AI shared a complex structure. So, I went back to the CA pdf and read it carefully and made a structure for me, but the AI also helped. 
While working, the app that claude generated was blank and it had nothing, so I had to ask multiple times to claude to correct it. I also struggled with making a good layout as it seems that AI had some fixed or already stored layouts and colour preferences, that it was not able to change easily, so I had to direct claude and needed to work with him to implement my idea and create a nice landing page and app. 
Going forward I will not go and put everything in one go and I will work with the AI in steps to get better, clearer answers.**

## Assumptions and limits

- Pack data is observed; messages and the market scan are claimed; everything I computed is inferred.
- "Groups of three or more": colleagues appear only as ratios for groups of at least 3 other people. Bar (2 people), kitchen porters (2, then 1 after week 8) and the floor manager (1) are never shown. Even so, small groups can be combined to guess at one person; a real product needs a larger minimum and a review.
- `app.html` embeds exact copies of `data/payouts.csv` and `data/takings.csv` so it works anywhere; the same files are in `data/`.
- The background is a decorative photo of a restaurant dining room that I chose. It is not Halloran's and holds no data. I took this picture from google. Fonts are Inter Display and, for the logo on the landing page, Comic Relief (both SIL Open Font Licence), embedded in the pages.
- Concerns are simulated: saved in the browser only, nothing is sent. The "Who are you?" picker is a demo device. A real app would sign in by phone number.
- Portuguese labels are machine-made and need a native speaker's check. I assumed a neutral Portuguese.
- Seven opening days show a service charge of 0.00 with no payee; I assume no table of six or more was served on them.
- "Paid out" means the `tip_payout_eur` Sciar logged; the pack has no bank records.
- The what-if (late hours counted at the person's rate) is my calculation, not Halloran's rule.

## What I left off the landing page

| Request | Decision | Why |
|---|---|---|
| "100% of tips go to the team" (Declan) | Changed to the sourced pool figure | Card tips match payouts (€31,754.13 in, €31,754.09 out). The service charge (€9,004.69, paid to the house) is separate, so a bare "100%" would mislead. |
| "Fully compliant with Irish tips law" (Declan) | Refused | No legal source in the pack; the brief bans legal claims. |
| "34% longer retention", "2.3x", "8 in 10", "only fully compliant platform" (05-market-scan.md) | Refused | No sources were attached. |
| Points table hidden from staff (Declan, Aoife) | Not followed in the staff view | Showing own hours and points is what answers Rafael's question. |

## AI use

Built with Claude (claude.ai chat). Full chat: [Claude share link](https://claude.ai/share/8103f0e2-4b17-4684-8aef-35985cf58de6). A short summary of what the AI did and what I did myself: [ai-log/ai-sessions.txt](ai-log/ai-sessions.txt). Part 4c and the bias paragraph in Part 4b are my own words, written without AI. I have not redacted anything.
