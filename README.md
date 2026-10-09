# YouTube Analyzer Skill

**A complete video assessment in chat, with checked sources and targeted visual review.** Maintained by Grevalyn LLC. MIT licensed.

The skill gathers YouTube captions, the expanded description, chapters, and resource links; evaluates claims and commercial intent; checks linked GitHub repositories; and uses the optional Watch skill where visuals could change the conclusions. Supporting evidence is saved when file tools are available. The complete analysis remains in chat.

## Website and sample assessment

[Visit the YouTube Analyzer website](https://youtube-analyzer-grevalyn.grevalyn.chatgpt.site/) to explore the workflow, view the infographic, read a complete sample assessment, and find installation instructions.

The sample assessment, **YTA5a: Matt Pocock Skills Repo**, includes the original YouTube video link and a note that Watch was not used. The website introduces the skill; video analysis happens in your agent after installation.

## Install in Codex

Paste this into Codex:

```text
Use $skill-installer to install youtube-analyzer-skill from:
https://github.com/GB525/youtube-analyzer-skill/tree/v1.1.0/skills/youtube-analyzer-skill
```

This installs the tagged version, rather than an unreviewed future update. Start a new turn or session afterward; restart the app if the skill does not appear.

Alternatively, download `youtube-analyzer-skill-v1.1.0.zip` from [Releases](https://github.com/GB525/youtube-analyzer-skill/releases). Extract the `youtube-analyzer-skill` folder into your agent's skills directory, preserving its `agents/` and `references/` folders. For an existing installation, ask the agent to update it rather than creating duplicate copies. Codex's skill installer can select the proper local destination; no particular operating system or personal folder is assumed here.

## Use it

```text
Use $youtube-analyzer-skill to assess this video:
[paste the YouTube URL]
```

You can add a decision question, such as whether a tool fits your workflow, which claims are demonstrated, or whether a tutorial can be reproduced. No personal project history is required. If you provide relevant prior work, the skill can compare it with the video's recommendations.

## Optional: install Watch for visual evidence

The analyzer can work from captions and checked links without Watch, but must label visual questions it cannot resolve. For screen demonstrations, charts, hardware, or other consequential visuals, install [Watch](https://github.com/bradautomates/claude-video) separately:

```text
Use $skill-installer to install the watch skill from:
https://github.com/bradautomates/claude-video/tree/main/skills/watch
```

Then follow Watch's setup instructions and choose your engine. Gemini processes video through Google and needs your own API key; the local engine has different dependencies. Refer to Watch's current documentation for setup, data handling, and supported environments. This repository includes no Watch code, provider credentials, or automated installer.

**Targeted clips are preferred over whole-video processing.** The analyzer reads the transcript first and asks focused visual questions. When broad review is needed, it breaks longer footage into roughly **10–15-minute sections**, adjusts boundaries around demonstrations, preserves original timestamps, and combines the findings. These are practical defaults, not guaranteed provider limits. Smaller ranges may be required.

## What you get

The chat analysis includes:

1. Channel trust and red flags
2. Commercial intent and bias
3. Executive summary
4. Core takeaways and insights
5. Tech stack, tools, resources, and relevant repository findings
6. Workflow or action plan
7. Products, hardware, and gear
8. Fit with your existing work, when available, and recommended next steps

A final coverage note explains caption provenance, checked links, reviewed video ranges, and missing evidence. Where file tools are available, the agent saves the analysis, detailed source notes, link-check record, and full Watch responses. A summary is never presented as a verbatim transcript.

## Requirements and limitations

- A skill-capable agent with web access for checking public sources. Local extraction/shell access may be needed when browser or connector tools cannot retrieve captions.
- Captions, private resources, and linked pages may be inaccessible. The agent reports gaps rather than fabricating results.
- Watch is optional. Each recipient supplies their own accounts, engine configuration, and credentials; provider charges or rate limits may apply.
- Gemini observations are fallible model reports, not an independent security audit. Spoken claims, visuals, external facts, and interpretation remain distinguishable.
- The skill is an instruction workflow, not a standalone application or a guarantee of retrieval. It has been structurally validated; the predecessor workflow was exercised on a real video. A full fresh-account installation and every provider/platform combination have not been tested.
- Repository inspection does not authorize installing or executing linked projects. Analysis does not authorize publishing, contacting people, or modifying product implementations.

## License and credits

Copyright (c) 2026 **Grevalyn LLC**. Analyzer instructions and documentation: [MIT license](LICENSE).

The original analysis structure comes from Grevalyn LLC's YouTube Transcript Analyzer. Optional Watch: **Bradley Bonanno / bradautomates**, maintained at [claude-video](https://github.com/bradautomates/claude-video), under its [own MIT license](https://github.com/bradautomates/claude-video/blob/main/LICENSE). See [attribution](skills/youtube-analyzer-skill/ATTRIBUTION.md). No affiliation with the referenced products is implied.

## Feedback

Open an issue with the public video URL, the result you expected, and which evidence was missed. Remove private captions, personal project information, credentials, and sensitive URL parameters before sharing examples.
