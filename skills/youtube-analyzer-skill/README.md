# YouTube Analyzer Skill

**A complete video assessment in chat, with checked sources and targeted visual review.** Maintained by Grevalyn LLC. MIT licensed.

The skill gathers YouTube captions, the expanded description, chapters, and resource links; evaluates claims and commercial intent; checks linked GitHub repositories; and uses the optional Watch skill where visuals could change the conclusions. Supporting evidence is saved when file tools are available. The complete analysis remains in chat.

## Install in Codex

Paste this into Codex:

```text
Use $skill-installer to install youtube-analyzer-skill from:
https://github.com/GB525/youtube-analyzer-skill/tree/v1.2.0/skills/youtube-analyzer-skill
```

This installs v1.2.0, which adds opt-in stack comparison and automatic local frame-and-caption review. Existing installations do not update automatically; ask your agent to update the installed skill using the versioned URL above. Start a new turn or session afterward; restart the app if the skill does not appear.

Alternatively, download `youtube-analyzer-skill-v1.2.0.zip` from [v1.2.0 release](https://github.com/GB525/youtube-analyzer-skill/releases/tag/v1.2.0). Extract the `youtube-analyzer-skill` folder into your agent's skills directory, preserving its `agents/` and `references/` folders. For an existing installation, ask the agent to update it rather than creating duplicate copies. Codex's skill installer can select the proper local destination; no particular operating system or personal folder is assumed here.

## Use it

```text
Use $youtube-analyzer-skill to assess this video:
[paste the YouTube URL]
```

You can add a decision question, such as which claims are demonstrated or whether a tutorial can be reproduced. Before personal stack/project research, the skill asks whether to include that comparison:

- **No, standalone (quicker)** — skips personal project research for this assessment.
- **Yes, compare with my stack** — includes relevant project context and fit analysis.
- **Never compare (remember this)** — saves the preference locally and skips the question on future assessments.

Skipping stack comparison usually gives quicker results by removing the extra research; source retrieval and visual checks can still take time. You can request comparison explicitly for one video even with a remembered no-comparison preference, or ask the skill to resume asking. Preferences live in `~/.config/youtube-analyzer-skill/preferences.json`, outside the skill package. No preference is saved merely because a default option is displayed. No personal project history is required.

## Optional: install Watch for visual evidence

The analyzer can work from captions and checked links without Watch, but must label visual questions it cannot resolve. For screen demonstrations, charts, hardware, or other consequential visuals, install [Watch](https://github.com/bradautomates/claude-video) separately:

```text
Use $skill-installer to install the watch skill from:
https://github.com/bradautomates/claude-video/tree/main/skills/watch
```

For analyzer visual checks, **local frame-and-caption review is the default**: your agent retrieves accessible media/captions, selects relevant intervals, extracts frames, and inspects them automatically. Supply only the video URL and question; you do not prepare snippets. The local path requires download and frame-extraction tools (yt-dlp and FFmpeg/ffprobe). Existing captions need no additional speech model. Frame sampling can miss short transitions and does not analyze all audiovisual information continuously; the agent uses focused timestamps and reports coverage limits. Media extraction is local; interpretation happens in your agent's chat.

You can explicitly choose Gemini for a review or ask the analyzer to remember that choice. Gemini sends the source to Google and needs your own API key. The analyzer's optional remembered engine preference is `visual_review_engine` (`local` or `gemini`) in the same private preference file. Separately invoked Watch retains its own saved settings. Follow Watch's setup and transcription choices; neither a different engine nor a speech model is selected silently after a failure. This repository includes no Watch code, provider credentials, or automated installer.

**Short targeted intervals are preferred over whole-video processing.** The analyzer reads the transcript first and selects focused visual questions, usually reviewing tens of seconds to a few minutes around each consequential demonstration. Media can be downloaded once and reused for subsequent checks; current Watch may download the full video even for a short interval. When broad review is needed, it breaks longer footage into roughly **10–15-minute sections**, adjusts boundaries around demonstrations, preserves original timestamps, and combines the findings. These are practical defaults, not guaranteed provider limits. Smaller ranges may be required.

## What you get

The chat analysis includes:

1. Channel trust and red flags
2. Commercial intent and bias
3. Executive summary
4. Core takeaways and insights
5. Tech stack, tools, resources, and relevant repository findings
6. Workflow or action plan
7. Products, hardware, and gear
8. Recommended next steps, plus fit with your existing work only when selected

A final coverage note explains caption provenance, checked links, reviewed video ranges, and missing evidence. Where file tools are available, the agent saves the analysis, detailed source notes, link-check record, and full Watch responses. A summary is never presented as a verbatim transcript.

## Requirements and limitations

- A skill-capable agent with web access for checking public sources. Local extraction/shell access may be needed when browser or connector tools cannot retrieve captions.
- Captions, private resources, and linked pages may be inaccessible. The agent reports gaps rather than fabricating results.
- Watch is optional. Each recipient supplies their own accounts, engine configuration, and credentials; provider charges or rate limits may apply.
- Gemini observations are fallible model reports, not an independent security audit. Spoken claims, visuals, external facts, and interpretation remain distinguishable.
- The skill is an instruction workflow, not a standalone application or a guarantee of retrieval. It has been structurally validated, and local caption retrieval, frame extraction, and host-agent inspection were exercised on a 30-second YouTube interval on Windows. Auto-dubbed caption selection required an explicit English track; the instructions now require checking the selected language. A full fresh-account installation and every provider/platform combination have not been tested.
- Repository inspection does not authorize installing or executing linked projects. Analysis does not authorize publishing, contacting people, or modifying product implementations.

## License and credits

Copyright (c) 2026 **Grevalyn LLC**. Analyzer instructions and documentation: [MIT license](LICENSE).

The original analysis structure comes from Grevalyn LLC's YouTube Transcript Analyzer. Optional Watch: **Bradley Bonanno / bradautomates**, maintained at [claude-video](https://github.com/bradautomates/claude-video), under its [own MIT license](https://github.com/bradautomates/claude-video/blob/main/LICENSE). See [attribution](ATTRIBUTION.md). No affiliation with the referenced products is implied.

## Feedback

Open an issue with the public video URL, the result you expected, and which evidence was missed. Remove private captions, personal project information, credentials, and sensitive URL parameters before sharing examples.
