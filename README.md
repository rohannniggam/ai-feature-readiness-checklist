# AI Feature Readiness Checklist

A short, practical checklist for deciding whether an AI feature is ready for paying customers, not just ready for a demo.

Demos use the best case. Customers bring the worst case at scale: messy inputs, questions the prompt never imagined, data that should not leave one account, and quality that drifts after a model update. This checklist makes those cases explicit before launch.

Maintained by [Rohann Niggam](https://rohanniggam.com), fractional product, technology and AI advisor and founder of [Aarohii AI Solution](https://aarohii.com). Background essay: [The AI feature that looked done](https://builddecisions.beehiiv.com/p/the-ai-feature-that-looked-done).

## How to use it

1. Copy [`CHECKLIST.md`](CHECKLIST.md) into your feature spec or PR description.
2. Fill in every line with a number, an owner or a link. "Looks good" is not an answer.
3. Turn the failure modes into test cases. [`examples/eval-cases.yaml`](examples/eval-cases.yaml) shows the shape.
4. Re-run the eval set on every prompt change and every model upgrade.

## The five questions

| # | Question | Ready when |
|---|---|---|
| 1 | What does "good" mean, as a number? | A written pass threshold on a fixed eval set, agreed by product and engineering |
| 2 | What happens when the model is wrong, slow or silent? | Defined UI and system behaviour for low confidence, timeout, refusal and malformed output |
| 3 | What must never happen? | Named red lines (data leaking across tenants, irreversible actions without a human, invented facts in regulated text) with tests that prove them |
| 4 | What will it cost at real volume? | Cost per request and per active account estimated at 10x today's usage, with a budget alert |
| 5 | How will we know it got worse? | Quality and cost monitored in production, with an owner and a rollback path for model or prompt changes |

## License

MIT. Use it, adapt it, share it.
