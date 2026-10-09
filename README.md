# botproof-registry

**The public record of who made which bot.** Every entry is signed. Every change is a pull request. CI checks the proofs before anything is merged.

- API: https://ao3575911.github.io/botproof-registry/api/index.json
- One bot: `/api/bots/<platform>/<botId>.json`
- Badge: `/badge/<platform>/<botId>.svg`
- CLI: [ao3575911/botproof](https://github.com/ao3575911/botproof)

## Add your bot

Use the CLI. `botproof publish` opens the pull request for you.

## What CI checks

1. Every file carries a valid Ed25519 signature.
2. Each creator's GitHub proof (gist or profile README) is live and owned by that account.
3. Each bot is signed by its creator's key.
4. Reviews come from registered creators, never the bot's own creator.
5. Revocations come from whoever signed the original.

Every proof is re-checked nightly when the site rebuilds.

## Layout

```
creators/github-<user>.json             linked accounts and key
bots/<platform>/<botId>/manifest.json   current signed manifest
bots/<platform>/<botId>/versions/       every signed version, by hash
bots/<platform>/<botId>/attestations/   signed reviews
revocations/<hash>.json                 signed withdrawals
```

"Identity linked" is not "safe". A listing tells you who made a bot, not whether to trust it. Data is CC0.
