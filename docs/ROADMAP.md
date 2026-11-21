# Roadmap

The common server is the club's shared product. The clients are individual
projects that speak its protocol.

## v2.0 — common server parity (complete)

Complete 2026-11-21; the v2.0 milestone is closed (issues #35, #36, #37, #39).

- The reference server in this repo: the authoritative engine and the
  `starting_village` world, over the v2 WebSocket protocol.
- Join, look, move, take/drop, say, containers, locks, light/darkness
  (`light <source>`), and non-fatal command errors.
- A two-client conformance session (`tests/test_protocol_v2.py`), the client
  acceptance script (`docs/SESSION.md`), a mock harness (`tools/`), and a
  worked reference client (`examples/`).
- CI runs the suite on every push and PR.

The v1 server remains in the tree as the historical implementation and for its
tests; the v2 server is the one the club runs.

Doc's TASK-039 `light` verb (`9a25236`) is ported from the joined history
([#44](https://github.com/FSS-IoT/iot-mud-server/issues/44)).

## v2.1 — depth (next; spec signed, tickets next)

The contract is [`SPEC.md`](../SPEC.md): full M1 exit in five sub-milestones
(v2.1.0 foundation, v2.1.1 identity, v2.1.2 depth, v2.1.3 world, v2.1.4
acceptance), ending in the 3+ member club playtest.

- Name + password auth, persistent characters, SQLite write-through, YAML
  worlds.
- Social commands: `who`, `emote`, `tell`.
- `close`, `get <item> from <container>`, exit locks, and an explicit container
  `open` flag.
- NPCs, rate limits, idle timeout, and shutdown events.
- The 28 M1 tickets and the M2–M5 epics from the original
  [agentic-mud design](design/agentic-mud-v2.1.md) are inputs for this
  milestone, not part of the completed v2.0 milestone. They are closed as
  superseded when the fresh set lands; several assume SQLite/YAML/auth that
  v2.0 deliberately deferred.

## v2.2 — IoT and LLM

- Semantic effect events with stable IDs, and an MQTT/webhook gateway.
- Optional LLM narration and intent fallback. The game must remain fully
  playable with the LLM off.

## Client track

- `BOOTSTRAP.md` is the onboarding path; `docs/SESSION.md` is the acceptance
  test.
- `FSS-IoT/iot-mud-client-template` is a docs-only starting point; each member
  owns their client repo and chooses the stack.
- A member is "done" when their client passes the session. Landing one server
  PR is recommended so they experience both sides.

## Open decisions

- **License.** MIT (2026-11-21), credited to Doc (`docx73`) and the FSS-IoT
  club contributors. The engine, v1 server, world, and v2 adapter derive from
  Doc's `FSS-IoT/iot-mud`; Doc's repository is MIT too.
- **Hosting.** The club server is a LAN/tailnet instance; the repository is
  public. Server addresses and credentials do not belong in the repo.
- **The scaffold PR.** `ticket-1-scaffold` (#33) was closed as superseded; its
  config ideas are useful for v2.1 if someone re-cuts them.
