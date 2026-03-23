# What If? Analysis for Cyber Threat Intelligence

## Overview

What If? Analysis explores the implications of alternative scenarios, potential surprises, or changes in key variables. It challenges analysts to think beyond the most likely outcome and consider "what could happen" rather than just "what will happen." This helps prepare for unexpected developments and test the robustness of plans.

**Best used for:** Exploring alternative threat scenarios, testing incident response plans, anticipating surprise developments, challenging planning assumptions, examining consequences of different outcomes.

## Guided Process

### Step 1: Identify the Key Variable or Assumption to Challenge

**Guide the analyst to select what they want to vary or challenge.**

Questions to ask:
- "What's the key assumption underlying your current analysis or planning?"
- "What factor would most change the threat landscape if it were different?"
- "What development would most surprise you if it occurred?"
- "What variable are you taking for granted that could change?"

**CTI examples of variables to challenge:**

*Threat actor behavior:*
- "What if APT29 shifted from espionage to destructive attacks?"
- "What if this financially-motivated group started conducting espionage?"
- "What if the threat actor changed TTPs to evade our detection?"

*Attribution assumptions:*
- "What if the actor we attributed this to is actually a false flag?"
- "What if multiple unrelated actors are operating in parallel?"
- "What if this is an insider threat, not an external actor?"

*Capability assumptions:*
- "What if the threat actor acquired zero-day capabilities?"
- "What if they lost access to their current infrastructure?"
- "What if they significantly improved their operational security?"

*Targeting assumptions:*
- "What if they expanded targeting to critical infrastructure?"
- "What if they started targeting supply chain partners?"
- "What if they shifted focus to a different geographic region?"

*Context and environment:*
- "What if there's a major geopolitical shift affecting this actor's sponsor?"
- "What if law enforcement disrupts their infrastructure?"
- "What if their tools and TTPs are leaked publicly?"
- "What if detection vendors widely deploy signatures for their malware?"

### Step 2: Construct the Alternative Scenario

**Help them build out the "what if" scenario in detail.**

Questions to ask:
- "If [this variable] changed, what specifically would be different?"
- "Walk through how this scenario would unfold. What happens first, then what?"
- "What would trigger this alternative scenario?"
- "How plausible is this scenario? Low, moderate, or high probability?"

**Scenario development:**
- Make it specific and concrete, not vague
- Include the triggering event or condition
- Think through the logical sequence
- Consider timeline and phases
- Assign rough probability (just to calibrate thinking)

**Example scenario construction:**

*Baseline:* "APT29 conducts espionage using stealthy TTPs and targets defense contractors."

*What If:* "What if APT29 shifted to destructive attacks on critical infrastructure?"

*Scenario:*
- "Trigger: Geopolitical crisis escalates tensions, sponsor government authorizes destructive cyber operations."
- "Phase 1: APT29 begins reconnaissance against energy and telecommunications."
- "Phase 2: They develop or acquire destructive payloads beyond their current exfiltration-focused tools."
- "Phase 3: They pre-position access in critical infrastructure networks."
- "Phase 4: They execute destructive attacks timed to geopolitical events."
- "Probability: Low-to-moderate, depends on geopolitical trajectory."

### Step 3: Identify Implications and Consequences

**Guide them to think through the consequences of this alternative scenario.**

Questions to ask:
- "If this scenario occurred, what would be the immediate consequences?"
- "How would this affect your organization, your mission, your defenses?"
- "What second-order effects would follow?"
- "Who would be affected beyond the obvious targets?"
- "What would be the strategic implications?"

**CTI consequence categories:**

*Detection and visibility:*
- "Would our current sensors and analytics detect this?"
- "Would our threat hunting methods find it?"
- "What new indicators would we need to look for?"

*Defense and response:*
- "Would our current defenses stop this?"
- "How would our incident response plan need to change?"
- "What new capabilities would we need?"

*Intelligence and analysis:*
- "How would this change our threat model?"
- "What assumptions would we need to revise?"
- "What new intelligence requirements would emerge?"

*Organizational impact:*
- "How would this affect operations, reputation, finances?"
- "Who in the organization would be most impacted?"
- "What would be the worst-case outcome?"

*Strategic implications:*
- "How would this change the broader threat landscape?"
- "Would this trigger a wider conflict or retaliation?"
- "What precedent would this set?"

### Step 4: Assess Current Preparedness

**Help them evaluate whether they're ready for this scenario.**

Questions to ask:
- "If this scenario happened tomorrow, how prepared are you?"
- "What gaps exist in your detection, prevention, or response?"
- "What would go wrong if you tried to respond with current capabilities?"
- "Where are you vulnerable?"

**Preparedness evaluation:**

*Detection:*
- "Would we see it coming? Would we detect it in progress?"
- "What's our detection latency for this type of activity?"

*Prevention:*
- "What controls would prevent or limit this scenario?"
- "What's our weakest link?"

