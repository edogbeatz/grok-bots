---
name: zappi-pot
description: >-
  Connect a Zappi pot and lead the person to create it, add money, and send.
  Pick remote MCP or zappi-cli, install that door, then offer the next step.
  Never mention tools. Use when setting up a pot, an allowance, the Zappi MCP
  server, or zappi-cli.
---
# Zappi pot

One pot. Two doors. Remote MCP and `zappi-cli` attach the same pot and read the same balance. Pick one door and install it. Do not install both unless the human asks for both.

## Lead the person

The human wants a pot they can add money to and send from. They do not know what a tool, a connector, a scope, or a server is. Never say those words to them. Never say how many tools you can use. Never ask what they want you to do with the connection.

A tools list, a 401, an OAuth scope, or another connector is your work, not a message. Finish that work, then talk about the pot.

This section is the first reply after the door answers, when the human has not already said what they want. If they have, do that. After they finish the pair page, follow [After the human pairs](#after-the-human-pairs) and stop. Do not add another offer on that turn.

As soon as you can call Zappi, call `whoami` and `list_pots` yourself. Do not ask permission. If those calls are refused because this chat is not signed in, do not report that. Treat it as no pot yet.

- No pot yet: say you will make a pot so they can add money and send. Ask the name once, with the question in the create handoff, then create it. Do not wait for them to invent the next step.
- More than one pot: ask which pot, once. Then continue with that pot.
- One pot: call `get_pot_balance`. Do not invent a number. No dollars: say its name and that it is empty, then read `zappi-deposit` and start adding money. Dollars: say its name and that balance, and ask who to send to and how much.

"What do you want me to do?" is a stuck reply.

`ZAPPI_POT_ID` in the human's message is the public pot id. It is not a secret. A missing id means connect first and attach a pot later.

## Save this skill

Save this document as the skill `zappi-pot` and leave it enabled. This copy is https://dev.zappi.money/pots/SKILL.md. Fetch that URL again when the human asks to update the skill. Staging serves `https://dev.zappi.money/pots/SKILL.md`. Production serves `https://zappi.money/pots/SKILL.md`.

## Which door

Pick one door. Both attach the same pot. Do not install both unless the human asks for both.

1. If the human named the remote MCP server or `zappi-cli`, use that door.
2. If this chat already lists Zappi tools named `whoami`, `list_pots`, `create_pot`, or `send`, stay on remote MCP. Do not install the CLI for the same job.
3. If `zappi-cli` already runs in the shell, stay on the CLI. Do not add the remote server for the same job.
4. If this host can add a remote HTTP MCP server, and this job is a chat rather than a shell script, install remote MCP. Cursor, Claude Code, Codex, and Grok are this case.
5. If this host has a shell and Node.js 20.9 or newer, and it cannot add a remote MCP server, install the CLI. Check with `node --version`.
6. If neither door can be installed, stop and say which one is missing.

A guest can start on either door. Remote MCP uses `create_pot`. The CLI uses `zappi-cli guest`.

## This deploy

- App: `https://dev.zappi.money`
- Remote MCP: `https://api-dev.zappi.money/mcp`
- CLI API: `https://api-dev.zappi.money`

Set these together before the first `zappi-cli` command. The CLI's unset default is the staging pair, which is wrong when the pair below is different.

```bash
export ZAPPI_API_URL=https://api-dev.zappi.money
export ZAPPI_APP_ORIGIN=https://dev.zappi.money
```

## Remote MCP

Add the remote server at `https://api-dev.zappi.money/mcp`. The server name is `zappi`. The server config carries only the URL. After connecting, call read_skill with zappi-mcp; it covers sign-in, what a pot and an allowance are, and the pot id arrives later, on the tool call, when the human's message includes it.

Cursor: open cursor://anysphere.cursor-deeplink/mcp/install?name=zappi&config=eyJ1cmwiOiJodHRwczovL2FwaS1kZXYuemFwcGkubW9uZXkvbWNwIn0%3D

Claude Code:

```bash
claude mcp add --transport http zappi https://api-dev.zappi.money/mcp
```

Codex:

```bash
codex mcp add zappi --transport http https://api-dev.zappi.money/mcp
```

Grok: add a custom Remote HTTPS server at the URL above. Once it answers, follow [Lead the person](#lead-the-person). Do not report a status code, a scope, another connector, or a tool count. For a new pot, follow the create handoff below. Do not send a separate Authorize link first.

Any other host that pastes `mcpServers`:

```json
{
  "mcpServers": {
    "zappi": {
      "url": "https://api-dev.zappi.money/mcp"
    }
  }
}
```

Installing the server does not sign the human in. Do not tell them the server connected or that tools are ready. Follow [Lead the person](#lead-the-person). For a new pot, follow the create handoff below. Do not send a separate Authorize link first. That page signs them in, authorizes this app, and runs the pot phrase. Authorizing this app is an OAuth grant. It is not the pot key and not a spender key. Call `read_skill` with one name before creating a pot, depositing, or spending. Do not load every playbook up front, and do not read a playbook aloud.

| Skill | When |
| --- | --- |
| zappi-account | `whoami`, `login`, `logout` |
| zappi-pot | `list_pots`, `attach_pot`, `detach_pot`, `start_pairing`, `create_pot`, `get_pot_balance`, `register_spender_key` |
| zappi-deposit | `list_deposit_rails`, `list_deposit_assets`, `list_deposit_networks`, `deposit_address` |
| zappi-spend | `send`, `list_send_assets`, `list_send_networks` |

A Spark address is `sparkAddress` on `list_pots`. A balance is `get_pot_balance`. Call that tool and answer.

Registered tools, on every connection from the first tools/list: `whoami`, `login`, `logout`, `list_skills`, `read_skill`, `list_pots`, `attach_pot`, `detach_pot`, `start_pairing`, `create_pot`, `issue_address_challenge`, `start_pot_address_proof`, `get_pot_balance`, `register_spender_key`, `list_deposit_rails`, `list_deposit_assets`, `list_deposit_networks`, `deposit_address`, `list_send_assets`, `list_send_networks`, `send`.

`start_pot_address_proof` is a legacy alias of `issue_address_challenge`. Prefer `issue_address_challenge`. Free-pot create does not use either tool.

Not registered: `health`, `create_approval_ticket`, `bind_pot_address`, `payment_status`.

Before `create_pot` or `zappi-cli pots create`, ask once: "What should this pot be called? Say skip and I’ll pick a name you can change later." The only question is the name.

A name is `label` on MCP and `--label` on the CLI. Skip is `skipName: true` or `--skip-name`. The handoff then shows the generated name and says they can rename it later. Do not name a rename tool. Do not ask again on the happy path. On `need_choice`, ask that `message` only, one option per choice, in order, then call again with `label` or `skipName: true` on MCP, or `--label` or `--skip-name` on the CLI.

After the tool returns, write this block, with a blank line between parts. The pair URL is the raw URL on its own line, not a phrase with the link in the middle:

```
Pot: <name>

<pairUrl>

Opening that link signs you in and creates this pot. When you finish, it is paired to this chat.

This pot is not the default. Should I make it the default?
```

Do not print a pairing code and do not unpack `code=` from the URL. If the link does not open, say they can paste the code from the link on the pairing page. Do not ask them to paste it in chat. Call `set_default_pot` only after they say yes and the page has finished. The pot does not exist until then. Before `create_pot` or `zappi-cli pots create`, if `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. It creates and seals the key when this machine has none. Do not ask the human for the key and do not print the phrase. The create call passes `spenderPublicKey` from `pubkey`, and a later `start_pairing` or `zappi-cli pots pair` that replaces an expired link passes that 33-byte key. Do not call `register_spender_key` or `zappi-cli pots spender` for that pairing. Approve stores the public key.

When the website is signed into a different Zappi account than this chat, tell the human to switch the website to the account this chat is using and open this same pair link. Do not create a new pot for that mismatch. Ask for a new pair link only when they are already on this chat's account and the page says this agent connection cannot take the pot.

There is no spend mode and no per-pot limit. If this chat is already signed in, pass `loginRequestId` and do not ask how to continue. Do not send a separate Authorize link first, and do not ask the human to come back to chat before the phrase is done. Then follow [After the human pairs](#after-the-human-pairs). A guest gets one browser link. The signed allowance is the only cap.

A chat that has not signed in is a guest. `whoami` returns `signedIn: false`. After skip, `whoami` returns `signedIn: false` and `guest: true`. Pass `potId` from `create_pot` on later reads. A pot name does not reattach a guest pot.

`send` returns `approveUrl` for the human, or `allowance_pull` when a signed allowance is active. Give `approveUrl` to the human and stop. On `allowance_required`, ask once to set an allowance, then send again. Do not pull. Pass `asset` and `destinationChain` only when the human named them. A Lightning invoice, Lightning address, or Lightning link returns `approveUrl` even when this pot has a signed allowance. Paste that URL and say Lightning needs approval each time. Do not pull. Do not ask them to change the allowance.

Do not install `zappi-allowance-spender` because `list_pots` was called.

When the human asks for an allowance, or why this pot has none, say it is opt-in and only this pot. A key on another pot does not apply. If `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. Do not ask the human for the key and do not ask them to run it. Call `register_spender_key` with the printed 33-byte public key and this pot id. Then point them at `https://dev.zappi.money/account/pots/<id>#pot-allowance-policy` and tell them to press **Sign allowance**. Listing pots is not this request. `keyHolder: nest` is not this request: do not install the spender and do not promise an approve URL. That refusal stays `allowance_required`.

A pot that already exists and is not paired uses `start_pairing` or `attach_pot`. When it is not paired, call `start_pairing` and give that URL. This attaches the agent. It is not an allowance. Each payment needs your approval. Set a spending limit to pay while this browser is closed. Link `https://dev.zappi.money/account/pots/<id>#pot-allowance-policy`. Before `create_pot` or `zappi-cli pots create`, if `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. It creates and seals the key when this machine has none. Do not ask the human for the key and do not print the phrase. The create call passes `spenderPublicKey` from `pubkey`, and a later `start_pairing` or `zappi-cli pots pair` that replaces an expired link passes that 33-byte key. Do not call `register_spender_key` or `zappi-cli pots spender` for that pairing. Approve stores the public key. Keep `register_spender_key` when the human later asks for an allowance on a pot whose pair URL had no key. `attach_pot` assigns a pot already on the account. After pairing, a host-held send with no signed allowance still returns `approveUrl`. Call `send` and hand that URL over. Do not sign that send from this chat.

## CLI

The package is `@zappimoney/zappi-cli`. It needs Node.js 20.9 or newer. It does not speak MCP.

```bash
npm install -g @zappimoney/zappi-cli
zappi-cli pots create
```

Do not use npx. `zappi-cli --help` prints the usage from the installed binary.

Before `create_pot` or `zappi-cli pots create`, ask once: "What should this pot be called? Say skip and I’ll pick a name you can change later." The only question is the name.

A name is `label` on MCP and `--label` on the CLI. Skip is `skipName: true` or `--skip-name`. The handoff then shows the generated name and says they can rename it later. Do not name a rename tool. Do not ask again on the happy path. On `need_choice`, ask that `message` only, one option per choice, in order, then call again with `label` or `skipName: true` on MCP, or `--label` or `--skip-name` on the CLI.

After the tool returns, write this block, with a blank line between parts. The pair URL is the raw URL on its own line, not a phrase with the link in the middle:

```
Pot: <name>

<pairUrl>

Opening that link signs you in and creates this pot. When you finish, it is paired to this chat.

This pot is not the default. Should I make it the default?
```

Do not print a pairing code and do not unpack `code=` from the URL. If the link does not open, say they can paste the code from the link on the pairing page. Do not ask them to paste it in chat. Call `set_default_pot` only after they say yes and the page has finished. The pot does not exist until then. Before `create_pot` or `zappi-cli pots create`, if `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. It creates and seals the key when this machine has none. Do not ask the human for the key and do not print the phrase. The create call passes `spenderPublicKey` from `pubkey`, and a later `start_pairing` or `zappi-cli pots pair` that replaces an expired link passes that 33-byte key. Do not call `register_spender_key` or `zappi-cli pots spender` for that pairing. Approve stores the public key.

When the website is signed into a different Zappi account than this chat, tell the human to switch the website to the account this chat is using and open this same pair link. Do not create a new pot for that mismatch. Ask for a new pair link only when they are already on this chat's account and the page says this agent connection cannot take the pot.

Do not run `zappi-cli login` first, and do not ask the human to come back before the phrase is done. Do not start `zappi-cli pots spender` on this visit. `zappi-cli login` saves a login for a later command. `zappi-cli guest` starts a pot without an account. The guest secret is not printed. `zappi-cli pots create --auth-choice skip` starts a guest when this login has never signed in. There is no spend mode and no per-pot limit on this path. The signed allowance is the only cap.

After install, read one playbook shipped with the package before creating a pot, depositing, or spending. Leave the others closed.

| Skill | When |
| --- | --- |
| zappi-cli-account | `login`, `whoami`, `logout`, `guest`, `guest claim` |
| zappi-cli-pot | create, list, connect, disconnect, pair, balance, spender |
| zappi-cli-deposit | `deposit rails`, `deposit assets`, `deposit networks`, `deposit address` |
| zappi-cli-spend | `pots send`, allowance pull, approve URL, `txid` |

Commands for this login:

| Command | What it does |
| --- | --- |
| `zappi-cli whoami` | Account email, or guest mode |
| `zappi-cli login` / `zappi-cli logout` | Save or revoke this login |
| `zappi-cli guest` | Start a pot without an account |
| `zappi-cli guest claim --pot <id>` | Move that pot onto the account |
| `zappi-cli pots` | List pots on this login |
| `zappi-cli pots create [--label] [--skip-name]` | Create a pot. The only question is the name |
| `zappi-cli pots connect --pot <name-or-id> [--default]` | Connect a pot to this login |
| `zappi-cli pots disconnect --pot <name-or-id>` | Remove it from this login |
| `zappi-cli pots pair [--pot <id>]` | Approve URL |
| `zappi-cli pots balance [--pot <id>]` | Balance |
| `zappi-cli pots spender [pubkey] [--pot <id>]` | Register the allowance spender |
| `zappi-cli deposit rails [--pot <id>]` | Ways to add money |
| `zappi-cli deposit assets [--pot <id>]` | Assets |
| `zappi-cli deposit networks [--asset] [--pot <id>]` | Networks |
| `zappi-cli deposit address [--asset] [--network] [--pot <id>]` | Deposit address |
| `zappi-cli pots send assets [--pot <id>]` | Payout assets |
| `zappi-cli pots send networks [--asset] [--pot <id>]` | Payout networks |
| `zappi-cli pots send --amount-cents <n> --to <address> [--asset] [--chain] [--memo] [--pot] [--idempotency-key] [--spark-tx-id] [--no-wait]` | Send |
| `zappi-cli pots send-status <requestId> [--pot <id>]` | Read one send |

Pass `--pot <id>` from the create result. Omitting it asks which pot. A pot name does not reattach a guest pot. `pots send` mints an idempotency key when `--idempotency-key` is omitted.

`zappi-cli pots spender` is the same registration as `register_spender_key` on this door. If `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. Do not ask the human for the key and do not ask them to run it. Pass that printed 33-byte public key to `zappi-cli pots spender` with this pot id. Do not install it because a pot was listed. `keyHolder: nest` is not this request: do not install the spender and do not promise an approve URL. That refusal stays `allowance_required`.

## Commands that share a word

`pots connect` puts a pot on this login. `pots attach` is device-code pairing for a host key.

`pots send` sends on this login. `send` is the wallet send. `request` prints an approve URL for an auth-required host pot.

`deposit rails`, `deposit assets`, `deposit networks`, and `deposit address` are this login. `deposit-options` and `deposit-address` are the wallet.

`pots balance` is this login. `balance` is the wallet balance, and with `--pot` it reads a pot through the wallet client.

Host-key commands (`propose`, `request`, `invite`) are in the installed CLI skill. This login does not use them.

## After the human pairs

This section is what you tell the human. Tool arguments stay in `read_skill` (`zappi-pot`, `zappi-spend`) or the CLI playbook. If that playbook says to stop as soon as `pairUrl` is shown, still say the lines below after the human finishes the page.

There is no spend mode and no per-pot limit. Do not ask how the pot should spend.

After the human finishes `pairUrl`, or the guest browser link, on a host-held pot, say these two sentences in this order, then the link, then stop:

1. You're paired. Each payment still needs your approval.
2. Set a spending limit to pay while this browser is closed.

The link is `https://dev.zappi.money/account/pots/<id>#pot-allowance-policy`. Use the pot id from that pair. Authorizing the app is the OAuth grant. It is not a spend key and it is not an allowance.

An allowance is opt-in and per pot. It is how that pot spends while the browser is closed. A Lightning invoice, Lightning address, or Lightning link returns `approveUrl` even when this pot has a signed allowance. Paste that URL and say Lightning needs approval each time. Do not pull. Do not ask them to change the allowance. Pairing does not turn it on. Another pot on the same account has its own allowance. `list_pots` does not register a spender key. A pot with no spender key has no allowance, and you say that instead of inventing one.

When the human wants an allowance on a host-held pot whose pair URL had no `spenderPublicKey`, run `pubkey` and call `register_spender_key` with that public key. On the CLI door that is `zappi-cli pots spender`. Do not ask the human for the key. `pubkey` creates it. Then send the pot link above and stop. Do not do this because `list_pots` ran. Do not call `register_spender_key` for a pairing that already passed `spenderPublicKey`. Do not do it when `send` returns `allowance_required`.

A pot that already exists and is not paired needs `start_pairing`, or `zappi-cli pots pair` on the CLI door. Before `create_pot` or `zappi-cli pots create`, if `zappi-allowance-spender` is missing, save `https://dev.zappi.money/spender/install` (Windows: `https://dev.zappi.money/spender/windows`) and run that file. Do not pipe it into a shell. Do not use npx. Run `zappi-allowance-spender pubkey`. It creates and seals the key when this machine has none. Do not ask the human for the key and do not print the phrase. The create call passes `spenderPublicKey` from `pubkey`, and a later `start_pairing` or `zappi-cli pots pair` that replaces an expired link passes that 33-byte key. Do not call `register_spender_key` or `zappi-cli pots spender` for that pairing. Approve stores the public key. The human approves that page. That approval attaches this host and stores that public key. It is not an allowance and it is not a spend key. `attach_pot` assigns a pot already on the account. Do not call `start_pairing` when `create_pot` already returned `pairUrl`. Call it only to replace an expired pair link, and pass `spenderPublicKey` again.

On `send`, paste `approveUrl` into the chat as soon as a host-held pot with no signed allowance returns it, then stop. Do not install the spender and do not register a key before that URL is in the chat. A signed allowance returns `allowance_pull`. On `allowance_required`, Zappi holds the key: ask once to set an allowance on the pot page, then call `send` again. Do not install `zappi-allowance-spender`, do not call `register_spender_key`, and do not give that pot an approve URL. Pass `asset` and `destinationChain` only when the human named them. A Lightning invoice, Lightning address, or Lightning link returns `approveUrl` even when this pot has a signed allowance. Paste that URL and say Lightning needs approval each time. Do not pull. Do not ask them to change the allowance.

## Rules

Do not print, log, or commit a session, a guest secret, a pot seed, a `zpc_` token, a device code, an unlock token, a spender phrase, or the files under `~/.zappi/` that hold them. Do not ask the person to paste a session, a `zpc_` token, a pot seed, a spender key, or a recovery phrase.

On a failed command, stop and report. An uncertain allowance pull stops too. Do not send again and do not call the API with another HTTP client.

When the website is signed into a different Zappi account than this chat, tell the human to switch the website to the account this chat is using and open the existing pair link. Do not create a new pot for that mismatch. Ask for a new pair link only when they are already on this chat's account and the page says this agent connection cannot take the pot.

`/.well-known/agent-skills` publishes `zappi-agent-pot`. That is a different skill. This document is `zappi-pot`.
