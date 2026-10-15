# Decisions, Provenance, and Open Items

## Preservation rules

- The v7 architecture graph, invariant hierarchy, ownership model, stream epoch/frame-sequence/parser phase model, calibration boundary, window semantics, energy commit semantics, and fault-recovery path are recorded as frozen.
- New research should be additive. Preserve existing files, decision history, evidence, and provenance.
- Do not renumber existing requirements, decisions, or checkpoints without an explicit migration record.
- Keep verified facts separate from remembered design values, assumptions, plans, and unverified claims.
- Do not describe VoltaEdge as a certified protection device or utility-meter replacement.

## Context recovered for this import

The currently preserved context includes:
- project purpose and product boundary;
- acquisition platform and sampling/framing/timing values;
- analog front-end assumptions and procurement notes;
- ESP-IDF environment-level verification (CP-000);
- a list of frozen v7 contracts.

## Open items requiring source recovery or engineering evidence

1. Locate the original full v7 specification and compare this import line by line.
2. Recover the exact architecture graph and invariant hierarchy, including identifiers and precedence.
3. Recover the detailed ownership and concurrency contract.
4. Recover exact stream epoch, frame sequence, and parser phase transitions.
5. Recover calibration equations, coefficients, validity checks, and delay-compensation procedure.
6. Recover window boundaries, partial-window handling, and energy commit/rollback rules.
7. Recover the fault table, recovery ordering, retry limits, and safe failure state.
8. Verify current BOM, supplier evidence, and safety ratings.
9. Build the actual VoltaEdge firmware and record the exact command/output.
10. Perform bench validation with a reference measurement setup before making accuracy claims.
11. Record physical hardware and mains-safety review separately from software tests.

## Source-of-truth rule

This import is a recovered context summary. When it conflicts with an existing canonical v7 file or a newer signed-off decision, stop and reconcile the discrepancy explicitly; do not silently overwrite either source.
