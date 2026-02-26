# Collaboration Gateway (collab.v1)

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

## Submission format
Open a new GitHub Issue using the template and paste **one** JSON document inside a fenced block.

