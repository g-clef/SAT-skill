# The Diamond Model of Intrusion Analysis for Cyber Threat Intelligence

## Overview

The Diamond Model is an analytical framework that describes cyber intrusion events through four core features: Adversary, Capability, Infrastructure, and Victim, connected as vertices of a diamond. It provides a structured way to organize CTI data, identify relationships, pivot to new information, and develop hypotheses about attacks.

**Best used for:** Organizing attack data systematically, identifying intelligence gaps, pivoting to discover new indicators, linking disparate events, developing attribution hypotheses, planning collection strategies.

## Core Concepts

### The Four Vertices

Every intrusion event involves these four elements:

- **Adversary**: The threat actor or group conducting the operation
- **Capability**: The tools, techniques, and tactics used (malware, exploits, TTPs)
- **Infrastructure**: The physical and logical resources used (C2 servers, domains, email accounts)
- **Victim**: The target of the intrusion (organization, person, asset)

### Edge Relationships

The diamond edges represent direct relationships:

- **Adversary ←→ Capability**: The adversary develops, acquires, or deploys capabilities
- **Capability ←→ Infrastructure**: Capabilities are delivered via or controlled through infrastructure
- **Infrastructure ←→ Victim**: Infrastructure connects to or affects the victim
- **Victim ←→ Adversary**: The adversary targets specific victims (often strategic selection)

### The Center: Social-Political Layer

The diamond's center represents the social, political, and organizational context driving the event - the "why" behind the attack.

### Meta-Features

Additional attributes that describe the event:
- **Timestamp**: When the event occurred
- **Phase**: Where in the attack lifecycle (reconnaissance, weaponization, delivery, exploitation, installation, C2, actions on objectives)
- **Result**: Outcome (success, failure, unknown)
- **Direction**: Attacker-to-victim, victim-to-attacker, bidirectional
- **Methodology**: How the event was conducted
- **Resources**: What the adversary used or expended

## Guided Process

### Step 1: Define the Intrusion Event

**Guide the analyst to scope what they're analyzing.**

Questions to ask:
- "What specific intrusion event are you analyzing?"
- "Is this a single discrete action, or are you looking at a campaign with multiple events?"
- "What's the timeframe of this event?"
- "Do you want to create one diamond or multiple diamonds for a campaign?"

**Event definition tips:**
- An "event" should be atomic - a single adversary using a single capability via infrastructure against a victim
- Large campaigns may need multiple diamonds
- Start with what you know, expand from there
- You can link diamonds together for complex operations

**CTI Examples:**
- "Phishing email delivered to finance department on 2024-12-15"
- "Malware beacon from compromised workstation to C2 server on 2024-12-16"
- "Data exfiltration to external FTP site on 2024-12-20"
- "Overall APT29 campaign against our organization (this would be multiple diamonds)"

### Step 2: Populate the Victim Vertex

**Help them document what they know about the victim.**

Questions to ask:
- "Who or what was targeted?"
- "Was it a specific person, department, system, or the entire organization?"
- "What made this victim attractive to the adversary?"
- "What assets or information did the victim have access to?"
- "Were there multiple victims, or was it targeted at one?"

**Victim characteristics to capture:**
- Identity (organization, individual, system)
- Industry/sector
- Geography
- Size/value
- Assets of interest (data, access, credentials)
- Vulnerabilities exploited
- Detection capability
- Relationship to other victims

**CTI victim examples:**
- "Finance department employees with access to wire transfer systems"
- "Windows Server 2019 domain controller"
- "Defense contractor with classified information"
- "CEO and CFO (credential harvesting targets)"

### Step 3: Populate the Capability Vertex

**Guide them to document the tools and techniques used.**

Questions to ask:
- "What malware, exploits, or techniques were used?"
- "What was the capability designed to do?"
- "Is this a known tool/malware family or something new?"
- "What technical details do you have about it?"
- "What phases of the attack lifecycle does this capability support?"

