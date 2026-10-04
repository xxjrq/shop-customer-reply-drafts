# Shop Customer Reply Drafts

![Shop reply drafts: turn buyer questions into ready-to-copy replies](assets/promo-1600x900.png)
A free Markdown Skill with no third-party API key required. It turns product facts, store policies, and buyer questions into short, copy-ready customer-service drafts. It does not connect to a customer-service API or send messages. Provide the facts and question to receive a reply draft and a short list of any missing information.

## What it does

It returns a pre-sales, after-sales, or manual-review classification; a natural Chinese reply draft; missing information; and items to verify. It never invents stock, refund eligibility, shipping dates, delivery dates, discounts, or order status.

Use [fixtures/success.json](fixtures/success.json) for a ready-to-run input and compare it with [fixtures/success.expected.md](fixtures/success.expected.md). [fixtures/failure.json](fixtures/failure.json) demonstrates how missing order and policy data is surfaced instead of guessed.

## Optional browser verification

The Skill works without a browser. For separately authorized checks in an already logged-in shop page, install [Easy WebBridge on GitHub](https://github.com/xxjrq/easy-webbridge), with [Gitee](https://gitee.com/xxjrq/easy-webbridge) as a mirror. Select one explicit `browserId`, create one isolated session group per task, and never broadcast across accounts. Verification only informs a draft; sending remains a user decision.

## Self-test

```bash
node scripts/self-test.mjs
```

## Attribution and license

This is an original implementation under the [MIT License](LICENSE). It only checked the public Skill directory conventions in [Anthropic Skills](https://github.com/anthropics/skills) and the installation entry point of [Easy WebBridge](https://github.com/xxjrq/easy-webbridge); no code or documentation was copied. Each referenced repository retains its own license.

## Install

```bash
npx skills add xxjrq/shop-customer-reply-drafts
```

Alternatively, copy this repository folder into your Agent’s skill directory, then invoke `$shop-customer-reply-drafts` with your input.
