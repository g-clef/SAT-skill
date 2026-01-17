# Indicators or Signposts of Change for Cyber Threat Intelligence

## Overview

Indicators or Signposts of Change is a technique for identifying observable events that would signal a change in the current threat environment or validate/invalidate a hypothesis. It helps analysts move from static assessments to dynamic monitoring and early warning.

**Best used for:** Monitoring threat actor evolution, anticipating campaign changes, tracking capability development, watching for strategic shifts, validating ongoing assessments.

## Guided Process

### Step 1: Define the Baseline and Potential Changes

**Guide the analyst to articulate the current state and possible future states.**

Questions to ask:
- "What's the current state or pattern you're observing with this threat?"
- "What are the possible ways this threat could evolve or change?"
- "What different scenarios or outcomes are you concerned about?"
- "What would represent a significant shift from the current baseline?"

**CTI Examples:**

*Current state:*
- "APT29 is conducting espionage campaigns using these TTPs."
- "FIN7 targets retail and hospitality with ransomware."
- "This threat actor operates from 9am-5pm UTC+3."
- "The malware family uses HTTP for C2."

*Potential changes:*
- "The actor might expand to new victim sectors."
- "The actor could shift from espionage to disruption."
- "The actor may develop zero-day capabilities."
- "The actor might change operational security practices."
- "The campaign might end or go dormant."
- "A new actor might emerge targeting the same victims."

### Step 2: Identify Observable Indicators for Each Change

**For each potential change, guide them to identify specific, observable indicators.**

Questions to ask:
- "What would you actually SEE if [this change] were happening?"
- "What technical, behavioral, or contextual signs would appear?"
- "Would this change be sudden and obvious, or gradual and subtle?"
- "What's the earliest indicator you might detect?"
- "What's the most reliable indicator?"

**Characteristics of good indicators:**
- **Observable:** Can be detected through available collection
- **Specific:** Clearly defined, not vague
- **Measurable:** Objective, not subjective interpretation
- **Timely:** Provides adequate warning time
- **Discriminating:** Distinguishes this change from other possibilities

**CTI indicator categories:**

*Technical indicators:*
- New malware capabilities or tooling
- Infrastructure changes (hosting, protocols, obfuscation)
- Different exploitation methods or vulnerabilities
- Changes in malware signatures or artifacts
- Operational security improvements or failures

*Behavioral indicators:*
- Targeting pattern shifts
- Operational tempo changes
- Timing/timezone modifications
- Reconnaissance activity in new sectors
- Changes in exfiltration methods or volumes

*Contextual indicators:*
- Geopolitical events or policy changes
- Organizational changes in sponsor country
- Public attribution or exposure
- Arrests or law enforcement actions
- Budget or resource indicators

### Step 3: Develop Indicator Statements

**Help them write clear, specific indicator statements.**

Format: "We would observe [specific event/pattern] if [change scenario] were occurring."

Questions to ask:
- "Can you make that indicator more specific and measurable?"
- "How would you know if you saw this? What exactly would you look for?"
- "Is this indicator unique to this change, or could it mean multiple things?"

**Examples of indicator statements:**

*For expansion to new sectors:*
- "We would observe reconnaissance scanning against energy companies if the actor were expanding beyond defense contractors."
- "We would see malware samples submitted from financial institutions if targeting scope expanded."

*For TTP evolution:*
- "We would observe use of previously unseen CVEs if the actor developed zero-day capability."
- "We would detect encrypted C2 communications using new protocols if the actor upgraded operational security."

*For operational changes:*
- "We would see activity outside the established 9am-5pm UTC+3 window if the actor changed personnel or locations."
- "We would observe longer gaps between campaigns if the actor went dormant or shifted priorities."

*For strategic shifts:*
- "We would detect destructive payloads rather than exfiltration tools if the mission changed from espionage to disruption."
- "We would observe public data dumps if the actor shifted from state-sponsored espionage to hacktivist behavior."

### Step 4: Establish Monitoring Plan

**Guide them to create a practical monitoring approach.**

Questions to ask:
- "What data sources would detect each indicator?"
- "How frequently should you check for these indicators?"
- "Who is responsible for monitoring each indicator?"
- "What's your response plan if you detect an indicator?"

**Monitoring considerations:**

*Data sources:*
- Internal telemetry (SIEM, EDR, network sensors)
- External sources (industry reports, OSINT, sharing groups)
- Targeted collection (specific indicators or infrastructure)
- Automated feeds (threat intelligence platforms)

*Collection gaps:*
- "Are there indicators you CAN'T currently monitor? What would you need?"
- "Do you have blind spots in your detection coverage?"