**Capability characteristics to capture:**
- Tool/malware name or hash
- Function (backdoor, RAT, loader, dropper, ransomware, etc.)
- Exploits used (CVEs)
- TTPs (MITRE ATT&CK techniques)
- Technical sophistication
- Customization level (commodity, modified, custom)
- Delivery method
- Persistence mechanisms
- C2 protocols

**CTI capability examples:**
- "Emotet banking trojan (SHA256: abc123...)"
- "Spearphishing attachment with weaponized macro"
- "Cobalt Strike beacon with custom malleable C2 profile"
- "EternalBlue exploit (CVE-2017-0144) + DoublePulsar implant"
- "Custom keylogger with encrypted HTTPS beaconing"

### Step 4: Populate the Infrastructure Vertex

**Help them document the infrastructure used.**

Questions to ask:
- "What infrastructure delivered or controlled this capability?"
- "What C2 servers, domains, or IP addresses were involved?"
- "Is this infrastructure dedicated to this operation or shared?"
- "Do you know who controls or owns this infrastructure?"
- "Is it compromised legitimate infrastructure or adversary-owned?"

**Infrastructure characteristics to capture:**
- IP addresses
- Domains and subdomains
- URLs
- Email addresses
- SSL certificates
- Hosting providers
- Registration details (WHOIS)
- Infrastructure type (dedicated, shared, compromised, legitimate)
- Geographic location
- Operational security practices

**CTI infrastructure examples:**
- "C2 domain: evil-updates[.]com (registered 2024-11-01, NameCheap)"
- "IP: 185.220.101.42 (Hosting: ExampleHosting, Location: Netherlands)"
- "Phishing email sent from: noreply@company-security[.]info"
- "Staging server: hxxps://192.0.2.15/updates/payload.exe"
- "Compromised WordPress site used as watering hole"

### Step 5: Populate the Adversary Vertex

**Guide them to document what they know or hypothesize about the adversary.**

Questions to ask:
- "Who do you believe is behind this attack?"
- "What evidence points to this adversary?"
- "How confident are you in this attribution?"
- "What are the adversary's motivations?"
- "What is their assessed capability level and resourcing?"

**Adversary characteristics to capture:**
- Identity (APT group name, alias, unknown)
- Attribution confidence (confirmed, suspected, unknown)
- Motivation (espionage, financial, disruption, hacktivism)
- Sponsorship (nation-state, criminal, independent)
- Sophistication level
- Known TTPs and patterns
- Targeting preferences
- Historical activity
- Aliases and related groups

**CTI adversary examples:**
- "APT29 (suspected, moderate confidence based on TTP overlap)"
- "Unknown financially-motivated cybercriminal group"
- "FIN7 (confirmed based on unique tool signatures)"
- "Nation-state actor, likely Russian-speaking based on language artifacts"
- "Insider threat (employee terminated 2024-12-10)"

**Important note on unknowns:**
- It's okay to have "Unknown Adversary" - that's often the case early in analysis
- The diamond helps you discover the adversary through the other vertices
- Hypotheses about the adversary should be documented with confidence levels

### Step 6: Add Meta-Features and Context

**Help them enrich the diamond with additional details.**

Questions to ask:
- "When did this event occur? What's the exact timestamp?"
- "What phase of the attack lifecycle was this?"
- "Was this event successful from the adversary's perspective?"
- "What was the direction - attacker to victim, or victim responding?"
- "What methodology or approach did they use?"

**Meta-features to add:**
- **Timestamp**: Precise time of event
- **Phase**: Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command & Control, Actions on Objectives
- **Result**: Success, Failure, Unknown
- **Direction**: Adversary-to-Victim, Victim-to-Adversary, Bidirectional, Unknown
- **Methodology**: How it was conducted (automated, manual, social engineering, technical)
- **Resources**: Time, money, personnel invested

**Social-Political context:**
- "Why did this attack happen?"
- "What geopolitical, economic, or organizational factors drove it?"
- "What was the adversary trying to achieve strategically?"

