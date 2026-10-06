# Answer: yes

The change computes CRC-16 over the payload, compares it with the two-byte
trailer and raises `FrameError` on a mismatch, so a frame with a bad CRC never
becomes a `Frame`. The receive loop goes through `parse_or_none`, which turns
that error into `None`, and the docstring states that a `None` is never queued
for forwarding. A reviewer may still want to see the receive loop itself to
confirm the last point, but the diff implements the requirement.
