# Profile Site Redesign — Design Spec

**Date:** 2026-06-21
**Repo:** `jaybilgaye.github.io` (GitHub Pages, static)
**Status:** Approved direction, pending spec review

## Goal

Refresh the public profile site with (1) a new wide visual design and (2) fully
rewritten content reflecting Jay's current role and work. The current site is
stale: it lists an outdated title ("Senior Solution Specialist · Big data"),
the wrong location (Pune), and omits all recent work — products, open source,
certifications, and an authored course.

The redesign repositions Jay as a **Senior Cloud / DevOps Engineer** (cloud-forward,
AWS / Kubernetes / IaC) with deep big-data operational roots as supporting depth,
and a builder/founder track (shipped products + open source).

## Constraints (unchanged)

- Single static page: `index.html` + `assets/style.css`. No framework, no build step.
- Hosted on GitHub Pages at `https://jaybilgaye.github.io`.
- Vanilla HTML/CSS; one tiny inline script (footer year). Google Fonts via CDN.
- Accessible (semantic landmarks, focus states, `prefers-reduced-motion`).

## Visual Design — "D · Minimal, Elevated" (wide, v2)

Approved from the visual companion mockup `design-minimal-wide-v2.html`.

- **Layout:** Two-column. Sticky left **sidebar** (320px) for identity; wide right
  **main column** for content. Collapses to single column under ~860px. Container
  max-width **1240px**.
- **Hero band:** Full-width band at the top with a subtle lime radial glow fading to
  background and a thin lime top-edge line; the circular photo overlaps the band.
- **Palette — lime on near-black (toned-down):** brand accent is **lime**, used
  sparingly (primary button, stat numbers, links/hover, small tick before section
  headers). Earlier bright glows were dialed back per feedback.
  - **Dark:** bg `#0b0d0b`, text `#f3f6f3`, accent text `#c4f06a`, accent fill `#b6f23c`
    (dark text on fill), muted `#9aa39a`, line `#222a22`, faint grid lines.
  - **Light:** bg `#f6f8f4`, text `#16181a`, accent text `#4d7c0f` (deeper olive so it
    stays readable on white), accent fill `#a3e635`, line `#e5e9e0`.
- **Theme switcher:** floating pill, top-right. Cycles **Auto → Light → Dark**;
  choice persisted in `localStorage` (`jb-theme`). **Auto** follows
  `prefers-color-scheme`. Implemented via a `data-theme` attribute on `<html>` plus
  a small inline script. Default = Auto.
- **Type:** "Inter Tight" for display (name, roles, stat numbers), "Inter" for body.
- **Detail touches:** section headers with a small lime tick + trailing rule line;
  accent in intro emphasis and role names; cards lift on hover; tabular date numerals.
- **Photo:** Jay's LinkedIn headshot (`linkedin-profile-2026-compresed.png`),
  circular, saved into `assets/` (e.g. `assets/profile.png`). Used for the avatar
  and `og:image`.

## Content Architecture

Order top-to-bottom in the main column (sidebar is persistent):

1. **Sidebar (identity)** — photo, name, title, location, action buttons, focus pills, links
2. **Stats strip** — 4 real metrics
3. **About** — rewritten summary
4. **Products & Open Source** — *featured, top section* (per decision), as cards
5. **Experience** — 4 roles, updated
6. **Certifications** — compact grid of 7
7. **Writing & Publications** — course + Medium/blog
8. **Footer**

## Content (final copy)

### Identity (sidebar)
- **Name:** Jayprakash Bilgaye
- **Title:** Senior Cloud / DevOps Engineer
- **Location:** Melbourne, Australia
- **Buttons:** Get in touch (`mailto:jaybilgaye@gmail.com`) · LinkedIn · GitHub
- **Phone:** NOT shown publicly (per decision).
- **Focus pills:** AWS · Terraform · Kubernetes / EKS · EMR / Spark · Kafka ·
  ClickHouse · GitHub Actions · Observability · Cloud security & compliance
- **Links row:** GitHub · LinkedIn · Medium · aiopsone.com · X · YouTube

### Link map (all real, confirmed)
- Email: `mailto:jaybilgaye@gmail.com`
- LinkedIn: `https://www.linkedin.com/in/jay-bilgaye/`
- GitHub: `https://github.com/jaybilgaye`
- Medium: `https://medium.com/@jayprakash.bilgaye`
- Blog: `https://aiopsone.com`
- X: `https://x.com/jaybilgaye`
- YouTube: `https://www.youtube.com/@jaybilgaye`
- KafkaGuard: `https://kafkaguard.com`
- ClusterSight: `https://clustersight.io`
- APRA tooling (repo): `https://github.com/jaybilgaye/cps234-aws-config-pack`
- Course: `https://market.tutorialspoint.com/course/azure-kubernetes-service/index.asp`
- CloudScoop (footer): `https://medium.com/cloudscoop`
- Medium articles: Introduction to ClickHouse, AKS in 10 minutes (real URLs from old site), + "More on Medium"

