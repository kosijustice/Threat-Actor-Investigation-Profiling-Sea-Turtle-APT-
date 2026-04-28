# Threat-Actor-Investigation-Profiling-Sea-Turtle-APT-
A real-world cyber threat intelligence investigation into the Sea Turtle APT group, conducted using MISP, MITRE ATT&amp;CK, VirusTotal, and AbuseIPDB. Includes IOC correlation, TTP mapping, infrastructure analysis, and defensive recommendations.**
 🐢 Threat Actor Investigation & Profiling — Sea Turtle (APT)

<div align="center">

![MISP](https://img.shields.io/badge/Platform-MISP-4B0082?style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgo=&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red?style=for-the-badge&logoColor=white)
![Threat Intel](https://img.shields.io/badge/Type-Threat_Intelligence-darkred?style=for-the-badge)
![APT](https://img.shields.io/badge/Actor-State_Sponsored_APT-black?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![TLP](https://img.shields.io/badge/TLP-WHITE-white?style=for-the-badge&labelColor=555555)

**A real-world cyber threat intelligence investigation into the Sea Turtle APT group, conducted using MISP, MITRE ATT&CK, VirusTotal, and AbuseIPDB. Includes IOC correlation, TTP mapping, infrastructure analysis, and defensive recommendations.**

[📋 Executive Summary](#-executive-summary) • [🔬 Methodology](#-misp-investigation-methodology) • [🌐 Infrastructure](#-infrastructure-analysis) • [⚔️ TTPs](#️-mitre-attck-ttp-mapping) • [🛡️ Mitigations](#️-mitigation-recommendations)

</div>

---

## 📌 Table of Contents

- [Investigation Context](#-investigation-context)
- [Executive Summary](#-executive-summary)
- [MISP Investigation Methodology](#-misp-investigation-methodology)
- [Infrastructure Analysis](#-infrastructure-analysis)
- [IOC Analysis from MISP](#-ioc-analysis-from-misp)
- [OSINT Correlation](#-osint-correlation)
- [MITRE ATT&CK TTP Mapping](#️-mitre-attck-ttp-mapping)
- [MISP Correlation Analysis](#-misp-correlation-analysis)
- [Threat Actor Profile](#-threat-actor-profile--sea-turtle)
- [Key IOCs Summary](#-key-iocs-summary)
- [Detection Indicators](#-detection-indicators)
- [Executive Risk Summary](#-executive-risk-summary)
- [Mitigation Recommendations](#️-mitigation-recommendations)
- [Tools & Platforms Used](#️-tools--platforms-used)
- [Author](#-author)

---

## 🔭 Investigation Context

| Field | Details |
|-------|---------|
| **Investigation Target** | Sea Turtle — State-Aligned APT Group |
| **Platform** | MISP Threat Sharing Platform |
| **MISP Event ID** | 1869 |
| **MISP UUID** | `4b79f6b1-f69c-483b-9d24-6e20039f5e96` |
| **Source Event** | 187 (CUDESO, 2019-07-09) |
| **IOCs Merged** | 15 verified Indicators of Compromise |
| **TTPs Mapped** | 9 MITRE ATT&CK Techniques |
| **Classification** | Strategic & Operational Threat Intelligence |
| **Analyst** | Justice C. Alucho — Cybersecurity SOC Analyst |
| **Context** | Authorized Cybersecurity Research Lab |

### Background

A recent surge in malicious activity has been detected targeting critical infrastructure and government agencies across Europe. Current intelligence identifies five primary threat groups as suspected originators. This investigation deep-dives into **Sea Turtle**, one of the five, using real-world intelligence from the MISP platform.

**Investigation Objectives:**

1. **Infrastructure Mapping** — Identify command-and-control (C2) and delivery systems
2. **Technical Analysis** — Evaluate Indicators of Compromise (IOCs) to determine actor TTPs
3. **Risk Mitigation** — Construct comprehensive threat profiles to provide actionable defensive strategies

---

## 📋 Executive Summary

This investigation confirms the presence of a **high-confidence strategic cyber threat** linked to the Sea Turtle threat actor, identified through real-world intelligence correlation using MISP threat feeds and OSINT platforms.

> **Sea Turtle is a state-aligned cyber espionage group known for long-term, stealthy operations focused on infrastructure-level compromise rather than noisy malware activity.**

Unlike financially motivated cybercriminal groups, Sea Turtle operates with **strategic intent**, targeting government, military, telecom, and critical infrastructure sectors. Their primary technique — **DNS hijacking combined with Adversary-in-the-Middle (AiTM) operations** — allows them to silently intercept communications, harvest credentials, and manipulate network traffic without triggering traditional endpoint security controls.

### Strategic Risk Overview

MISP correlation confirms this activity is **not isolated**. The actor demonstrates:

- ♻️ Persistent operational behavior and infrastructure reuse
- 📅 Long-term campaign continuity across multiple intelligence events
- 🖧 Dedicated C2 nodes, rogue DNS infrastructure, and MITM nodes
- 🔇 Low-noise, high-impact operational model

### Confirmed Threat Outcomes

| Risk | Impact |
|------|--------|
| Long-term data interception | ⚠️ Critical |
| Intelligence leakage | ⚠️ Critical |
| Credential compromise | ⚠️ Critical |
| Network trust erosion | 🔴 High |
| Regulatory & compliance exposure | 🔴 High |
| National & organizational security risk | ⚠️ Critical |

> **Key Leadership Implication:** This threat validates the need to shift from **reactive cybersecurity** to **proactive, intelligence-driven defense**. Protection must extend beyond endpoints into DNS security, network monitoring, infrastructure integrity, and threat intelligence integration.

---

## 🔬 MISP Investigation Methodology

### Step 1 — MISP Intelligence Search

Performed comprehensive queries within the MISP platform leveraging:

- **Talos Intelligence** — Validate IOCs against Cisco's threat intelligence feeds
- **MITRE ATT&CK Framework** — Map behaviors to known adversary techniques
- **MISP Galaxy** — Identify related clusters and attribution patterns

### Step 2 — APT Profile Creation

Created a dedicated Advanced Persistent Threat (APT) profile within MISP:

```
Event:        1869
Profile Name: APT Profile – Sea Turtle DNS Hijacking Campaign
Purpose:      Consolidate indicators, behavioral patterns, and contextual intelligence
```

### Step 3 — Threat Actor Taxonomy Applied

```
Taxonomy:   misp-galaxy:threat-actor
Actor:      Sea Turtle
Cluster ID: 81836
Purpose:    Establish attribution consistency and structured intelligence mapping
```

### Step 4 — Indicator Correlation & IOC Merging

Merged **15 verified IOCs** from Source Event 187 into Event 1869 using MISP's merge functionality:

- ✅ Consolidation of validated intelligence
- ✅ Elimination of duplicate entries
- ✅ Centralized event management

### Step 5 — TTP Documentation

Mapped and documented **9 MITRE ATT&CK Tactics, Techniques, and Procedures (TTPs)**, linked to Sea Turtle operations using MISP Galaxy relationships.

### Step 6 — Intelligence Report Authoring

Produced a structured intelligence report within the MISP Event Reports module:

- Analyst findings
- Technical assessment
- Attribution rationale
- Supporting evidence and correlation analysis

### Step 7 — Publication & Export

Published the finalized intelligence event and exported in **STIX 2 format** for:

- Information sharing
- Inter-organizational collaboration
- Threat intelligence dissemination

---

## 🌐 Infrastructure Analysis

### Infrastructure Types Used by Sea Turtle

```
┌─────────────────────────────────────────────────────────────────────┐
│                    SEA TURTLE INFRASTRUCTURE MAP                    │
├──────────────────────┬──────────────────┬───────────────────────────┤
│  Infrastructure Type │ Assessment       │ Role                      │
├──────────────────────┼──────────────────┼───────────────────────────┤
│  C2 Servers          │ ✅ Confirmed      │ Remote control & coord.   │
│  DNS Hijacking Nodes │ ✅ Confirmed      │ Core attack vector        │
│  Rogue Nameservers   │ ✅ Confirmed      │ DNS manipulation          │
│  MITM Infrastructure │ ✅ Confirmed      │ Session interception       │
│  Exploit Infra.      │ ✅ Confirmed      │ Public app exploitation   │
│  Phishing Infra.     │ ⚠️ Limited       │ Secondary credential ops  │
│  Cloud Abuse         │ 🔵 Possible      │ Staging / proxying        │
└──────────────────────┴──────────────────┴───────────────────────────┘
```

### Command & Control (C2) Infrastructure

**Purpose:** Malware control, session management, data exfiltration, remote access persistence

```
Operational Nodes (C2 Servers):
├── 185.64.105.100   → Primary C2 node
└── 178.17.167.51    → Primary C2 node
```

### DNS & Network Manipulation Infrastructure

**Primary Technique:** DNS Hijacking

```
Actor-Controlled DNS Infrastructure:
├── Compromised DNS registrars
├── Rogue name servers
├── MITM routing nodes
└── ns1.rootdnsservers.com   → Actor-controlled nameserver

MITM Nodes:
├── 95.179.131.225
├── 140.82.58.253
├── 45.32.100.62
└── 193.46.255.33
```

**Purpose:** Credential interception, session hijacking, traffic redirection, AiTM attacks, credential harvesting

---

## 🔍 IOC Analysis from MISP

### MISP Attributes — Evidence Screenshots

**📸 Screenshot 1 — MISP Event 1887 Overview & Sea Turtle Threat Actor Profile**

> *MISP platform showing Event 1887 tagged with `misp-galaxy:threat-actor='Sea Turtle'`, Threat Level: High, Analysis: Completed. The Sea Turtle Threat Actor Profile is visible in the Event Reports section showing Overview, Targeting, and TTPs sections. 15 attributes (IOCs) are listed with related events correlated.*

---

**📸 Screenshot 2 — MISP Attributes Table — Full IOC List**

> *Full MISP attribute view showing all 15 merged IOCs from Event 187. IOC types include: IP-DST (Operational Nodes, MITM Nodes), hostname (Actor-controlled nameservers), and external analysis links. All attributes tagged with MISP Galaxy and correlated across 2+ related events.*

---

### IOC Summary Table

| IOC Type | Value | Category | Classification |
|----------|-------|----------|----------------|
| `ip-dst` | `185.64.105.100` | Network Activity | Operational Node (C2) |
| `ip-dst` | `178.17.167.51` | Network Activity | Operational Node (C2) |
| `ip-dst` | `95.179.131.225` | Network Activity | MITM Node |
| `ip-dst` | `140.82.58.253` | Network Activity | MITM Node |
| `ip-dst` | `95.179.156.61` | Network Activity | MITM Node |
| `ip-dst` | `196.29.167.100` | Network Activity | MITM Node |
| `ip-dst` | `188.226.192.35` | Network Activity | MITM Node |
| `ip-dst` | `45.32.100.62` | Network Activity | Hosted Malicious |
| `ip-dst` | `193.46.255.33` | Network Activity | MITM Node |
| `hostname` | `ns1.rootdnsservers.com` | Network Activity | Actor-Controlled Nameserver |
| `hostname` | `ns2.rootdnsservers.com` | Network Activity | Actor-Controlled Nameserver |
| `link` | Talos Intelligence Report | External Analysis | Merged from Event 190 |
| `link` | MITRE ATT&CK Reference | External Analysis | Merged from Event 190 |

---

## 🌍 OSINT Correlation

### VirusTotal Analysis

**📸 Screenshot 3 — VirusTotal Detection: 45.32.100.62**

> *VirusTotal scan of `45.32.100.62` (AS20473 — The Constant Company, LLC). Result: **1/93 security vendors flagged this IP as malicious**. SOCRadar detection: Malware. Analysis conducted 20 days prior. Community Score: 1. This IP appears in the MISP IOC list as "Hosted Malicious" confirming the MISP intelligence.*

```
IP:              45.32.100.62  (45.32.0.0/16)
ASN:             AS20473 (The Constant Company, LLC)
Flag:            1/93 vendors — SOCRadar: Malware
Location:        SG (Singapore)
Analyst Note:    Corroborates MISP classification as malicious hosted infrastructure
```

---

### AbuseIPDB Analysis

**📸 Screenshot 4 — AbuseIPDB: 193.46.255.33**

> *AbuseIPDB lookup of `193.46.255.33` showing **Confidence of Abuse: 100%**, reported **271,026 times**. ISP: UNMANAGED LTD. Usage Type: Data Center/Web Hosting/Transit. ASN: AS47890. Hostname: `hostingmailto181.statics.servermail.org`. This confirms the IP's role as a hostile infrastructure node.*

```
IP:              193.46.255.33
Abuse Score:     100% (Maximum confidence)
Report Count:    271,026 reports
ISP:             UNMANAGED LTD
ASN:             AS47890
Type:            Data Center / Web Hosting / Transit
Analyst Note:    100% confidence score confirms active malicious use — highest severity rating
```

---

## ⚔️ MITRE ATT&CK TTP Mapping

### Visual Reference

**📸 Screenshot 5 — MITRE ATT&CK T1557 (Adversary-in-the-Middle)**

> *MITRE ATT&CK navigator showing T1557 — Adversary-in-the-Middle technique, confirming Sea Turtle's AiTM methodology. Associated groups include LuminousMoth, Wizard Spider, and Mustang Panda — illustrating how widely this technique is shared across APT actors.*

**📸 Screenshot 6 — MITRE ATT&CK T1584 (Compromise Infrastructure)**

> *MITRE ATT&CK entry for T1584 showing groups including Indrik Spider, Evil Corp, and Axiom using infrastructure compromise. Sea Turtle's use of this technique involves compromising third-party DNS servers and web hosting environments as staging platforms.*

---

### Full TTP Table

| ID | Technique | Sea Turtle Implementation | Phase |
|----|-----------|--------------------------|-------|
| **T1583** | Acquire Infrastructure | Purchasing domains and renting VPS instances to host shadow nameservers and C2 nodes | Preparation |
| **T1584** | Compromise Infrastructure | Compromising third-party DNS servers and legitimate web hosting to host malicious tools | Preparation |
| **T1566** | Phishing | Spear-phishing employees at DNS registrars and telecoms to steal admin credentials | Initial Access |
| **T1557** | Adversary-in-the-Middle (AiTM) | Modifying DNS records at registrar level to position as MITM and intercept credentials | Core Strategy |
| **T1588.004** | Obtain Capabilities: Digital Certificates | Obtaining CA-signed X.509 certificates for target domains to facilitate AiTM attacks | Resource Development |
| **T1046** | Network Service Discovery | Using scanning tools in compromised environments (e.g., cPanel) to identify internal services | Discovery |
| **T1114.001** | Email Collection: Local | Collecting email archives from victim environments (cPanel accounts) for intelligence gathering | Collection |
| **T1560.001** | Archive Collected Data: via Utility | Using `tar` to bundle email and sensitive files into archives before exfiltration | Exfiltration |
| **T1070.002** | Indicator Removal: Clear Linux/Mac Logs | Overwriting Linux system logs and unsetting Bash history to erase post-exploitation tracks | Defense Evasion |
| **T1071** | Application Layer Protocol | Custom malware (SnappyTCP) using HTTP/S for C2 communication to blend with legitimate traffic | C2 |

---

### 🧠 Analyst Note: The Sea Turtle Kill Chain

```
Sea Turtle doesn't hack a website — they hack the entire PATH to that website.

Step 1: PREPARATION  (T1583 / T1584)
        └── Set up or compromise infrastructure (nameservers, VPS, domains)

Step 2: ACCESS       (T1566 / T1199)
        └── Spear-phish a DNS registrar employee or exploit a trusted relationship

Step 3: THE PIVOT    (T1557)
        └── Modify DNS records to redirect ALL traffic through actor-controlled node
            → Every login, every credential, every session is now intercepted

Step 4: THE PAYOFF   (T1114.001 / T1071)
        └── Harvest credentials, collect email archives, exfiltrate intelligence
            → Victim never knows their traffic was silently rerouted
```

---

## 🔗 MISP Correlation Analysis

### Related Event Identified

```
Event Title:    "Sea Turtle keeps on swimming, finds new victims, DNS hijacking techniques"
Date:           2019-07-09
Correlated IOC Count: 15
```

### What This Correlation Means

| Correlation Signal | Intelligence Interpretation |
|-------------------|----------------------------|
| Shared IOCs across events | Same infrastructure reused across multiple campaigns |
| Campaign continuity | Active operations spanning multi-year timelines |
| Infrastructure reuse | Deliberate operational consistency — not random |
| Recurrent targeting | Systematic focus on specific sectors and geographies |
| Persistent operations | Ongoing threat — not a one-time campaign |

> **Intelligence Conclusion:** Sea Turtle is not an isolated campaign actor. It is a **persistent, long-term threat group** with reused infrastructure, repeated DNS-based attack chains, long operational timelines, and strategic targeting across multiple years.

---

## 🎯 Threat Actor Profile — Sea Turtle

### Identity & Attribution

| Field | Value |
|-------|-------|
| **Primary Name** | Sea Turtle |
| **Known Aliases** | Teal Kurma, Silicon, Cosmic Wolf |
| **Suspected Origin** | Turkey |
| **Attribution Type** | State-aligned / State-sponsored |
| **Operational Alignment** | Turkish national strategic interests |
| **Cluster ID (MISP)** | 81836 |
| **Threat Level** | 🔴 High |

### Motivation Assessment

| Category | Assessment | Analyst Evaluation |
|----------|------------|-------------------|
| **Espionage** | ✅ Confirmed — Primary | Core operational objective focused on intelligence gathering and strategic data acquisition |
| **Intelligence Collection** | ✅ Confirmed | Direct evidence of credential harvesting, network interception, and surveillance activity |
| **Financial Gain** | ❌ Not Observed | Actor does not demonstrate ransomware or financially motivated behavior |
| **Sabotage** | ❌ Not Primary | Infrastructure attacks focus on access — not destruction |

**Primary Motivation: Cyber espionage and intelligence collection**

### Targeting Profile

**Sectors Targeted:**

```
├── 🏛️  Government agencies
├── ⚔️  Military organizations
├── 🕵️  Intelligence agencies
├── 🤝  Diplomatic organizations
├── 📡  Telecom providers
└── 🏗️  National critical infrastructure
```

**Geographic Focus:**

```
Primary Regions:
├── Middle East (MENA)
├── North Africa
└── Eastern Mediterranean

Countries Targeted:
├── Turkey    ├── Greece
├── Cyprus    ├── Iraq
├── Syria     └── Egypt
```

### Tools, Malware & Capabilities

| Category | Examples |
|----------|---------|
| **Custom Malware** | SnappyTCP (HTTP/S C2 communication) |
| **DNS Toolkits** | Custom DNS manipulation frameworks |
| **Network Tools** | Traffic redirection frameworks, network sniffing tools |
| **MITM Systems** | Proxy-based attack frameworks |
| **Credential Tools** | Credential harvesting platforms |
| **Persistence** | Infrastructure persistence scripts |

---

## 📊 Key IOCs Summary

### Operational Infrastructure

```
C2 Nodes (Command & Control):
├── 185.64.105.100
└── 178.17.167.51

MITM Nodes (Adversary-in-the-Middle):
├── 95.179.131.225
├── 45.32.100.62       ← VirusTotal: Malware (1/93)
├── 140.82.58.253
├── 193.46.255.33      ← AbuseIPDB: 100% abuse confidence, 271,026 reports
└── 95.179.156.61

DNS Infrastructure:
├── ns1.rootdnsservers.com   ← Actor-controlled nameserver
└── ns2.rootdnsservers.com   ← Actor-controlled nameserver
```

### IOC Severity Assessment

| IOC | Type | Severity | Verified By |
|-----|------|----------|-------------|
| `193.46.255.33` | MITM Node | 🔴 Critical | AbuseIPDB: 100% confidence |
| `45.32.100.62` | Hosted Malicious | 🔴 High | VirusTotal: SOCRadar Malware |
| `ns1.rootdnsservers.com` | Rogue Nameserver | 🔴 Critical | MISP + OSINT |
| `185.64.105.100` | C2 Server | 🔴 Critical | MISP Correlation |
| `178.17.167.51` | C2 Server | 🔴 Critical | MISP Correlation |
| `95.179.131.225` | MITM Node | 🟠 High | MISP Correlation |

---

## 🚨 Detection Indicators

### Network-Level Detection Signals

```
DNS Indicators:
├── Unauthorized DNS resolver changes
├── Rogue name server entries appearing in DNS delegation
├── Unexpected DNS propagation changes
├── Abnormal DNS TTL values (unusually low = fast redirect capability)
└── DNS registrar modification logs showing unauthorized access

Traffic Indicators:
├── TLS certificate mismatches (wrong CA or provider for domain)
├── Traffic redirection anomalies (unexpected routing paths)
├── MITM behavior patterns in network flow analysis
├── Unexpected IP routing paths for known-good domains
└── Traffic flows through untrusted or unrecognized nodes
```

### Security Operations Signals

```
Certificate Anomalies:
├── Certificate chain irregularities
├── CA-signed certificates from unexpected providers
└── Domain certificates issued by non-standard authorities

Authentication Signals:
├── Sudden domain resolution changes (pre vs. post DNS query)
├── Credential reuse from unexpected sources/locations
└── Authentication from IPs not in baseline activity
```

### SIEM Detection Queries (Example)

```splunk
# Detect DNS resolution to known IOC IPs
index=dns_logs dest_ip IN ("185.64.105.100","178.17.167.51","95.179.131.225","140.82.58.253","193.46.255.33","45.32.100.62")
| table _time, src_ip, dest_ip, query, record_type

# Detect queries to actor-controlled nameservers
index=dns_logs query IN ("rootdnsservers.com","ns1.rootdnsservers.com","ns2.rootdnsservers.com")
| table _time, src_ip, query, answer

# Detect TLS certificate anomalies
index=tls_logs
| eval cert_mismatch=if(issuer_org!=expected_org,"YES","NO")
| where cert_mismatch="YES"
| table _time, src_ip, dest_domain, issuer_org, expected_org
```

---

## ⚠️ Executive Risk Summary

Sea Turtle represents a **high-level strategic cyber threat** characterized by:

```
THREAT CHARACTERISTICS:
├── 🕐 Long-term persistence (multi-year campaigns)
├── 🏛️ State-aligned operations
├── 🌐 Infrastructure-layer manipulation
├── 🎯 Intelligence-focused targeting
└── 🔇 Low-noise, high-impact operations

BUSINESS & NATIONAL RISK:
├── 📁 Data sovereignty compromise
├── 🔒 National security exposure
├── 🤝 Diplomatic data interception
├── 📋 Regulatory compliance violations
├── 🕵️ Long-term espionage exposure
└── 🔗 Supply-chain trust erosion
```

> ⚠️ **This actor does not rely on noisy ransomware operations. Their threat model is stealth, persistence, and long-term intelligence access. Traditional endpoint security alone will NOT detect Sea Turtle.**

---

## 🛡️ Mitigation Recommendations

### Recommendation 1 — DNS & Infrastructure Hardening (Strategic)

**Implement DNS Security Governance:**

```
DNSSEC:
├── Enable DNSSEC signing on all organizational zones
├── Validate DNSSEC on all outbound DNS resolvers
└── Monitor for DNSSEC validation failures

Registrar Security:
├── Enable MFA on ALL DNS registrar accounts
├── Activate Registry Lock services for critical domains
├── Restrict registrar account access to named administrators only
└── Enable out-of-band change notifications for DNS modifications

DNS Monitoring:
├── Deploy continuous DNS telemetry monitoring
├── Alert on any name server changes
├── Monitor DNS TTL anomalies
└── Validate name server integrity against known-good baseline
```

**Expected Impact:** Prevents DNS hijacking, MITM attacks, and infrastructure compromise at the root level.

---

### Recommendation 2 — Network Detection & Intelligence Integration (Operational)

**Deploy Intelligence-Driven Detection Engineering:**

```bash
# Suricata IDS Rule — Detect connections to Sea Turtle C2 nodes
alert ip any any -> [185.64.105.100,178.17.167.51] any \
  (msg:"Sea Turtle C2 Node Contact Detected"; \
   classtype:trojan-activity; sid:9000001; rev:1;)

# Suricata IDS Rule — Detect MITM node communication
alert ip any any -> [95.179.131.225,140.82.58.253,193.46.255.33,45.32.100.62] any \
  (msg:"Sea Turtle MITM Node Contact Detected"; \
   classtype:network-scan; sid:9000002; rev:1;)

# Suricata IDS Rule — Detect rogue nameserver queries
alert dns any any -> any 53 \
  (msg:"Sea Turtle Rogue Nameserver Query"; \
   dns.query; content:"rootdnsservers.com"; \
   classtype:policy-violation; sid:9000003; rev:1;)
```

**MISP → SIEM → IDS Integration Pipeline:**

```
MISP (IOC Source)
    ↓  (STIX 2 export / API feed)
SIEM (Splunk / QRadar / Wazuh)
    ↓  (Automated IOC ingestion)
IDS / Firewall (Suricata / Snort / pfSense)
    ↓  (Real-time blocking rules)
SOC Alert Queue
    ↓  (Analyst investigation)
Incident Response
```

**Expected Impact:** Transforms threat intelligence into real-time detection and active prevention.

---

### Priority Action Matrix

| Priority | Action | Tool | Timeline |
|----------|--------|------|----------|
| 🔴 Immediate | Block all IOC IPs at perimeter firewall | Firewall / ACL | 24 hours |
| 🔴 Immediate | Enable MFA on DNS registrar accounts | Registrar portal | 24 hours |
| 🟠 High | Deploy DNSSEC on critical domains | DNS server | 7 days |
| 🟠 High | Ingest Sea Turtle IOCs into SIEM | MISP → Splunk | 7 days |
| 🟡 Medium | Configure Suricata rules for IOC detection | Suricata IDS | 30 days |
| 🟡 Medium | Implement certificate transparency monitoring | TLS monitoring | 30 days |
| 🟢 Ongoing | Subscribe to MISP threat feeds | MISP platform | Continuous |
| 🟢 Ongoing | DNS telemetry monitoring | SOC workflow | Continuous |

---

## 🏁 Executive Conclusion

Sea Turtle is not a conventional cybercriminal group — it is a **strategic cyber espionage actor** using infrastructure-level attacks rather than malware-heavy operations. Their focus on DNS hijacking and MITM positioning allows them to **silently intercept data at scale**, making detection difficult and impact severe.

```
KEY INTELLIGENCE TAKEAWAYS:

✅ Sea Turtle is state-aligned — Turkish national strategic interests drive targeting decisions
✅ DNS hijacking is their core TTPs — not malware, not ransomware
✅ MISP correlation confirms multi-year campaign continuity and infrastructure reuse
✅ OSINT validation (VirusTotal + AbuseIPDB) corroborates MISP IOC classifications
✅ 9 MITRE ATT&CK techniques mapped — providing structured adversary profiling
✅ Endpoint security alone is insufficient — network and DNS layers must be defended
⚠️ Organizations without DNS monitoring and threat intelligence integration remain exposed
```

**Final Leadership Message:**

> *"Organizations that rely only on endpoint security will not detect actors like Sea Turtle. Defense must move to the network, infrastructure, and intelligence layers."*

---

## 🗂️ Repository Structure

```
sea-turtle-threat-investigation/
│
├── README.md                          ← This file — full investigation report
│
├── iocs/
│   ├── ip_indicators.txt              ← All IP-based IOCs (C2, MITM nodes)
│   ├── domain_indicators.txt          ← DNS/hostname IOCs
│   └── stix2_export.json             ← STIX 2 formatted IOC export from MISP
│
├── misp/
│   ├── event_1869_profile.md          ← Sea Turtle APT profile created in MISP
│   └── misp_methodology.md            ← Step-by-step MISP investigation workflow
│
├── ttps/
│   └── mitre_attack_mapping.md        ← Full MITRE ATT&CK TTP mapping table
│
├── screenshots/
│   ├── 01_misp_event_overview.png     ← MISP Event 1887 — Sea Turtle profile
│   ├── 02_misp_attributes_table.png   ← Full IOC attribute list in MISP
│   ├── 03_virustotal_45.32.100.62.png ← VirusTotal detection result
│   ├── 04_abuseipdb_193.46.255.33.png ← AbuseIPDB 100% abuse confidence
│   ├── 05_mitre_t1557.png             ← MITRE ATT&CK T1557 AiTM reference
│   └── 06_mitre_t1584.png             ← MITRE ATT&CK T1584 Infra Compromise
│
├── detections/
│   ├── suricata_rules.rules           ← Suricata IDS detection rules for Sea Turtle IOCs
│   └── splunk_queries.txt             ← SIEM detection queries
│
└── reports/
    └── Sea_Turtle_Full_Report.pdf     ← Complete investigation report (PDF)
```

---

## 🧰 Tools & Platforms Used

| Tool | Purpose |
|------|---------|
| **MISP** | Threat intelligence platform — IOC management, correlation, event profiling |
| **MITRE ATT&CK** | TTP mapping and adversary behavior framework |
| **VirusTotal** | OSINT validation of malicious IPs and infrastructure |
| **AbuseIPDB** | IP reputation and abuse confidence scoring |
| **Talos Intelligence** | Cisco's threat intelligence feed for indicator validation |
| **STIX 2** | Structured Threat Information eXpression — IOC export format |

---

## 📚 References

- [MITRE ATT&CK — Sea Turtle](https://attack.mitre.org/groups/G0079/)
- [Talos Intelligence — Sea Turtle Campaign](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)
- [CUDESO MISP Event 187 — 2019-07-09](https://www.misp-project.org/)
- [MITRE T1557 — Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557/)
- [MITRE T1584 — Compromise Infrastructure](https://attack.mitre.org/techniques/T1584/)
- [AbuseIPDB](https://www.abuseipdb.com/)
- [VirusTotal](https://www.virustotal.com/)

---

## 👤 Author

<div align="center">

**Justice C. Alucho**
*Cybersecurity SOC Analyst | Threat Intelligence | Incident Response*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-justice--alucho-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/justice-alucho-30aba6145)
[![GitHub](https://img.shields.io/badge/GitHub-kosijustice-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/kosijustice)
[![Email](https://img.shields.io/badge/Email-kosijustice7alucho@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:kosijustice7alucho@gmail.com)


</div>

---

## 📄 License

This project is licensed under the MIT License — research and educational use.

---

<div align="center">

*⭐ If this investigation demonstrates skills relevant to your team, feel free to star the repository.*

**Threat Intelligence Research | MISP Platform | MITRE ATT&CK | OSINT Correlation**

`#ThreatIntelligence` `#MISP` `#MITREATTACK` `#APT` `#SeaTurtle` `#DNSHijacking` `#CyberEspionage` `#SOCAnalyst` `#ThreatHunting`

</div>
See below the full Report
[Threat-Actor-Investigation-Report](https://github.com/kosijustice/Threat-Actor-Investigation-Profiling-Sea-Turtle-APT-/blob/main/Threat%20Actor%20Investigation%20and%20Profiling%20MAIN%20DOC%20Google%20Docs.pdf)
