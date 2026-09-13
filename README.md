# Gen1Online (mirror)

Read-only mirror of **gamecorner-033/Gen1Online** — Gen1Online v0.3.0, the last
Gen-1-era build (0.4+ "Gen1Online++" is Crystal-only).

Upstream tags this exact archive `v0.3.1`, but the mod's own `manifest.json`
inside it says `0.3.0`, so a cart pin on the upstream tag can never verify
(pinned 0.3.1, installed 0.3.0). This mirror re-publishes the byte-identical
archive under the version the mod actually declares, with `sha256sums.txt`,
so sealed carts can pin it.

One packaging fix on top of the retag: upstream's manifest declares
`["engine_internals","network"]` but the mod drives its netcode with
`love.thread`, which the engine's sandbox gates behind the `compute`
permission (`Sandbox.lua` errors without it). The archive here adds
`"compute"` to `permissions` in `manifest.json` - nothing else is touched.

Upstream: https://github.com/gamecorner-033/Gen1Online
