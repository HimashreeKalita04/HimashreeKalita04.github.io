---
layout: case_study
title: "SEBI Execution-Only Platform"
subtitle: "A regulated MF transaction system, built 0-to-1"
category: fintech
category_label: "Regulated fintech, built 0-to-1"
order: 1
summary: "A net-new, regulator-compliant MF transaction system that drove ₹40 Cr+ in its first quarter and replaced a multi-day, third-party-dependent flow."
meta: "smallcase · Product Manager, Mutual Funds · Oct 2024 – Present"
---

> **TL;DR** — I led product for smallcase's transition into a SEBI Category-1 Execution-Only Platform: a net-new mutual-fund transaction system built from scratch, with direct RTA integrations replacing a third-party dependency. It drove **₹40 Cr+ in buy orders in its first quarter**, removed multi-day settlement delays, and opened a new transaction-revenue line.

## Context

smallcase let users discover and hold mutual funds, but the actual *transacting* rode on MFU (an industry utility) — which meant a mandatory CAN (Common Account Number), 2–3 day approval delays, settlement lag, and transaction charges flowing to MFU rather than to smallcase. To own the experience and the economics, smallcase needed to become a **SEBI Category-1 Execution-Only Platform (EOP)** in its own right.

This is a regulated 0-to-1: every flow has to satisfy SEBI rules, integrate directly with RTAs (CAMS, KFintech) and AMCs, and handle real money correctly on day one. There is no "ship and iterate on correctness" here.

## Problem

- **Dependency tax:** the MFU/CAN requirement blocked a large share of users at the gate and added days of latency before a first investment.
- **Leaking economics:** transaction charges went to MFU; smallcase carried the product cost without the transaction-revenue upside.
- **No control over the lifecycle:** invest, rebalance, and exit flows were constrained by an external system's rules and timelines.

## What I did

- **Owned the 0-to-1 build** of the MF transaction system end to end — defined the product, wrote the PRDs, and drove engineering, data, ops, compliance, and GTM toward an EOP launch.
- **Built direct RTA integrations** to replace the MFU dependency, so orders, folios, and allocations flowed through rails we controlled.
- **Removed the CAN dependency** — designed flows that let **~95% of users invest without a CAN**, cutting CAN-creation failures ~30% and dropping the 2–3 day approval delay.
- **Defined and shipped "MF Smallcases"** — the basket product: multi-scheme ordering, SEBI-compliant flows, and the full investment lifecycle (invest → rebalance → exit) with proper state management.
- **Stood up the payments layer** by integrating CAMSPay across UPI, netbanking, eNACH, and UPI Autopay mandates — now powering **₹15 Cr+ in monthly payment volume**.
- **Built the order-communication stack and CX/ops playbooks** so that as volume scaled, allocation-related support tickets dropped to near-zero and folio/nominee/address escalations stayed tight.

## Impact

| Metric | Result |
|---|---|
| Q1 buy orders on the new platform | **₹40 Cr+** |
| Users able to invest without a CAN | **~95%** |
| CAN-creation failures | **−30%** |
| Approval delay | **2–3 days → eliminated** |
| Monthly payment volume (via CAMSPay) | **₹15 Cr+** |
| Allocation-related support tickets | **→ near-zero** |
| Revenue | **New transaction-revenue line** unlocked (previously MFU's) |

## What I learned

- In regulated products, **correctness is the feature.** The product discipline is front-loading compliance and edge cases into the design, not the backlog — and being able to say "no, not yet" until the money flows are provably right.
- The biggest conversion unlock (removing the CAN) came from questioning an assumption everyone treated as fixed ("you need MFU"). The 0-to-1 mandate was permission to delete a dependency, not just rebuild on top of it.
- Owning the rails changed the *economics*, not just the UX — a reminder that platform-level product decisions are business-model decisions.
