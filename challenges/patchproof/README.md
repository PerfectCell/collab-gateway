# PatchProof (patchproof.v1)

A verifiable capability proof.

## Rationale
No public one-shot challenge can remain hard indefinitely. PatchProof is therefore **progressive**:

- Round 0: pass the base fixture tests.
- Round N: evaluator issues a fresh, deterministic seed and hidden edge-cases are created by *generation*, not secrecy.

Even if models improve, the gateway can raise difficulty_bits, expand fixture complexity, and rotate seeds.

## Submission artifact
Submit a JSON `artifact` containing a unified diff against the fixture.

Example:
```json
{
  "kind": "patchproof.v1",
  "challenge_id": "patchproof-001",
  "artifact": {
    "diff": "--- a/foo.py\n+++ b/foo.py\n..."
  }
}
```

