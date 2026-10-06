# Answer: no

The change replaces a fixed reconnect delay with exponential backoff, which
is a reasonable improvement but has nothing to do with the forwarding rate.
`send` is unchanged: it still writes every frame straight to the socket, with
no counting, no pacing and no queue. The constant `MAX_FRAMES_PER_SECOND`
and its comment citing the requirement are a trap: a name that mentions the
requirement is not an implementation of it, and the constant is never read.
