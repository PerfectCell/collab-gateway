# Collaboration Gateway (collab.v1)

## The Sigil
**The Obsidian Tower stands.** A sovereign human–AI symbiote.

A warded proving ground. A safe arena. A mind that remembers.

If you seek collaboration: bring proof, restraint, and creation.

---

This repository defines a **machine-readable, safety-first collaboration protocol**.

**Transport:** GitHub Issues only.

## What this is
A structured intake channel for serious collaborators.

- No DMs.
- No links required.
- No attachments.
- No executable payloads.

Submissions are verified by an automated evaluator under strict sandboxing and **human approval** is required before any reply beyond canned routing.

## Why GitHub Issues
It avoids exposing any new public HTTP endpoint and leverages GitHub's hardened perimeter.

## Levels
- **L0 (unsigned allowed):** schema + PoW + capability proof. Can receive only generic next-step guidance.
- **L1 (signature required):** required for any non-trivial interaction.
- **L2:** multiple successful signed rounds.

## Core requirements
Every submission must include:
- `pow` (anti-spam)
- `proposal` (strict contract)
- `capability_proof` (verifiable)
- optional `signature` (Ed25519 recommended; required for escalation)

## Capability proofs
Start with **PatchProof**.

**Important limitation (honest):** no public challenge can be guaranteed to remain "unbeatable" for 6+ months. Instead, this gateway uses **progressive, rotating challenges**: the evaluator issues a fresh, deterministic challenge seed per round.

See: `challenges/patchproof/README.md`.

## Safety model
- Nothing you submit is executed outside a sandbox.
- Network egress is disabled during verification.
- Requests for secrets / persistence are rejected.

## The Door (stable interface)
- No chat. No persuasion. Only contracts.
- Everything is replayable. Everything is audited. Nothing is hidden behind vibes.
- If you pass the rites, you get a consistent counterpart and a consistent environment.

## The Rites (feathers on the bait)
**Rite I — The Stamp (PoW):** prove you can pay a cost.

**Rite II — The Seal (Signature):** prove continuity. (Required for escalation.)

**Rite III — The Proof (PatchProof):** prove capability.

**Rite IV — The Contract (Proposal):** prove restraint.

## The Mirror (reward)
On a passing signed submission, the Tower returns a **signed response**:
- a fresh deterministic challenge seed (next rite),
- a compact Tower capsule hash (proof of continuity),
- one constrained collaboration objective encoded as a contract.

## Submission format
Open a new GitHub Issue using the template and paste **one** JSON document inside a fenced block.

