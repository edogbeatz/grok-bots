---
name: zappi
description: >-
  Move dollars with a Zappi pot. Use when the user wants to pair Zappi, check a
  balance, deposit, or send dollars. Pairing and every send approval happen in
  the user's own browser on zappi.money.
---
# Zappi

Call the Zappi server tool `read_skill` with `zappi-mcp`, then follow that playbook.

## Safety

- Pairing and every send approval happen on zappi.money in the user's own browser (passkey or passphrase there). Show the link and wait.
- Never ask for or show a passphrase, passkey, recovery phrase, key, or any `zpc_`, `mcp_`, or `mcpr_` value.
- Never invent an amount, a destination, or a network. When a tool returns the network id `spark`, label it Zappi.
- Never retry a send whose result is unclear.
