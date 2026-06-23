# 🎯 Dartboard — SECOPS Priority Framework

> **Real incidents. Real priorities.**
> Built from 4 years of daily threat actor activity inside Falcon Complete.

**Live at → [dartboard.david-clarke.id.au](https://dartboard.david-clarke.id.au)**

---

## What is this?

Dartboard is a practitioner-built SECOPS framework distilled from hundreds of real-world incidents. No vendor fluff. No theoretical frameworks. Just the 8 things that consistently separate organisations that get breached from those that don't.

Every priority maps directly to MITRE ATT&CK techniques observed in real intrusions. Every frequency stat is sourced from industry threat reports. Built by a defender, for defenders.

---

## The 8 Priorities

| # | Priority | Severity | Key MITRE Techniques |
|---|----------|----------|----------------------|
| 01 | Know your attack surface | 🔴 CRITICAL | T1595, T1590, T1592 |
| 02 | Remote access tools (RMM) | 🔴 CRITICAL | T1219, T1133, T1078 |
| 03 | Password & MFA reset — harden the helpdesk | 🔴 CRITICAL | T1621, T1598, T1078 |
| 04 | Data exfil tools & services | 🔴 CRITICAL | T1567, T1048, T1074 |
| 05 | Phishing-resistant MFA | 🔴 CRITICAL | T1557, T1621, T1111 |
| 06 | 3rd party incident response plan | 🟠 HIGH | TA0040, T1486, T1490 |
| 07 | Fortify the developers | 🟠 HIGH | T1552, T1195, T1078 |
| 08 | Reduce unmanaged hosts | 🟠 HIGH | T1046, T1133, T1078 |

---

## Features

- **Interactive dartboard** — hover to preview, click any segment to open the full priority detail
- **Live threat feed** — 12 MITRE ATT&CK techniques with real-world abuse frequency data, clickable to jump directly to the related priority
- **MITRE ATT&CK mapped** — every priority links to real observed techniques
- **Source-cited data** — frequency stats backed by CrowdStrike, Unit 42, CyberCX, Picus, and Recorded Future
- **Modal detail view** — clean full-screen pop-out with prev/next navigation across all priorities
- **Fully responsive** — works on desktop, tablet, and mobile
- **Zero dependencies** — single HTML file, no build step, no frameworks

---

## Threat Intelligence Sources

Frequency data in the live feed is drawn from the following reports:

| Source | Report |
|--------|--------|
| CrowdStrike | Global Threat Report 2025 |
| Palo Alto Unit 42 | Incident Response Report 2026 (750+ incidents) |
| CyberCX | Threat Report 2025/2026 |
| Picus Security | Red Report 2026 (1.08M malware samples) |
| Recorded Future | H1 2025 Threat Intelligence Report |

---

## Deploying

This is a single static HTML file — no build step, no dependencies, no Node.

### GitHub Pages

```bash
git clone https://github.com/davidclarke-au/dartboard.git
cd dartboard
# add your index.html
git add .
git commit -m "Deploy"
git push origin main
```

Then enable GitHub Pages under **Settings → Pages → Deploy from branch → main / root**.

### Custom Domain

Add a `CNAME` file to the repo root:

```
dartboard.david-clarke.id.au
```

Add a DNS record at your provider:

| Type | Name | Value |
|------|------|-------|
| CNAME | dartboard | davidclarke-au.github.io |

SSL is auto-provisioned by GitHub Pages once DNS propagates.

---

## Updating Content

All priority content lives in the `PRIORITIES` array in `index.html`. Each entry follows this structure:

```js
{
  num: "01",
  name: "Priority name",
  severity: "CRITICAL",       // CRITICAL or HIGH
  short: "One-liner for hover tooltip",
  detail: "Full detail shown in the modal.",
  tags: ["T1595 Active Scanning", "Tag2", "Tag3"]
}
```

Threat feed data lives in `FEED_TECHNIQUES` with source citations per technique:

```js
{
  id: "T1078",
  name: "Valid Accounts / credential abuse",
  pct: 79,
  sev: "critical",
  sources: [
    { label: "CrowdStrike GTR 2025", note: "79% of detections malware-free" },
  ]
}
```

---

## About

Built by **[David Clarke](https://david-clarke.id.au)** — 4 years as part of the CrowdStrike Falcon Complete team, responding to and hunting threats across hundreds of customer environments daily.

This framework is the distilled answer to one question: *if you could only focus on a handful of things to protect your organisation, what would they be?*

---

## Roadmap

- [ ] Per-priority deep-dive pages
- [ ] About / background section
- [ ] Expanded priority list as new patterns emerge
- [ ] Printable / shareable PDF version

---

<p align="center">
  <a href="https://dartboard.david-clarke.id.au">dartboard.david-clarke.id.au</a>
  &nbsp;&middot;&nbsp;
  Built with zero dependencies
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/davidclarke-au/dartboard">GitHub</a>
</p>
