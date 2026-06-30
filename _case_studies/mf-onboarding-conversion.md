---
layout: case_study
title: "MF Onboarding Conversion: 12% → 22%"
subtitle: "Rebuilding a KYC, nominee & bank-verification funnel"
category: fintech
category_label: "Regulated fintech, built 0-to-1"
order: 2
summary: "Tore apart a multi-provider mutual-fund onboarding funnel and nearly doubled completion, from 12% to 22%."
meta: "smallcase · Product Manager (Pod Lead), Mutual Funds · 2024–2025"
---

> **TL;DR** — I rebuilt the mutual-fund onboarding funnel — KYC, nominee, and bank verification — and **nearly doubled completion from 12% to 22%**, while also driving a 5% activation uplift by going after a user segment everyone else had written off.

## Context

A new investor on smallcase has to clear a gauntlet before their first rupee is invested: KYC, nominee registration, and bank verification — each gated by an external provider with its own failure modes. Only **12%** of users who started actually finished. For a regulated platform, you can't remove these steps; you can only make them not hurt.

## Problem

- The funnel was a sequence of third-party black boxes (KYC, penny-drop bank checks, nominee capture). When one failed, the user just... left.
- A meaningful slice of new users (**~25%, the non-demat segment**) was effectively unserved — the flows implicitly assumed an existing demat/investing setup.
- No clear instrumentation of *where* in the multi-provider chain users were dropping.

## What I did

- **Instrumented the funnel step-by-step** to find the real drop-off points rather than guessing, then attacked them in priority order.
- **Re-architected verification across providers** — integrating and orchestrating **Signzy, Juspay, MFCentral, NDML, and Setu** — so each step had the most reliable path and graceful fallbacks instead of dead ends.
- **Optimized KYC, nominee, and bank-verification UX** — reducing fields, fixing failure messaging, and removing steps that didn't need to block first investment.
- **Targeted the non-demat segment (~25% of new users)** explicitly, designing flows for users without an existing investing setup and leading GTM across Marketing, CX, Ops, and Partnerships to convert them.

## Impact

| Metric | Before | After |
|---|---|---|
| Onboarding conversion | 12% | **22%** |
| First-purchase / activation | — | **+5% uplift** |
| Addressable segment | demat-first | **non-demat (~25%) included** |

## What I learned

- When your funnel is a chain of third-party services, **your real product surface is the orchestration and the failure states** — not the happy path. Most of the 10 points came from handling failure better, not from a prettier UI.
- "These users won't convert" is often "we never designed for them." The non-demat segment was a growth lever hiding behind an assumption.
- Instrumentation first, opinions second. The biggest leak wasn't where the team assumed it was.