### Stats strip (real numbers)
- **15+** — Years in production
- **7** — Cloud / platform certifications
- **3** — Products shipped
- **120-node** — Clusters operated

### About
> Senior Cloud / DevOps Engineer with **15+ years** building, automating, and
> securing distributed platforms in regulated enterprise environments. I
> **re-platform on-prem Hadoop/Spark workloads onto serverless AWS**, stand up
> production Kubernetes with zero-downtime deploys, and ship infrastructure as
> code in Terraform through GitHub Actions. Deep operational roots — 120-node
> Hadoop clusters and hardened Kafka & ClickHouse estates (TLS, Kerberos, RBAC) —
> now applied as **least-privilege cloud IAM and Kubernetes RBAC**.

### Products & Open Source (featured cards)
1. **KafkaGuard** — Kafka security & compliance scanner. Audits cluster
   configurations against ~55 controls mapped to PCI-DSS, SOC 2, ISO 27001.
   → kafkaguard.com
2. **APRA Compliance Tooling for AWS** *(open source, featured full-width card)* —
   CPS 234 / CPS 230 conformance pack for AWS Config (46 managed rules,
   paragraph-mapped), also covering Cyber Security Act 2024 ransomware-reporting and
   replacing AWS's ~4-year-stale pack; plus Cloud Custodian + Prowler policy-as-code
   and a Bedrock "compliance narrator" for audit-ready reports.
   → github.com/jaybilgaye/cps234-aws-config-pack
3. **ClusterSight.io** — ClickHouse monitoring & observability SaaS, built
   end-to-end (React, Python, Docker, Prometheus). → clustersight.io

### Experience
- **Senior Cloud / DevOps Engineer** — Telstra (client) · Melbourne · Mar 2022 – present
  Re-platformed on-prem Hadoop/Spark ETL onto AWS EMR & EMR Serverless (S3 data
  lake, Athena/Glue/QuickSight); built production EKS with IRSA + dual IAM/RBAC and
  zero-downtime rollouts; Terraform + GitHub Actions IaC; hardened Kafka & ClickHouse.
- **Senior Engineer, Cloud & Ops** — Clairvoyant · Pune · Apr 2017 – Mar 2022
  Led big-data admin across Cloudera & Hortonworks (~300 nodes); AKS via Terraform;
  CIS benchmarking; Prometheus/Grafana observability.
- **Module Lead, DevOps / Hadoop** — Persistent Systems · Pune · May 2014 – Mar 2017
  TLS/SSL + LDAP for Hadoop services; greenfield provisioning through CDH upgrades; NiFi.
- **Programmer Analyst** — Cognizant · Pune · Jul 2010 – Apr 2014
  Multi-node Hadoop cluster install, config, and operational support across distributions.

### Certifications (grid of 7)
AWS Certified Security – Specialty · AWS Certified Solutions Architect – Associate ·
Certified Kubernetes Administrator (CKA) · Microsoft Certified: Azure Administrator
(AZ-104) · Cloudera Certified Hadoop Administrator (CCAH) · Hortonworks Certified
Hadoop Administrator (HDPCA) · Red Hat Certified Engineer (RHCE)

### Writing & Publications
- **Course:** *Azure Kubernetes Service: A Beginner's Guide* — authored on Tutorialspoint. Featured.
- Blog: aiopsone.com — AWS, cloud, and platform engineering writing.
- Medium (@jayprakash.bilgaye): Introduction to ClickHouse · ClickHouse on Docker (Mac) ·
  Azure Kubernetes Service in 10 minutes · more.

### Footer
© <current year> Jayprakash Bilgaye

## SEO / Meta updates
- `<title>` and `meta description` → new role + Melbourne + AWS/cloud focus.
- Open Graph: update `og:title`, `og:description`; add `og:image` (the photo).
- Add JSON-LD `Person` structured data (name, jobTitle, location, sameAs links). *(nice-to-have)*

## Assets
- Add headshot to `assets/profile.png`, referenced by the avatar + `og:image`.
- Source image: `/Users/jay/Downloads/linkedin-profile-2026-compresed.png`.
- Avatar is a CSS circle (`border-radius:50%`, `object-fit:cover`) with
  `object-position:center 22%` to keep headroom above the head. No manual crop needed.

## Out of scope
- Multi-page site, blog engine, CMS, analytics, contact form.
- Phone number, full resume PDF download (can add later if wanted).

## Resolved during brainstorming
- Palette: dark/light **lime** (toned down), not teal. ✔
- Theme switcher: Auto / Light / Dark, localStorage. ✔
- Photo: LinkedIn headshot, circular, headroom crop. ✔
- All links real and confirmed (incl. YouTube, Tutorialspoint course). ✔
- CloudScoop: kept in the footer. ✔
- Stats: 15+ / 7 / 3 / 120-node. ✔
- Reference implementation: `.superpowers/brainstorm/.../design-minimal-wide-v4.html`
  (this is the approved visual + content; implementation ports it into the real files).
