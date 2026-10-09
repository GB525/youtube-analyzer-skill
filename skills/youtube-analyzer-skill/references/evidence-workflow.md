# Evidence retrieval and preservation

Read this reference when gathering description links, assessing repositories, checking prior work, or saving an analysis.

## Description and URL checks

Retrieve the expanded description via an accessible metadata API/extractor or the YouTube page. Keep retrieval time and original link targets. Do not rely on chapter titles as a transcript. Caption extraction can use a working yt-dlp installation with caption-only options; media downloading is unnecessary when captions suffice. If a retrieval endpoint returns an empty response, treat it as failed evidence, not an empty transcript. Prefer another available retrieval method without cycling authentication or disabling TLS checks.

For each unique description URL:

- Open it using a suitable web or connector tool. Follow normal redirects and record the final destination. Deduplicate equivalent destinations while retaining the original links' context.
- Identify purpose: central tool/repository, tutorial/documentation, dataset, purchase/affiliate offer, sponsor, community, creator resource, or unrelated promotion.
- Record access status: checked, broken, restricted/login, unavailable, or inconclusive. A crawler failure alone does not prove the public link is broken; use a browser or another appropriate tool when useful and distinguish the outcomes.
- Check material claims on primary sources: product identity, current availability, maintenance, license, pricing or prerequisites if relevant. Record retrieval date; current details may differ from the recording.
- Inspect every description link at least to identify its destination and relevance. Deepen central or adoption-relevant resources. Do not recursively crawl entire sites; follow additional links only to resolve a material question. Large descriptions can use grouped summaries in chat and a full supporting ledger.
- Detect affiliate/tracking patterns but do not label an affiliate relationship as established without evidence. Check links without submitting forms, joining communities, purchasing, or downloading/running software.

When possible, use the official repository/product URL rather than a mirror or aggregator for factual conclusions. Unavailable sources remain explicit gaps; do not claim full URL coverage if some were not checked.

## GitHub repositories

Use available GitHub connectors or official GitHub pages/APIs. For every distinct linked repository, verify the owner/name, description, license, archived status, and visible maintenance/activity. Star counts are dated popularity signals, not quality scores. Follow redirects, including repository renames.

For repositories central to the video or relevant to adoption, record the inspected commit or release and review README, license, relevant manifests, installation guidance, and key implementation/docs supporting advertised functions. Assess:

- What actually ships, and what the demonstrated environment adds separately.
- Runtime/dependency burden, platform compatibility, configuration, credentials/permissions, external services, and documented costs.
- Published security/update practices and concrete concerns evident in the inspected files. This is a bounded adoption review, not a comprehensive security audit.
- Fit with current tooling, overlap with existing practices, maintenance responsibility, and whether selective curation is more useful than wholesale adoption.

Separate static repository inspection from running tests or installing the project. Do not execute repository code merely to analyze it. Name unresolved questions and inspect additional primary files only when they can materially change the recommendation. A prior pinned review does not establish the state of today's revision.

## Prior assessments and project fit

When a resource may overlap with the user's work, search available chat/project listings and known project files for its identity or URL. Read the actual assessment and current adoption record; a chat title or summary is only a discovery aid. Read-only inspection does not require messaging another chat. Do not send messages to other chats without explicit user authorization.

Distinguish a recommendation from an implemented change. Corroborate implementation through the receiving project's current records when accessible. Preserve project-specific boundaries: shared engineering standards do not mean a product has installed a runtime, shared credentials, or deployed a tool. If no relevant history is found, say that rather than inventing continuity.

## Supporting artifacts

Use the task's designated deliverable directory, normally `outputs/`, with a video-specific subfolder when analyzing multiple videos. Keep disposable retrieval files under `work/`. Save:

- **analysis.md:** the full substantive analysis delivered in chat; maintain consistent judgments, evidence, and coverage.
- **source-notes.md:** detailed timestamped paraphrases, verified metadata, caption provenance and quality, description context, and material evidence. This is a reusable analyzer input, not a fabricated verbatim transcript. Store raw retrieved captions as working evidence; redistribution must respect source rights and applicable quoting limits.
- **link-checks.md:** original and final public URLs, purpose, access result, checked date, key findings, and repository revision when inspected. Do not expose sensitive query parameters.
- **watch-report-N.md:** each full Watch response, including source, requested interval, actual coverage when known, engine, and reported errors. Save directly from returned output where possible; if copied afterward, identify that provenance. Keep reported token usage if provided, without calling it a measured price.

Do not generate empty Watch reports when Watch was unnecessary. Record why in coverage. If saving is unavailable, deliver the full analysis in chat and explain the artifact limitation. Provide only a few meaningful links in the final response; the user should not have to read Markdown to obtain the answer.

## Completion criteria

The analysis is complete when accessible speech evidence and the full description have been considered, every description link has a recorded access/result status, material visual gaps have been reviewed or disclosed, relevant prior work has been checked when accessible, and the complete chat response distinguishes evidence from judgment. Failures can yield a bounded assessment; do not label that as full evidence coverage. Resolve material contradictions before presenting a confident recommendation.
