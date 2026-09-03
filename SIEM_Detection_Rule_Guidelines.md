# SIEM Detection Rule Naming and Description Guidelines
## (Based on Global Standards + Your Team's Patterns)

---

## 1. SIEM Detection Rule Naming Conventions

### 1.1 Objectives

The primary objectives of establishing clear and consistent SIEM rule naming standards are:

- **Clear Communication** — Rule names appear in alerts and incident reports; they must instantly convey what threat is detected so security teams can quickly assess risk
- **Faster Response** — Security teams can quickly understand and prioritize alerts without reading full rule details, reducing mean time to respond (MTTR)
- **Consistency** — Standardized naming across all rules improves team efficiency, reduces confusion, and enables better automation and alert routing
- **Better Collaboration** — New team members quickly understand the detection landscape with consistent naming patterns, accelerating onboarding
- **Compliance** — Rule names document the organization's detection capabilities for audit and compliance purposes, demonstrating comprehensive security posture

---

### 1.2 Your Team's Naming Format (Recommended Standard)

**Pattern Structure:**
```
[Action/Threat Type] [Target Component] [Method/Indicator (optional)]
```

**Components:**

| Component | Description | Examples |
|-----------|-------------|----------|
| **Action/Threat Type** | What's happening or what's suspicious | Suspicious, Malware, Tampering, Disabling, Unauthorized, Brute Force, Lateral Movement |
| **Target Component** | What is being targeted or affected | Outlook Process, Registry Key, Windows Defender, RDP, SMB, Scheduled Task |
| **Method/Indicator** | How it's being done (optional, only if critical) | via Reg.exe, via Powershell, via WMI, Child Process, Registry Modification |

**Examples from Your Team:**

1. `Suspicious Outlook Child Process` — Detects anomalous process spawning from Outlook
2. `AmsiEnable Registry Key tampered` — Detects tampering with AMSI registry key
3. `Disabling Windows Defender WMI Autologger Session via Reg.exe` — Detects defense evasion using reg.exe
4. `Brute Force RDP Attack` — Detects multiple failed RDP login attempts
5. `Lateral Movement via SMB` — Detects suspicious SMB activity across systems

---

### 1.3 Naming Conventions to Follow

#### **Do's:**
- ✅ Use Title Case for readability
- ✅ Start with the action or threat type
- ✅ Include the specific component being targeted
- ✅ Include method only if it's critical security context
- ✅ Use clear, non-technical terms where possible
- ✅ Keep consistent across all rules in your environment
- ✅ Use spaces or hyphens as separators (avoid underscores)
- ✅ Match your team's existing naming pattern

#### **Don'ts:**
- ❌ Avoid abbreviations (unless industry-standard like RDP, SSH, SQL, AMSI, WMI)
- ❌ Don't use generic names like "Suspicious Activity Detected"
- ❌ Avoid rule IDs or technical identifiers in the name
- ❌ Don't make names too long (>100 characters)
- ❌ Avoid duplicate/similar names for different rules
- ❌ Don't use special characters except spaces and hyphens
- ❌ Don't include timestamps or version numbers in the rule name

---

## 2. SIEM Detection Rule Description Guidelines

### 2.1 Your Team's Description Format

Based on your team's actual rules, descriptions should include:

1. **Executive Summary** (1-3 sentences, technical but concise)
   - What is detected?
   - Why is it important/dangerous?
   - What technique or attack does it represent?

---

### 2.2 Rule Description Template (Your Team's Format)

```
RULE NAME: [As per naming convention above]

RULE TYPE: Standard

RULE DESCRIPTION:
[1-3 sentence technical summary. Example: "An attempt was detected to tamper 
with the Windows Antimalware Scan Interface (AMSI). This activity involved 
either disabling AMSI via a registry value change or deleting the AMSI Providers 
registry key"]
```

---

## 3. Best Practices & Implementation Checklist

### 3.1 Rule Naming Best Practices
- [ ] Rule name is 50-100 characters
- [ ] Starts with Action or Threat Type
- [ ] Includes Target Component
- [ ] Includes Method only if critical
- [ ] Uses Title Case format
- [ ] No abbreviations (except industry-standard)
- [ ] Matches team's existing patterns
- [ ] No duplicate names in the environment
- [ ] Easy to understand at first glance

### 3.2 Rule Description Best Practices
- [ ] Executive summary is 1-3 sentences
- [ ] Explains what and why it's important
- [ ] Includes MITRE ATT&CK mapping
- [ ] Specifies severity level accurately
- [ ] Lists correct data sources
- [ ] Tested for false positives
- [ ] Reviewed by security team before deployment

---

This documentation is now complete and ready for your team to use as a standard for creating new SIEM detection rules!
