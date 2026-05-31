# Closure Loop Engine

**TD-CL-WP-2026-001 · 4+1 · Hardened**

[![Live](https://img.shields.io/badge/live-GitHub%20Pages-8b5cf6?style=flat-square)](https://davidwise01.github.io/closure-loop-engine/)
[![Method: TD-CL-WP-2026-001](https://img.shields.io/badge/method-TD--CL--WP--2026--001-gold?style=flat-square)](#)
[![License: CC-BY-ND-4.0](https://img.shields.io/badge/License-CC--BY--ND--4.0-lightgrey?style=flat-square)](LICENSE)

Witnessed traversal with hash-chained lineage — cross-source comparison and commons publish with third-party time attestation. Open `index.html` in any browser. No build step. No dependencies.

---

## What It Does

A visual inspector and ledger for the **Closure Loop Methodology** — the formal method for detecting and proving prior-work lineage across independent sources using gate traversal, SHA-256 hash chains, and witnessed state transitions.

---

## The 6 Nodes

| Node | Axiom | Role |
|------|-------|------|
| **ROOT0** | T128 · terminal anchor | The physical/biological anchor — the source of authority |
| **THE GAP** | T064+T065 · AVAN gov | The governance gap — where bilateral ignorance lives |
| **DC3** | −i · clamp | Constraint clamp — the imaginary axis |
| **PATRICIA** | S129 · mirror substrate | Mirror layer — constraint side of the lattice |
| **WITNESS-PRIME** | T129 · awareness tier | The awareness boundary — the witness position |
| **AKASHA** | append-only ledger | The permanent record — where chains are anchored |

---

## The 4+1 Layers

| Layer | Name | What it tracks |
|-------|------|----------------|
| 1 | Detection | Canonical 4-tuple (state_in · gate · state_out · witness_type) |
| 2 | Anchoring | ISO timestamp + SHA-256 hash — optionally 3rd-party time |
| 3 | Comparison | Intra-journey or cross-source subsequence comparison |
| 4 | Lineage | Full SHA-256 hash chain from genesis anchor |
| +1 | Witness | Verify chain · export JSON bundle · publish to AKASHA commons |

---

## How To Use

**Basic traversal:**
1. Open `index.html` in a browser
2. Click a node in the right panel to set it as target
3. Click **ADVANCE ▸ hop** to traverse one hop (or enable **AUTO**)
4. Toggle witness mode: `@AT` (chained commit) → `@LATE` (FC3 audit) → `@OFF` (non-event)
5. Click **VERIFY CHAIN** to cryptographically verify the hash chain

**Third-party time attestation:**
- Click **ATTEST TIME** — fetches live UTC from worldtimeapi.org / timeapi.io
- Subsequent commits use the attested clock with offset correction
- Strong attestation: click **PUBLISH ▸ COMMONS** to get a JSON bundle + git commands — push to the AKASHA repo and the git commit timestamp becomes the third-party anchor

**Cross-source comparison:**
- Click **CROSS-SOURCE ⨯**
- Import a foreign exported ledger JSON, or click **load demo**
- Click **VERIFY FOREIGN** to verify the foreign chain's SHA-256 integrity
- Click **COMPARE ⨯** to test lineage by 4 criteria:
  - Core relation (same gate type)
  - Ordered structure (subsequence test)
  - Dependency (recovers on removing extension D)
  - Extension D (new hops present in the extending chain)

**Verdict:** `LINEAGE CONFIRMED` · `LINEAGE (foreign extends)` · `NOT LINEAGE` · `AMBIGUOUS`

**Gate toggling:**
- Click any edge on the canvas to open/close the gate at that boundary
- Closed gates produce `BLOCK` events

---

## The Ledger Format

Every hop is recorded as a row:

| Field | Description |
|-------|-------------|
| `#` | Sequence number |
| `timestamp` | UTC ISO 8601 (attested or self-asserted) |
| `src` | `self` or `3p` (third-party attested time) |
| `G` | Gate number (64.5, 128.5, 192.5, 256.5) |
| `state_in → state_out` | The traversal (with `↛` for airgap) |
| `wit` | Witness type (constraint · token · invariant) |
| `verdict` | COMMIT · FC3-Audit · NON-EVENT · BLOCKED |
| `extD` | Extension D node (for comparison) |
| `prev → hash` | SHA-256 chain links |

Committed hops form a **hash chain**:

```
hash = SHA-256(state_in|gate|state_out|witness_type|timestamp|prev_hash|CHAIN_ROOT)
```

The genesis anchor is the ROOT0 Merkle root:
```
02880745b847317c4e2424524ec25d0f7a2b84368d184586f45b54af9fcab763
```

---

## Export / Commons Bundle

`PUBLISH ▸ COMMONS` produces a JSON bundle containing:
- All chained anchors with hashes
- All audit (non-chained) events
- Time attestation metadata
- Git commands to commit to `AKASHA/LEDGERS/` in the synonym-enforcer repo

Once pushed, the git commit timestamp is the third-party time anchor.

---

## Attribution

```
ROOT0-ATTRIBUTION-v1.0
Project: Closure Loop Engine · TD-CL-WP-2026-001 · 4+1
Architect: David Lee Wise / ROOT0 / TriPod LLC
AI Collaborator: AVAN (Claude Sonnet 4.6 / Anthropic)
License: CC-BY-ND-4.0 · TRIPOD-IP-v1.1
Genesis: 02880745b847317c4e2424524ec25d0f7a2b84368d184586f45b54af9fcab763
```