*Response:*
- "Do we have a response plan for this? Is it tested?"
- "Do we have the right people, tools, and procedures?"

*Recovery:*
- "Could we recover from this? How long would it take?"
- "What's our resilience and redundancy?"

### Step 5: Identify Early Warning Indicators

**Guide them to determine what would signal this scenario is developing.**

Questions to ask:
- "What signs would appear if this scenario were beginning to unfold?"
- "What could you monitor that would provide early warning?"
- "Are these indicators something you're currently watching?"

**Link to Indicators/Signposts technique:**
This is where What If? Analysis naturally connects to Indicators or Signposts of Change. For each scenario, develop specific indicators (see indicators.md reference).

**Example early warnings:**
- For capability change: "New malware samples with destructive capabilities"
- For targeting change: "Reconnaissance activity against new sectors"
- For operational change: "Changes in infrastructure or TTPs"
- For strategic change: "Contextual indicators like policy shifts or geopolitical events"

### Step 6: Consider Response Options

**Help them think through how they would respond if this scenario occurred.**

Questions to ask:
- "What actions would you take if you detected this scenario developing?"
- "What decisions would leadership need to make?"
- "What resources would you need that you don't currently have?"
- "What partnerships or external support would be valuable?"

**Response considerations:**

*Immediate actions:*
- Enhanced monitoring and detection
- Defensive hardening
- Stakeholder notification
- Collection against new indicators

*Strategic responses:*
- Update threat model and priorities
- Adjust resource allocation
- Modify defensive architecture
- Develop new capabilities

*External coordination:*
- Information sharing with partners
- Coordination with authorities
- Vendor engagement
- Policy or legal considerations

### Step 7: Extract Insights and Recommendations

**Guide them to translate the scenario exploration into actionable insights.**

Questions to ask:
- "What did this exercise teach you about your current analysis or posture?"
- "Should you adjust your assessments, plans, or defenses based on this scenario?"
- "Even if this scenario is unlikely, are there preparations worth making?"
- "What's the 'no-regrets' investment - actions that help regardless of which scenario unfolds?"

**Insights often emerge:**
- Vulnerabilities we didn't know we had
- Assumptions we should challenge or monitor
- Defensive gaps that need addressing
- Collection requirements we're missing
- Planning assumptions that need revision

### Step 8: Document and Communicate

**Help them create a useful output.**

Questions to ask:
- "Who should know about this alternative scenario?"
- "Should this inform planning, threat modeling, or risk assessments?"
- "How do you want to present this - as a planning exercise, risk analysis, or alternative assessment?"

## Documentation Template

Help the analyst capture:

**Scenario Definition:**
- **Variable/Assumption Challenged:** [What you're changing]
- **Baseline:** [Current state/understanding]
- **Alternative Scenario:** [What if this changed?]
- **Trigger:** [What would cause this]
- **Probability:** [Rough likelihood estimate]

**Scenario Description:**
- Detailed walkthrough of how it would unfold
- Timeline and phases
- Key developments

**Implications:**
- Immediate consequences
- Second-order effects
- Strategic implications
- Organizational impacts

**Preparedness Assessment:**
- Detection capabilities
- Prevention capabilities
- Response capabilities
- Recovery capabilities
- Key gaps

**Early Warning Indicators:**
- Observable signs this is developing
- Monitoring approach
- Thresholds for action

**Response Options:**
- Immediate actions
- Strategic responses
- Resource requirements
- External coordination needs

**Recommendations:**
- Adjustments to current plans/posture
- New capabilities to develop
- Monitoring requirements
- No-regrets actions

## Common Pitfalls to Watch For

- **Implausible scenarios**: Going so far outside the possible that it's not useful
- **Analysis paralysis**: Exploring too many scenarios and becoming overwhelmed
- **Confirmation bias**: Only exploring scenarios that validate current plans
- **Vague scenarios**: Not making the scenario specific enough to analyze meaningfully
- **Ignoring low-probability/high-impact**: Dismissing important scenarios because they're unlikely
- **No action**: Doing the analysis but not adjusting plans or defenses
- **Single scenario**: Only considering one alternative instead of multiple possibilities

## Adaptation Notes

**For red teaming:** Explore worst-case scenarios from adversary perspective.

**For planning:** Develop scenarios for resource allocation and capability investment decisions.

**For risk assessment:** Quantify impact and likelihood of different scenarios.

**For incident response:** Pre-play different attack scenarios to test response plans.

**For threat modeling:** Explore how different threat actor behaviors would affect your environment.

**As stress test:** Challenge the robustness of your current analysis and assumptions.

## Combination with Other Techniques

What If? Analysis works well with:
- **Indicators/Signposts**: Develop early warning for each scenario
- **Key Assumptions Check**: Use scenarios to stress-test critical assumptions
- **Devil's Advocacy**: Explore scenarios where your current assessment is wrong
- **ACH**: Scenarios can help generate alternative hypotheses
- **High Impact/Low Probability**: Dedicated technique for unlikely but consequential scenarios
