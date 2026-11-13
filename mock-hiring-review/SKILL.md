---
name: mock-hiring-review
description: Run a blind hiring-manager review of final application documents for a specific job, internship, or program. Use for application critiques, interview-likelihood assessments, and repeat reviews. Requires a fresh independent reviewer; otherwise prepare a packet for a separate session and disclose the limitation.
---

# Mock hiring-manager review

Simulate a stranger reading the application cold. Evaluate what the final documents communicate, without leaking candidate intentions, source comments, or earlier feedback.

Read [references/review-protocol.md](references/review-protocol.md) before preparing a review. Use [references/reviewer-prompt.md](references/reviewer-prompt.md) as the fixed reviewer prompt.

## Prepare the evidence

Collect the final documents in their submission format, the public listing URL, and optional public company information supplied by the user. Rebuild stale rendered documents from their current sources. If rendering is unknown, ask rather than guess. Markdown or plain text is admissible only when submitted as-is.

Create a new isolated temporary folder for each round. Copy only the final application documents under neutral filenames, preserving extensions. Keep sources, candidate notes, previous reviews, manifests, and comparison records outside the reviewer's accessible files. The listing and optional company information belong in the prompt.

## Select independent execution

Choose the first available mechanism that satisfies the protocol:

1. A new native subagent with no inherited conversation and restricted file access.
2. A new external agent process or session with clean context and restricted file access.
3. A packet and filled prompt for a manually launched independent session.

Let the host harness select the reviewer model and reasoning level using its configured defaults, available models, task needs, and token or cost budget. This skill imposes no preferred model tier or minimum reasoning level. Do not automatically upgrade to a more expensive model or higher reasoning level. Honor explicit user selections and budget limits; if a requested setting is unavailable, disclose that and use the harness's configured fallback within those limits. If selection controls are unavailable, use the harness default.

Record the actual model, reasoning level, prompt version, evidence version, and isolation limitations outside the reviewer packet; record settings that cannot be determined as unknown. Model and reasoning selection does not relax the independence or evidence requirements below.

A new agent alone does not establish isolation. Verify context inheritance and access controls before launching. If access cannot be restricted, report the limitation and prepare the packet for a suitable separate session. Never substitute the current conversation or claim that instructions to ignore other files enforce isolation. Do not claim a blind review completed until independent execution is verified.

Start a fresh reviewer each round. Provide only the filled fixed prompt and admissible evidence. Never resume, message, or brief an earlier reviewer. Do not mention the round number, revisions, prior verdicts, or desired outcome.

## Return and compare

Present findings faithfully, trimming length without softening them. Keep coordinator commentary separate. Do not revise documents, rebut findings, or give additional candidate context to the reviewer unless the user requests action; a reviewer given such context cannot supply a fresh blind verdict afterward.

From round two onward, compare verdicts and concerns in the coordinating session only. Match concerns by meaning and state uncertain matches. Flag changes in model, effort, prompt, posting, document access, or isolation that limit comparability. Repeated concerns are useful evidence, but a concern disappearing from one review does not prove it was fixed.

If asked to revise, keep every claim faithful to the candidate's actual work. For another review, rebuild final documents and repeat with a new packet and reviewer.
