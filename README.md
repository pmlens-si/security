# Qualys ROCky, wherever you work

> **Concept demo with sample data.** This is a product concept, not a shipping Qualys feature. Every company, person, score, asset and IP address in it is fictional. IP addresses come from the documentation ranges.

**Live demo:** https://pmlens-si.github.io/security/

## The idea

ROCky is the AI assistant inside Qualys ETM and the Risk Operations Center. Today a leader has to sign in, open ETM and launch ROCky to get an answer.

This concept takes ROCky further, into the places security leaders already work: **Microsoft Teams, Slack and WhatsApp**, plus **Claude and ChatGPT** through a read-only Qualys MCP server. No login, no opening ETM, no launching ROCky. The leader asks by voice or text, gets the answer and the fix, and approves with one tap.

Detailed data never leaves Qualys. The chat shows summaries only. Hostnames, IP addresses and full findings open through a secure Qualys link that uses the person's own SSO, is view-only, expires and is logged.

## What the demo shows

The core flow follows three Qualys capabilities:

1. **Detect with InstaScan.** A new zero-day is found on exposed servers 13 minutes after disclosure, with no scan needed.
2. **Prioritize with TruConfirm.** Safe exploit validation shows which critical findings are actually exploitable.
3. **Auto-remediate.** Wave patching, guided by a Patch Reliability Score, with approval in the chat.

It also covers:
- TruRisk score, trend and risk appetite, and the business entities above appetite
- Top risks and threats exploited in the wild
- Compliance posture by framework
- Patch status and team SLAs
- Approvals, tickets and job assignment, including ITSM tickets from Teams and Slack
- Alerts for critical findings and pending approvals
- Executive and board briefs, some with a 15-second narrated video
- TotalAI (shadow AI, prompt injection tests, AI agents at runtime) and TotalCloud toxic combinations

## Opening the demo

Open the live URL and pick an app under **Open the demo in**, or link straight to one:

| App | Link |
| --- | --- |
| Microsoft Teams | https://pmlens-si.github.io/security/#demo-teams |
| Slack | https://pmlens-si.github.io/security/#demo-slack |
| WhatsApp | https://pmlens-si.github.io/security/#demo-whatsapp |
| Claude | https://pmlens-si.github.io/security/#demo-claude |
| ChatGPT | https://pmlens-si.github.io/security/#demo-chatgpt |

In each app, tap a suggested topic or type a question such as "what needs my approval?". On desktop, the tabs at the top switch between apps. On a phone each app opens full screen, and the back arrow returns to the overview. Opening an app again from the overview starts a fresh chat.

## Sample data

The demo uses a fictional company, Acme Global, with CISO Alex Morgan and colleague Shailesh Soni. All numbers are illustrative. No customer data and no live Qualys connection are involved.

## Files

- `index.html`: the whole demo in one self-contained page (styles, scripts, images and videos inline)
- `.nojekyll`: tells GitHub Pages to serve the page as is

To update the demo, replace `index.html` and push to `main`. GitHub Pages republishes it automatically.