*Frequency:*
- Continuous (automated monitoring)
- Daily (manual review of feeds)
- Weekly (broader pattern analysis)
- Event-driven (triggered by specific occurrences)

### Step 5: Prioritize Indicators

**Help them focus monitoring efforts on the most important indicators.**

Questions to ask:
- "Which indicators would provide the earliest warning?"
- "Which indicators are most reliable and least prone to false positives?"
- "Which changes would have the biggest impact on your organization?"
- "Which indicators are easiest to monitor with your current capabilities?"

**Prioritization criteria:**
- **Warning time:** How much advance notice does it provide?
- **Reliability:** How confident can you be when you detect it?
- **Impact:** How consequential is the change it signals?
- **Detectability:** How feasible is it to monitor?
- **Uniqueness:** How specifically does it indicate this change vs. others?

Create tiers:
- **Tier 1 (Critical):** Monitor continuously, high impact, high confidence
- **Tier 2 (Important):** Monitor regularly, moderate impact or confidence
- **Tier 3 (Interesting):** Monitor opportunistically, lower priority

### Step 6: Define Thresholds and Response

**Guide them to establish decision points.**

Questions to ask:
- "How much evidence of this indicator constitutes a real signal vs. noise?"
- "What's your threshold for believing this change is actually happening?"
- "What action should you take if you detect this indicator?"
- "Who needs to be notified?"
- "Should you adjust your defensive posture?"

**Threshold questions:**
- "Do you need to see this indicator once, or multiple times?"
- "Do you need corroboration from multiple indicator types?"
- "What's the difference between an isolated observation and a trend?"

**Response planning:**
- **Reporting:** Who gets notified, how urgently?
- **Analysis:** What follow-on analysis is needed?
- **Defense:** What defensive measures should activate?
- **Collection:** What additional intelligence should you gather?

### Step 7: Review and Update

**Help them plan for periodic review.**

Questions to ask:
- "How often should you review and update your indicators?"
- "What would cause you to add new indicators or retire old ones?"
- "How will you share lessons learned from indicator monitoring?"

**Review triggers:**
- Periodic schedule (monthly, quarterly)
- After major events (public attribution, incidents)
- When assumptions change
- When new intelligence emerges

## Documentation Template

Help the analyst capture:

**Indicator Matrix:**
```
Scenario: [Potential change]

Indicator | Data Source | Monitoring Frequency | Threshold | Response
----------|-------------|---------------------|-----------|----------
[Specific observable event] | [Where to look] | [How often] | [What triggers action] | [What to do]
```

**Example:**
```
Scenario: APT29 expands targeting to energy sector

Indicator | Data Source | Monitoring Frequency | Threshold | Response
----------|-------------|---------------------|-----------|----------
Reconnaissance scanning of energy companies | Network sensors, threat intel feeds | Daily | 3+ confirmed scans from known APT29 infrastructure | Alert CISO, enhance monitoring of energy partners
Malware samples from energy sector with APT29 signatures | Malware analysis, sharing communities | Continuous | 1 confirmed sample | Initiate deep-dive analysis, notify energy sector
Open-source reporting of energy targeting by Russian APT | OSINT monitoring, vendor reports | Daily | 2+ independent credible reports | Validate against internal data, update threat model
```

## Common Pitfalls to Watch For

- **Vague indicators**: "Increased activity" instead of specific measurable events
- **Unfalsifiable indicators**: Can't prove they didn't occur
- **Unobservable indicators**: Indicators you have no way to detect
- **Too many indicators**: Overwhelming monitoring burden
- **Single-source indicators**: No corroboration or validation
- **Ignoring false positives**: Not accounting for noise in the signal
- **Static indicators**: Not updating as threat evolves
- **No response plan**: Detecting indicators but not knowing what to do

## Adaptation Notes

**For strategic warning:** Focus on high-level strategic shifts, longer timeframes, contextual indicators.

**For tactical warning:** Focus on immediate threats, technical indicators, short timeframes.

**For threat actor tracking:** Monitor for operational pattern changes, capability development, targeting shifts.

**For campaign monitoring:** Track indicators of campaign expansion, escalation, or termination.

**For defensive planning:** Identify indicators that trigger specific defensive measures or incident response.

**For validation:** Use indicators to test whether your current assessment remains valid over time.

## Combination with Other Techniques

Indicators/Signposts works well with:
- **ACH**: Develop indicators that would validate or invalidate competing hypotheses
- **Key Assumptions Check**: Create indicators for when key assumptions might be failing
- **Scenarios Analysis**: Build indicator sets for different future scenarios
- **What If? Analysis**: Identify indicators for the alternative outcomes you're exploring
