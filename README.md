# scamulation
a simulation for real life scam scinarios.
# A note on the simulator's core mechanic

Quick flag before we're too deep in: right now the simulator shows a mocked scam screen and asks the user to pick "proceed" or "flag as suspicious." It works, but it plays like a quiz — the user knows a decision point is coming, so they read more carefully than they would in real life. That's the opposite of how these scams actually get people.

**Proposed change:** instead of one screen with a fork in the road, walk the user through a normal multi-step flow — enter amount, confirm recipient, enter OTP, "Processing..." — that feels completely routine, the way a real payment app does. No decision prompt in the middle. The user just goes through it like they would any transaction. Then, after they've clicked through, hit them with the consequence: balance reads ₹0, "Transaction failed — funds already debited," account flagged. The realization lands *after* the fact, not mid-choice.

**Why this matters for judging:** it directly answers the PS's real ask — evaluate *decisions*, not just one decision. A multi-step flow gives you several data points (which screen they paused on, whether they double-checked the recipient, etc.) instead of one click. It also just feels more real, which is the difference between "nice UI" and "this actually taught me something."

**Practical scope for the time we have:** 2 full flows, done well, beats 4 shallow ones:
1. Payment flow scam (amount → recipient → OTP → processing → reveal)
2. Loan app flow (application form → permissions request → approval → reveal what those permissions actually enable)

Each ends in a reveal screen breaking down what was missed, feeding into the same scoring/tips system we already have.

Let's sync quickly before building further so we're not duplicating work in different directions.