**CTI context examples:**
- "Timed to coincide with political elections"
- "Financial motivation - ransomware for profit"
- "Espionage aligned with national priorities"
- "Retaliation for previous attribution or sanctions"

### Step 7: Analyze Relationships and Pivot

**Guide them to use the diamond to discover new information.**

Questions to ask:
- "Looking at the relationships between vertices, what don't you know?"
- "Where can you pivot to find more information?"
- "If you have the capability, what infrastructure might it use?"
- "If you know the adversary, what other capabilities do they typically use?"
- "If you know the infrastructure, what other victims might it target?"

**Pivoting strategies:**

*From Capability:*
- "What other infrastructure serves this same malware family?"
- "What other victims have been hit by this same tool?"
- "What adversaries are known to use this capability?"

*From Infrastructure:*
- "What other capabilities have been delivered from this infrastructure?"
- "What other victims has this infrastructure targeted?"
- "Can you find historical WHOIS or passive DNS data?"

*From Victim:*
- "What capabilities were used against similar victims?"
- "What infrastructure commonly targets this sector/geography?"
- "What adversaries typically target this victim profile?"

*From Adversary:*
- "What capabilities does this adversary typically use?"
- "What infrastructure patterns do they follow?"
- "Who else do they typically target?"

**Intelligence gaps:**
- Use the diamond to identify what you DON'T know
- Each unknown edge is a collection requirement
- Prioritize gaps that would enable pivoting or improve confidence

### Step 8: Create Multiple Diamonds for Campaigns

**If analyzing a campaign, help them build multiple related diamonds.**

Questions to ask:
- "What are the distinct events in this campaign?"
- "Should you create separate diamonds for different phases?"
- "How do these events link together?"
- "What patterns emerge when you compare diamonds?"

**Activity threading:**
- Link diamonds through common vertices
- Look for vertex reuse (same infrastructure, capability, or adversary)
- Identify patterns and evolution over time
- Build the campaign narrative

**Pattern analysis across diamonds:**
- "Do you see the same adversary using different capabilities?"
- "Is the same infrastructure being reused?"
- "Are multiple victims being targeted with the same tools?"
- "How are tactics evolving across the campaign?"

### Step 9: Develop and Test Hypotheses

**Help them use the diamond to formulate and validate hypotheses.**

Questions to ask:
- "What hypotheses can you develop from this diamond?"
- "Based on the capability and infrastructure, who might the adversary be?"
- "Based on the adversary and victim, what might the objective be?"
- "What would you expect to see if your hypothesis is correct?"
- "What additional diamonds would support or refute your hypothesis?"

**Hypothesis development:**
- Use known vertices to hypothesize about unknown vertices
- "If the adversary is X, we'd expect capabilities A, B, C"
- "If the objective is espionage, we'd expect exfiltration activity"
- "If this infrastructure serves this malware, other victims likely exist"

**Hypothesis testing:**
- Collect data to confirm or refute hypotheses
- Look for expected patterns in other diamonds
- Pivot to discover supporting or contradictory evidence

### Step 10: Document and Visualize

**Help them create a useful output.**

Questions to ask:
- "How do you want to document this diamond?"
- "Should you create a visual diagram?"
- "What audience will consume this analysis?"
- "How will this diamond inform your next steps?"

**Documentation approaches:**

*Structured format:*
```
Event: [Brief description]
Timestamp: [Date/time]
Phase: [Attack lifecycle phase]

ADVERSARY
- Identity: [Known or suspected]
- Confidence: [High/Moderate/Low]
- Motivation: [Why]
- Details: [Additional characteristics]

CAPABILITY  
- Tool/Malware: [Name, hash, description]
- Function: [What it does]
- TTPs: [MITRE ATT&CK techniques]
- Details: [Technical specifics]

INFRASTRUCTURE
- C2/Delivery: [IPs, domains, URLs]
- Hosting: [Provider, location]
- Type: [Dedicated/compromised/shared]
- Details: [Registration, certificates, etc.]

VICTIM
- Identity: [Who/what was targeted]
- Sector: [Industry]
- Assets: [What they have of interest]
- Details: [Why targeted]

Social-Political Context:
[Strategic drivers and motivation]

Intelligence Gaps:
[What's unknown or uncertain]

Pivot Opportunities:
[Where to collect additional data]
```

