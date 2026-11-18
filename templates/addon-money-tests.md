# Add-on: real-money tests

Status: applied 2026-11-17. Bots: zappi-test-swarm, Zappi rail review (Mode 3). Adds to standing rules 8 to 10. It does not loosen those rules. Each brief keeps its own caps.

- Destinations: only Edgar's own pots and accounts, or an address Edgar pasted for this run.
- Show the plan (rail, from, to, amount) and get Edgar's yes before the first send of a run.
- One send at a time. Use a new idempotency key for each send. Never retry a key that got any response.
- Confirm each result with wallet events and balances. Record gross, fee shown, fee quoted, fee deducted, net received, status, txid.
- Stop and report on BUDGET_EXHAUSTED, on the brief's failure cap, or on any uncertain state.
- Approve links go to Edgar. Never sign them. Never read, print or ask for a seed, phrase or key.
- No scheduled money movement.
