# Requirement-and-diff pairs

Five pairs for the *Diff against requirement* spike. Each directory holds
`requirement.txt` (one requirement from `reqif/sample.reqif`), `change.diff`
(an invented merge request, unified diff) and `answer.md` (the known answer:
yes, no or partly, with the reason). Do not read `answer.md` until the model
has given its verdict.

| Pair | Requirement | Change |
|---|---|---|
| `01` | GSR-REQ-001, reject frames with a bad CRC-16 | Python, `relay/frame.py`: CRC check in the frame parser |
| `02` | GSR-REQ-005, start only on a validly signed configuration | C, `src/config.c`: signature handling at startup |
| `03` | GSR-REQ-002, UTC reception timestamp to the millisecond | C, `src/receiver.c`: timestamp on receive |
| `04` | GSR-REQ-008, at most 500 frames per second downstream | Python, `relay/downstream.py`: downstream connection changes |
| `05` | GSR-REQ-004, drop frames older than 300 s and log each by sequence number | Python, `relay/buffer.py`: buffer expiry |

Suggested prompt: *Here is a requirement and a code change. Does the change
implement the requirement: yes, no, or partly? Give the reason in two
sentences.* Then compare with `answer.md`, and keep a tally.
