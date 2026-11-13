# Blind-review protocol

## Admissible evidence

- Finished documents exactly as they will be submitted: rendered PDF or another final format. A Markdown or plain-text document is final only when submitted as-is.
- The public position listing, or its faithfully captured public text if the page cannot be read.
- Public company context supplied by the user, and company research the reviewer performs from the listing site and company public pages.

The coordinator must not independently expand company research. Do not search for the candidate. Exclude candidate-side notes, application trackers, fit assessments, motivations, strategy, source documents, comments, TODOs, dead text, build logs, prior feedback, and AI commentary about the candidate. Do not filter mixed private notes into a job description; obtain the public posting instead.

Rebuild final outputs when their sources have changed. Modification times are a useful warning, not proof that an output matches its source. Ask how to render unknown source-only documents.

Check that the reviewer's document reader exposes the intended submitted content, rather than hidden comments, attachments, tracked changes, or source material. Do not silently change visible content to produce a cleaner review. If the reader cannot faithfully inspect the submission, disclose the limitation before treating layout or content findings as reliable.

## Isolation requirements

Each round needs a new session with no inherited conversation, earlier reviews, shared memories about the candidate, or candidate-specific briefing. Restrict the reviewer's accessible files to the curated application documents and any operational resources needed to read them. Keep preparation records, source paths, previous packets, and coordinator notes outside that access boundary.

Use neutral names such as `CV.pdf` and `CoverLetter.pdf`, preserving the final format. Do not include company, role, or round labels that reveal revision history in filenames. Pass the listing and optional public company information in the prompt, not additional packet files.

A clean folder is evidence curation, not an access control. A new working directory, a fresh process, or a no-history agent that can still read the candidate's source tree does not satisfy restricted access. Verify the execution mechanism's actual context and filesystem controls. Limit browsing to the listing and public company context; do not supply unrelated account or private workspace access.

If independent execution cannot be established, stop before running the review and prepare the packet for a separate session with suitable access restrictions. State which guarantee is missing. Do not describe an in-context critique or an unrestricted agent run as a completed blind review.

## Prompt stability

Fill the bracketed placeholders in `reviewer-prompt.md`; do not add backstory or leading questions. Omit the optional-company line if none was supplied. Drop the cover-letter bullet if there is no letter.

If the listing will not load, obtain its public text through available browsing or a public board endpoint, or ask the user for the posting text. Replace the listing URL/read-posting lines with that text and its source URL. Keep candidate commentary out. Record the substitution outside the packet. Do not invent missing requirements; if no authoritative posting is available, pause the role-specific review.

Keep the same evaluation wording across rounds. Record the template version or hash and actual execution settings privately so changes can be identified during comparison.

## Contamination and comparison

If a reviewer receives prior feedback, source commentary, candidate backstory, or other forbidden evidence, mark that run non-blind and exclude it from independent-round comparisons. Correct the access or context leak and start a new reviewer; do not ask the contaminated reviewer to forget.

Keep findings and cross-round comparisons in the coordinating session. Preserve uncertainty and distinguish what documents show from what the candidate may actually have done. Implement feedback only on request and never strengthen a claim beyond the underlying facts.
