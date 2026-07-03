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

> **TL;DR** — I rebuilt smallcase's mutual-fund onboarding funnel — KYC, nominee, and bank verification — and **nearly doubled completion from 12% to 22%**. Separately, I found that a large slice of users were dropping *before* MF onboarding because they assumed it required a demat account — and unlocked them with a **+5% first-purchase/activation** uplift.

## Context

Before a user can make their first mutual-fund investment on smallcase, they have to clear a dedicated MF onboarding flow — KYC, nominee registration, and bank verification — each gated by an external provider with its own failure modes. (This is separate from smallcase's general onboarding for its equity/demat products.) Only **12%** of users who started this MF flow actually finished. For a regulated platform, you can't remove these steps; you can only make them not hurt.

## Problem

- The funnel was a sequence of third-party black boxes (KYC, penny-drop bank checks, nominee capture). When one failed, the user just... left.
- No clear instrumentation of *where* in the multi-provider chain users were dropping.
- Separately, a meaningful slice of new users (**~25%, non-demat users**) hesitated at MF onboarding because they assumed it required opening a demat account — so they never engaged with the MF flow at all.

## What I did

- **Instrumented the funnel step-by-step** to find the real drop-off points rather than guessing, then attacked them in priority order.
- **Re-architected verification across providers** — integrating and orchestrating **Signzy, Juspay, MFCentral, NDML, and Setu** — so each step had the most reliable path and graceful fallbacks instead of dead ends.
- **Optimized KYC, nominee, and bank-verification UX** — reducing fields, fixing failure messaging, and removing steps that didn't need to block first investment. *(This is what drove 12% → 22%.)*
- **Unlocked the non-demat segment (~25% of new users)** — identified that these users were hesitating because MF onboarding felt tied to a demat account, then **integrated MF onboarding with smallcase's general onboarding** so they could complete it *without* a demat account. Led GTM across Marketing, CX, Ops, and Partnerships to bring them through. *(This drove the +5% activation uplift.)*

## Impact

| Metric | Result |
|---|---|
| MF onboarding conversion | **12% → 22%** |
| First-purchase / activation (from unlocking non-demat users) | **+5%** |

## What I learned

- When your funnel is a chain of third-party services, **your real product surface is the orchestration and the failure states** — not the happy path. Most of the 10-point lift came from handling failure better, not from a prettier UI.
- **The biggest unlock sat upstream of the funnel I was asked to fix.** The non-demat win came not from the MF flow itself but from removing a *perceived* prerequisite — a demat account — by wiring MF onboarding into the general onboarding path.
- "These users won't convert" is often "we never designed for them." An entire ~25% segment was bouncing on an assumption no one had questioned.
