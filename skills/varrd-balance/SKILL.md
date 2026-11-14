---
name: varrd-balance
description: Check VARRD tests remaining, balance, and plan. Use when the user asks about credits, billing, or how much research budget remains.
version: 1.0.0
tools: ["Bash"]
homepage: https://varrd.com
metadata: {"openclaw": {"requires": {"bins": ["varrd"]}, "emoji": "💰"}}
---

# VARRD Balance — Tests Remaining

Use this skill to check how many tests the user has left before running paid operations.

## Command

```bash
varrd balance
```

## How It Works

Returns tests remaining, the plan (if any), the per-test price, the prepaid balance in cents, whether billing enforcement is enabled, and available packs for purchase.

## When to Check

- Before running `varrd research` or `varrd discover` (each completed test costs $1.00)
- After getting a "credits depleted" error
- `varrd scan`, `varrd search`, `varrd hypothesis`, and `varrd reset` are free — no need to check first

## Cost Reference

| Operation | Cost |
|-----------|------|
| scan, search, hypothesis, balance, reset | Free |
| Charts, data queries, conversation, identical reruns | Free |
| One completed test (event study, backtest, retest, stop optimization) | $1.00 |
| The same on a Pro plan, after the 300 included tests | $0.75 |

## If Credits Are Low

Direct the user to purchase more at [app.varrd.com](https://app.varrd.com). Packs: $20 / $50 / $200 (one test per dollar). Plans: Starter $50/month (50 tests + 20 watched strategies), Pro $300/month (300 tests + 100 watched strategies, $0.75 a test after). Agents can also add funds with `varrd buy-credits` ($5 minimum).

Signing up at [app.varrd.com](https://app.varrd.com) grants 3 free tests — link your agent to that account to use them. Agent accounts created directly via MCP/CLI start at $0.

## Cost

Free. No credits consumed.

## Python SDK Equivalent

```python
from varrd import VARRD
v = VARRD()
b = v.balance()
print(f"Balance: ${b.balance_cents / 100:.2f}")
```
