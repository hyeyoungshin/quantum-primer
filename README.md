# quantum-primer — GitHub Project Roadmap

**Project Title**: quantum-primer — Quantum compiler test engineer onboarding

**Repository**: `hyeyoungshin/quantum-primer`

**Date**: 2026-07-14

---

## Summary

A structured onboarding project for starting work as a quantum compiler test engineer, derived from the two-week study plan in `contents/quantinuum_onboarding.html`.  Six milestones: environment setup and compiler-lens orientation (M1), quantum computing foundations (M2), the Quantinuum compiler stack — pytket, HUGR, TKET2, Guppy, H-series hardware (M3), quantum compiler testing methods (M4), the five required papers (M5), and a capstone test suite with an end-to-end pipeline walkthrough (M6).

---

## Description

The source curriculum (`contents/quantinuum_onboarding.html`) is a 14-day study plan written for an engineer with a solid programming-languages and compiler-verification background but little or no quantum physics.  The goal is not to become a quantum physicist: it is to acquire exactly enough quantum knowledge to reason about *what a quantum compiler must preserve*, and then to build working familiarity with the full Quantinuum compiler stack and the testing methods that apply to it.

This project turns that curriculum into trackable GitHub issues.  Each study day maps to one or more issues; the five required papers form their own reading track (M5) that interleaves with the daily work.  Nearly every issue produces a concrete artifact committed to this repository, under one of three directories established in M1:

+ `notes/` — one markdown note per study day or paper, including answers to each day's "key question";
+ `exercises/` — small runnable Python programs (Bell state, pass comparison, Guppy programs, end-to-end pipeline);
+ `tests/` — the growing pytest + Hypothesis test suite, run by GitHub Actions CI on every push.

The CI workflow (M1-3) is itself part of the learning: a compiler test engineer's deliverable is an automated test suite, so this project treats "my exercises run green in CI" as the standing definition of done.  The capstone (M6) grows the suite into the five standard categories for quantum compiler testing — structural, predicate, equivalence, metric, and regression tests — and adds a scheduled deep property-testing run.

**The Quantinuum stack (orientation)**.  Guppy (Python-embedded DSL for hybrid quantum-classical programs) compiles to HUGR (the shared IR — "LLVM IR for quantum"), which is optimized and lowered by TKET2 (Rust); the mature pytket (TKET) toolchain remains the production circuit-level compiler; everything targets H-series trapped-ion hardware (H1, H2, Helios).

### Day-to-issue map

| Day | Focus | Issues |
|-----|-------|--------|
| 1 | Compiler review through a quantum lens | M1-4 (M1-1, M1-2, M1-3 alongside); start M5-1 |
| 2 | Quantum computing — the minimum you need | M2-1 |
| 3 | Circuit model and what compilation does | M2-2, M2-3 |
| 4 | TKET (pytket) | M3-1; finish M5-1 |
| 5 | HUGR | M3-2, M5-2 |
| 6 | TKET2 | M3-3 |
| 7 | Guppy | M3-4; start M5-3 |
| 8 | H-series hardware | M3-5 |
| 9 | Testing methods and strategy | M4-1, M5-4, M5-5 |
| 10 | Circuit equivalence and formal verification | M4-2, M4-3 |
| 11 | Building a test suite | M6-1 |
| 12 | Papers day — deep reading | finish M5-3, M5-5; M5-6 |
| 13 | End-to-end: Guppy → HUGR → hardware | M6-2 |
| 14 | Review, gaps, integration | M6-3 |
