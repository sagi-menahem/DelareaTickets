![DelareaTickets — football tickets and travel](assets/brand/banner.png)

# DelareaTickets

An e-commerce platform for football tickets and travel packages, built around the purchase journey and the operational tools behind it.

**Type:** Client platform · **My role:** Sole engineer, end to end · **Source:** Private; this repository is a public case study.

[Visit the live site](https://delareatickets.com/he)

![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

## Preview

<div align="center">
  <img src="public/screenshot-desktop.png" alt="DelareaTickets homepage on desktop in Hebrew" width="640" />
  <img src="public/screenshot-mobile.png" alt="DelareaTickets homepage on mobile in Hebrew" width="220" />
</div>

## Problem and solution

Buying a football trip brings together more than a product page: fixtures change, travellers choose ticket categories and add-ons, and the business needs to manage enquiries, orders, customers, and fulfilment. DelareaTickets brings those parts into one Hebrew-first, bilingual platform. The public storefront guides the customer through the purchase flow, while the admin workspace supports catalog management, operations, customer communication, and sales agents.

## Product highlights

- Football tickets, travel packages, and configurable add-ons in a guided purchase flow.
- Hebrew-first RTL and English support, with CMS-backed content and locale fallbacks.
- Hosted payment pages with server-side verification before payment status changes.
- A WhatsApp CRM with a live inbox, scheduled customer journeys, and opt-out handling.
- Personal sales-agent links, attribution, commissions, and payout workflows.

## Engineering decisions

- **Trust payment outcomes independently.** The hosted payment provider redirects shoppers back to the site, but payment status is confirmed through an independently verified webhook path and recorded with the relevant order changes.
- **Keep price calculations precise.** Financial values use `decimal.js` in the application and `numeric(10,2)` in Postgres, so totals, discounts, and commissions do not depend on floating-point arithmetic.
- **Make external work resilient by failure domain.** Fixture and pricing jobs isolate independent failures, use advisory locks to avoid overlapping runs, and retain useful fallbacks when an upstream source is temporarily unavailable.

## Stack

Next.js App Router, React, TypeScript, Tailwind CSS, Supabase Postgres and Auth, Drizzle for types, handwritten SQL migrations, hosted payments, WhatsApp messaging, Vercel, Sentry, and Vitest.

---

Built by [Sagi Menahem](https://sagimenahem.tech) · [AfterTech](https://www.after-tech.co.il/)