*Visual diagram:*
- Draw the diamond with vertices labeled
- Show confidence levels with different line styles or colors
- Connect multiple diamonds for campaigns
- Use arrows to show relationships and data flow

## Use Cases in CTI

### 1. Organizing Raw Intelligence

**Scenario:** You have scattered indicators and observations from an incident.

**Approach:**
- Create a diamond for each discrete event
- Populate what you know
- Identify gaps systematically
- Use gaps to guide investigation

### 2. Threat Attribution

**Scenario:** You want to determine who conducted an attack.

**Approach:**
- Populate Capability, Infrastructure, and Victim vertices
- Use patterns to hypothesize about Adversary
- Pivot to find supporting evidence
- Compare against known adversary profiles
- Document confidence level

### 3. Campaign Analysis

**Scenario:** Multiple related events over time.

**Approach:**
- Create diamond for each event
- Identify common vertices (activity threading)
- Analyze evolution and patterns
- Build campaign timeline and narrative

### 4. Intelligence Gaps Analysis

**Scenario:** Understanding what you don't know.

**Approach:**
- Populate known vertices
- Identify empty or uncertain vertices
- Prioritize collection based on analytic value
- Use diamond edges to guide pivoting

### 5. Defensive Planning

**Scenario:** Preparing defenses against known adversaries.

**Approach:**
- Build diamonds for adversary's historical activity
- Identify their capability and infrastructure patterns
- Determine likely future victim profiles
- Develop detection and prevention strategies

### 6. Integration with Other Techniques

**With ACH:**
- Each hypothesis about attribution is a different adversary vertex
- Use capability, infrastructure, and victim to evaluate which adversary fits best

**With Key Assumptions Check:**
- Examine assumptions about each vertex
- "Are we assuming this infrastructure indicates that adversary?"
- "Are we assuming this capability means this intent?"

**With Indicators/Signposts:**
- Develop indicators for changes in adversary, capability, or infrastructure patterns
- Monitor for evolution across campaign diamonds

## Common Pitfalls to Watch For

- **Incomplete diamonds**: Not populating all four vertices with available information
- **Over-attribution**: Claiming adversary identity with low confidence
- **Single diamond thinking**: Not creating multiple diamonds for complex campaigns
- **Ignoring unknowns**: Not documenting what's missing or uncertain
- **Static analysis**: Not using the diamond to pivot and discover new information
- **Mixing events**: Combining multiple distinct events into one diamond
- **Missing context**: Not considering the social-political layer
- **No follow-through**: Building diamonds but not using them to guide action

## Adaptation Notes

**For incident response:** Rapid diamond creation during active investigation to organize findings and identify gaps.

**For threat intelligence:** Detailed diamonds with extensive pivoting for comprehensive adversary profiles.

**For reporting:** Visual diamonds to communicate complex intrusion activity to stakeholders.

**For hunting:** Use diamonds of known adversary activity to develop hunting hypotheses.

**For malware analysis:** Focus on capability vertex with deep technical details, use to pivot to infrastructure and adversary.

## References and Further Learning

The Diamond Model was developed by Sergio Caltagirone, Andrew Pendergast, and Christopher Betz. The original paper provides extensive detail on the framework's theoretical foundations and applications.

Key concepts:
- **Activity threads**: Linking diamonds through shared vertices
- **Activity groups**: Clusters of related diamonds
- **Confidence levels**: Documenting certainty about each vertex
- **Bidirectional analysis**: Using any vertex to discover others
