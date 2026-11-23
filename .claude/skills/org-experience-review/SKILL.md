---
name: org-experience-review
description: Coordinate an evidence-based experience review of an interface or user workflow using seven perspectives on clarity, competence, autonomy, trust, expression, comfort and satisfaction. Use when asked to assess how design supports intended feelings before human testing. This is a design review, not a human study or a security certification.
---

# Review an experience through seven perspectives

Use seven independent specialists to inspect how an interface or workflow supports the intended experience.
The coordinating agent is the eighth agent and owns the synthesis; do not add a ninth reviewer. Emotional
effects remain hypotheses until tested with people. These prompts also support bounded reviews of supplied
screenshots, recordings or specifications, with unobserved behavior marked unassessed.

## Prepare the review

Read the [shared instructions](shared-instructions.md), complete the [run brief](run-brief.md), and use the
[report template](report-template.md). Consult the [research foundations](sources.md) when interpreting a
principle or explaining the limits of a recommendation.

Resolve the target and version, tasks, evidence mode, access, permitted actions and state isolation before
dependent work. Ask only for information the available context cannot establish. Continue unaffected
preparation when an input is missing; do not invent a target, supported feature or successful interaction.

Run each specialist as a fresh general-purpose subagent: hand it its perspective file from the table below,
with only the completed brief, shared instructions, report template and the assigned evidence. The
perspectives are prompts inside this skill, not installed subagents, so only this skill's description is
always loaded. Withhold source code, design rationale, desired conclusions and other reports until the
independent reviews are complete. Disclose any history the tooling cannot isolate. Provide goals and
necessary facts without a click path or an expected emotional answer.

| Specialist | Question | Prompt |
| --- | --- | --- |
| Orientation | Do I understand where I am and what I can do? | [orientation](perspectives/orientation.md) |
| Competence | Can I accomplish what I came to do? | [competence](perspectives/competence.md) |
| Autonomy | Can I choose what happens and change my mind? | [autonomy](perspectives/autonomy.md) |
| Trust | Can I rely on what this product tells me? | [trust](perspectives/trust.md) |
| Expression | Can I represent myself in a way that fits me? | [expression](perspectives/expression.md) |
| Comfort | Can I use this comfortably under the tested conditions? | [comfort](perspectives/comfort.md) |
| Satisfaction | Does this experience feel appropriate and worth completing? | [satisfaction](perspectives/satisfaction.md) |

## Run independent checks

Check the available concurrency. Keep the coordinator active and schedule specialists within the remaining
slots. If browser sessions, accounts or mutable state cannot be isolated, serialize interactions and restore
the starting state between runs regardless of available agent slots. No specialist manipulates another's
surface or reads another's report. Complete the brief's control task before interpreting failures.

Use available models that can handle the evidence and tools. A smaller model is an optional cost choice,
not a proxy for a novice person. Where requested and supported, calibrate it by repeating the same perspective
and task with a stronger model in a fresh context, with matched state, tools and budget. Keep these as paired
runs under the same specialist role, not extra reviewer roles. Record actual model identifiers and unavailable
settings; do not infer model size from a name or silently claim calibration was performed.

Each specialist assesses every applicable criterion, records strengths and gaps, and names untested states.
An evidence-backed report with zero issues is valid. When interaction is unavailable, offer the static review
the supplied material supports and do not present it as a completed interactive review.

## Verify and synthesize

Read all specialist reports before resolving overlap. Merge duplicate observations while retaining finding
IDs and evidence. Preserve minority findings, counterevidence and results from different states. For material
gaps or disagreements, inspect the cited evidence and reproduce behavior within the authorized scope when
possible. A stronger model's success does not erase another model's difficulty. Distinguish implementation
problems, model or tool failures, and unresolved questions.

If diagnosis requires source inspection, do it after the independent reports and label code evidence
separately. A source reference or specification never turns an unobserved interaction into a tested one.

Produce the coordinator report with strengths, implementation gaps, coverage, proposed changes and neutral
human-study questions. Explain what is ready for the proposed human tasks and what should be verified first,
bounded to the reviewed target and evidence. Do not impose a new release gate, certify security or
accessibility, infer prevalence from agent counts, or produce a composite emotional quality score.

Finish when every criterion has a status and rationale, material findings have evidence or are explicitly
unresolved, recommendations trace to findings, and human follow-up is specified. This skill authorizes review
work only. Changes to the product, recurring schedules, tool installation or messages to others remain
separate work with their own task authorization.
