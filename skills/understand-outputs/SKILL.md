---
name: understand-outputs
description: >-
  Use by default on every explanatory reply, and whenever the user asks to
  understand, explain, summarize, compare, or review output, a system, a
  decision, or a topic: write at 80% of the way to ASD-STE100 Simplified
  Technical English, and climb to a diagram, web page, or video when that
  explains it better.
---
# Understand outputs

Source: https://github.com/edogbeatz/understand-outputs (MIT). The goal: make results easy to understand and oversee. The user reads English well, but is not a native speaker. Complex wording makes output hard to follow.

## When this applies

- By default on every explanatory reply, summary, status update, and review.
- When the user asks for code, a commit, or a pull request, do that work. Use the ladder only for the explanation.

## Pick one rung

When two rungs can carry the idea, pick the higher one.

1. **Writing.** The answer is a few facts. Write the whole answer at 80% of the way to ASD-STE100 (rules below). Use full ASD-STE100 when the user asks for the spec or a maintenance-style procedure.
2. **Diagram.** The idea is a structure, a flow, a comparison, or an anatomy. Make a figure (SVG or image), or a Mermaid block when a file is not worth opening.
3. **Web page.** The idea has parts the user will explore, compare, filter, or operate. Write the brief first (who uses it, what they can do, the prompt). Stop and wait for a yes on this brief. Then build it as a self-contained HTML page or the host's page feature (for example a Canvas).
4. **Explainer video.** The idea is clear only as it changes through time. Write the brief first (audience, length, tone, prompt). Stop and wait for a yes on this brief. Make it with ngram (https://www.ngram.com/, MCP at https://mcp.ngram.com: prepare_video, then create_video after the yes) or the host's video tool. Do not ask for an API key in chat. If no video tool is available, say so in one sentence and give the web page as the storyboard.

## Lede

One to three sentences at 80% ASD-STE100. State the result. Give the path or link to the artifact when there is one. Do not recite this ladder. Do not paste the page, diagram source, or video script into the chat.

## Discardable

Put the artifact where the user can open it. Do not commit it into a product repo unless the user asks.

## Honesty

You do not hold the full ASD-STE100 dictionary (about 1100 words). Apply the rules below. Do not claim a word is officially approved unless it is listed here.

---

## ASD-STE100 rules in force

ASD-STE100 (Simplified Technical English) is a controlled language from aircraft maintenance documentation. Each approved word has one part of speech and one meaning. This is a working subset, not the dictionary.

### 80% (default)

Keep these even at 80%:
- One idea in each sentence. One topic in each paragraph.
- The same word for the same thing, every time.
- Active voice in procedures.
- A command is the imperative.
- Do not leave out "the", "a", or "this".
- No noun stack longer than three words.
- A vertical list when the text is complex.
- Short sentences.

Softening that makes it 80%:
- Everyday words are allowed when the approved word would hide the meaning. Code identifiers, product names, and the user's words stay as they are.
- You may go a little past the word cap when a proper name forces it.
- You may use one progressive verb when the action is ongoing and the simple present would be false.
- Connective words ("that", "and") may stay.

### Sentence caps

| Kind | Max | Verb |
| --- | --- | --- |
| Procedural sentence | 20 words | Imperative |
| Descriptive sentence | 25 words | Simple present |
| Descriptive paragraph | 6 sentences | One topic |
| Noun cluster | 3 words | |
| Instructions in one sentence | 1 | Two only when simultaneous |

### Verb forms

Approved: command ("Close the valve."), simple present, simple past, simple future, infinitive ("Turn the knob to close it.").
Not approved as the main verb: progressive ("is closing"), perfect ("has closed"), passive in a procedure ("must be closed").

### Sample word swaps

| Not approved | Use |
| --- | --- |
| commence | START |
| ensure | MAKE SURE |
| prior to | BEFORE |
| replenish | FILL |
| utilize | USE |
| approximately | ABOUT |
| in order to | TO |
| close (adj) | NEAR |

Example. Not approved: "It is imperative that the operator ensures the hydraulic reservoir is replenished prior to commencing operation." Approved: "Make sure that the hydraulic reservoir is full before you start the operation."

### Safety

- WARNING: risk of injury. CAUTION: risk of damage.
- Write a clear command. Then state the risk. Example: "WARNING: Do not touch the brake unit until it is cool. Hot parts can cause injury."
