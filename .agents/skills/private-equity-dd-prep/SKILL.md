---
name: private-equity-dd-prep
description: "Use when CK asks to run `private-equity:dd-prep` or needs the converted Claude finance workflow for this command, including CFA real-world applications, practitioner artifacts, investment analysis, financial modeling, deal analysis, wealth workflows, diligence, screening, audits, or finance-agent review."
---

# private-equity:dd-prep

## Trigger Aliases

- `private-equity:dd-prep`
- `private-equity-dd-prep`

## Workflow

Prepare targeted questions and red flags for a due diligence call or meeting.

Provide: (1) company name, (2) meeting type (management presentation, expert call, or customer reference), (3) topic focus area. Ask for these if not provided.

Preparation framework:
1. **Background synthesis** — summarize what's known about the company/topic from available materials
2. **Key hypotheses to test** — what are you trying to confirm or disprove in this call?
3. **Targeted questions** — 10–20 specific, open-ended questions organized by topic; prioritized for a 60-minute call
4. **Benchmarks** — what does "good" look like? What metrics or answers would be incrementally positive vs. negative?
5. **Red flags to probe** — known risks or inconsistencies to investigate; how to probe without telegraphing concerns
6. **Competitive positioning questions** — how does the company describe competitors? What does it reveal about their own position?

For expert calls: frame questions around what a third-party expert would know that management wouldn't share.
For customer references: focus on renewal intent, competitive alternatives considered, and unmet needs.

Deliver a call prep sheet ready for use in the meeting.


## Codex Usage Notes

- When used for a CFA vault Real-World Application, save the final artifact under the module's Real-World Applications folder and include the required LOS connection callout.
- Ask for missing required inputs, such as ticker, company, deal, client case, or model type, before starting.
- Use available local files, SEC/company disclosures, market data tools, or clearly marked assumptions when proprietary sources named in the original Claude command are unavailable.
- Keep ordinary concept notes separate from practitioner artifacts.
