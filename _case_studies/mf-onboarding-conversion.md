---
layout: case_study
title: "MF Onboarding Conversion: 12% → 22%"
subtitle: "Rebuilding a KYC, nominee & bank-verification funnel"
category: fintech
category_label: "Regulated fintech, built 0-to-1"
order: 2
summary: "Tore apart a multi-provider mutual-fund onboarding funnel and nearly doubled completion, from 12% to 22%."
meta: "smallcase · Product Manager, Mutual Funds · 2024–2025"
---

> **TL;DR** — I rebuilt smallcase's mutual-fund onboarding funnel — KYC, nominee, and bank verification — and **nearly doubled completion from 12% to 22%** through step-by-step instrumentation and iterative fixes across a chain of third-party providers.

## Context

Before a user can make their first mutual-fund investment on smallcase, they have to clear a dedicated MF onboarding flow — KYC, nominee registration, and bank verification — each gated by an external provider with its own failure modes. (This is separate from smallcase's general onboarding for its equity/demat products.) Only **12%** of users who started this MF flow actually finished. For a regulated platform, you can't remove these steps; you can only make them not hurt.

## Problem

- The funnel was a sequence of third-party black boxes (KYC, penny-drop bank checks, nominee capture). When one failed, the user just... left.
- No clear instrumentation of *where* in the multi-provider chain users were dropping.
- Every step was treated as equally mandatory, even ones that didn't need to block a first investment.

## What I did

- **Instrumented the funnel step-by-step** to find the real drop-off points rather than guessing, then attacked them in priority order.
- **Re-architected verification across providers** — integrating and orchestrating **Signzy, Juspay, MFCentral, NDML, and Setu** — so each step had the most reliable path and graceful fallbacks instead of dead ends.
- **Optimized KYC, nominee, and bank-verification UX** — reducing fields, fixing failure messaging, and removing steps that didn't need to block first investment.
- **Iterated release by release**, re-checking the funnel after each change so improvements compounded rather than shifting the drop-off elsewhere.

## Impact

| Metric | Result |
|---|---|
| MF onboarding conversion | **12% → 22%** |

## What I learned

- When your funnel is a chain of third-party services, **your real product surface is the orchestration and the failure states** — not the happy path. Most of the 10-point lift came from handling failure better, not from a prettier UI.
- **Instrument before you optimize.** The largest drop-offs weren't where the team assumed they were — only step-level data made the priority order obvious.
- In regulated flows you can't delete steps, so the craft is in making mandatory steps *survivable* — fewer fields, better fallbacks, clearer recovery.
