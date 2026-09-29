# AI Feature Readiness Checklist

Feature: ______________________  Owner: ______________  Target launch: __________

## 1. Definition of good
- [ ] The task is written in one sentence, with the user and the decision it supports
- [ ] A fixed eval set exists (minimum 50 cases), including messy and adversarial inputs
- [ ] Pass threshold agreed and written down (e.g. "≥ 90% correct, 0 critical failures")
- [ ] Baseline measured: how does the non-AI path (or a human) score on the same set?

## 2. Failure behaviour
- [ ] Low-confidence output: what the user sees ___________________
- [ ] Timeout or provider outage: fallback ___________________
- [ ] Refusal or empty answer: handling ___________________
- [ ] Malformed output (bad JSON, wrong schema): validation and retry rule ___________________
- [ ] The user can correct or undo the AI's output

## 3. Red lines
- [ ] Tenant isolation: prompts and retrieval never mix data across accounts (tested)
- [ ] No irreversible action (send, pay, delete, publish) without explicit human approval
- [ ] Prompt injection: instructions inside user content or documents are treated as data (tested)
- [ ] Sensitive fields are masked before leaving your system, where required

## 4. Cost at scale
- [ ] Cost per request measured: ______
- [ ] Projected monthly cost at 10x current usage: ______
- [ ] Rate limits and a per-account budget cap exist
- [ ] Cheaper model or cached path considered for the easy 80% of requests

## 5. Drift and ownership
- [ ] Eval set runs in CI on every prompt change
- [ ] Eval set runs before any model or provider upgrade
- [ ] Production quality signal defined (thumbs down, correction rate, escalations)
- [ ] Named owner for the eval set and the rollback decision
- [ ] Rollback path tested: previous prompt/model can be restored in minutes

## Sign-off
- Product: __________  Engineering: __________  Date: __________
