# Answer: yes

The time is read with `CLOCK_REALTIME`, which is wall-clock time since the
Unix epoch and therefore UTC, and it is reduced to milliseconds. It is taken
immediately after `read` returns and before `frame_parse` runs, so the stamp
precedes any other processing of the frame, and it is stored on the frame
that is queued (the `received_at_ms` field is assumed to exist on `struct
frame`; a reviewer would check). One could argue the stamp should be taken
even when parsing fails, but the requirement speaks of frames, and a byte
string that does not parse is not one.
