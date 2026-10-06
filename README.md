# Spiking Lab sample material

Small, invented material for the hands-on block of the Spiking Lab: a
20-minute spike per participant or pair, on a laptop or in a browser, with
nothing from the hackathon environment needed. The subject throughout is a
made-up **ground-station telemetry relay** (GSR): a service that receives
telemetry frames, checks them, buffers them and forwards them downstream.

**Everything here is invented and unclassified. Nothing comes from Saab.**

## What is here

| Path | What | Spike it serves |
|---|---|---|
| `reqif/sample.reqif` | One ReqIF 1.2 file with eight requirements, GSR-REQ-001 to GSR-REQ-008 | Read a ReqIF export |
| `pairs/01` … `pairs/05` | A requirement, a unified diff, and the known answer | Diff against requirement |
| `links/trace-links.json` | Requirement-to-test links, with gaps and one failure | Matrix from a graph |

## The three spikes

**Read a ReqIF export.** Can you parse `reqif/sample.reqif` and print its
requirements with their identifiers in under twenty lines? ReqIF is XML; the
requirements are `SPEC-OBJECT` elements, each with two string attribute
values, the identifier and the text. Any language.

**Diff against requirement.** Give a chat model `requirement.txt` and
`change.diff` from one pair and ask: does this change implement the
requirement, and why? Then open `answer.md`. Do all five; count how often the
model is right, and note where it is confidently wrong. The pairs are listed
in `pairs/README.md` without their answers.

**Matrix from a graph.** Render `links/trace-links.json` as a traceability
matrix in HTML, requirements down the side, tests across the top. Two
requirements have no test at all; one test covers two requirements; one link
is a failed test. A matrix that does not make the gaps visible has not
answered the question.

## Rules of the lab, in short

State the question in one sentence first. Twenty minutes, crudest possible
means. Keep the write-up, throw the code away.

## Licence

CC0 1.0. Copy, change and reuse freely; see `LICENSE`.
