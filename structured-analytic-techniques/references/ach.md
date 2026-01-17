# Analysis of Competing Hypotheses (ACH) for Cyber Threat Intelligence

## Overview

ACH is a systematic method for evaluating multiple competing explanations for observed cyber threat activity. It helps analysts avoid confirmation bias by forcing equal consideration of alternative hypotheses.

**Best used for:** Attribution decisions, malware clustering, identifying threat actor motivations, determining attack objectives.

## Guided Process

### Step 1: Identify Competing Hypotheses

**Guide the analyst to brainstorm all plausible explanations.**

Questions to ask:
- "What are all the possible explanations for what you're observing? Don't filter yet - include even unlikely ones."
- "Who could be behind this? What groups have the capability?"
- "What could their motivations be? Consider: espionage, financial gain, disruption, testing, hacktivism, etc."
- "Could this be a false flag? Could it be multiple actors?"
- "Are there any non-malicious explanations?" (misconfiguration, legitimate tool, research activity)

**Aim for 4-7 hypotheses.** Too few limits consideration; too many becomes unwieldy.

**CTI Examples:**
- H1: APT29 conducting espionage campaign
- H2: APT28 false flag operation
- H3: Cybercriminal group testing new ransomware
- H4: Unknown actor using commodity tools
- H5: Penetration testing by authorized third party

### Step 2: Identify Evidence and Indicators

**Guide them to list all available evidence, not just what supports their favored hypothesis.**

Questions to ask:
- "What technical indicators do you have?" (malware signatures, TTPs, infrastructure)
- "What behavioral patterns have you observed?" (targeting, timing, operational security)
- "What contextual information is relevant?" (geopolitical events, victim profile, historical patterns)
- "What's the quality of each piece of evidence?" (confirmed, probable, possible, speculative)
- "What evidence is absent that you would expect to see?"

**Evidence categories for CTI:**
- Malware characteristics (tooling, compilation timestamps, language artifacts, code reuse)
- Infrastructure (IP/domain patterns, hosting choices, operational security)
- TTPs (techniques, persistence methods, exfiltration patterns)
- Targeting (victim industries, geographies, profiles)
- Timing (coordination with events, operational tempo)
- Language/cultural artifacts (timezone, language settings, errors)
- Historical patterns (past campaigns, known actor behaviors)

### Step 3: Create the Matrix

**Help them build a matrix: Hypotheses as columns, Evidence as rows.**

"Let's create a table. Each hypothesis gets a column, each piece of evidence gets a row. We'll evaluate how each piece of evidence relates to each hypothesis."

**Evaluation codes:**
- **CC** = Consistent with hypothesis (evidence fits this explanation)
- **II** = Inconsistent with hypothesis (evidence contradicts this explanation)
- **N/A** = Not applicable or neutral (evidence doesn't help evaluate this hypothesis)

Questions for each cell:
- "If [hypothesis X] were true, would we expect to see [evidence Y]?"
- "Does this evidence support, contradict, or neither support nor contradict this hypothesis?"
- "Be careful: just because evidence is consistent doesn't mean it's diagnostic. Does it distinguish between hypotheses?"

### Step 4: Refine the Matrix

**Guide them to look for diagnostic evidence - evidence that discriminates between hypotheses.**

Questions to ask:
- "Which pieces of evidence are consistent with ALL hypotheses?" (These don't help us discriminate)
- "Which pieces of evidence are inconsistent with only ONE hypothesis?" (These are highly diagnostic)
- "Are there any assumptions embedded in how you're evaluating this evidence?"
- "Do you need to collect additional evidence to discriminate between top hypotheses?"

**Look for:**
- Rows that are all CC (not diagnostic - expected under any hypothesis)
- Rows with mixed CC/II (highly diagnostic - discriminates between hypotheses)
- Rows with mostly N/A (may not be relevant to this analysis)

### Step 5: Draw Tentative Conclusions

**Help them analyze the matrix to determine which hypothesis is least inconsistent with the evidence.**

Questions to ask:
- "Count the 'Inconsistent' marks for each hypothesis. Which has the fewest?"
- "The hypothesis with the LEAST evidence against it is the most likely - not the one with the most evidence for it. Does that change your thinking?"
- "Are there any hypotheses you can definitively rule out based on strong inconsistencies?"
- "Among the remaining hypotheses, what's your confidence level? High, moderate, low?"
- "What would it take to increase your confidence or discriminate further?"

### Step 6: Identify Key Uncertainties and Assumptions

**Guide them to examine what would change their conclusion.**

Questions to ask:
- "What assumptions are you making about the quality or interpretation of your evidence?"
- "If one piece of evidence turned out to be wrong or misinterpreted, which would most change your conclusion?"
- "What additional information would be most valuable to collect?"
- "What could cause you to shift to a different hypothesis?"

### Step 7: Report and Monitor

**Help them document their analysis and establish monitoring.**

Questions to ask:
- "How should you present this analysis? What does your audience need to know?"
- "What are your key findings and confidence levels?"
- "What indicators would signal a shift to an alternative hypothesis?"
- "How should this analysis be revisited as new evidence emerges?"

## Documentation Template

Help the analyst capture:
- **Hypotheses considered** (with brief description of each)
- **Evidence evaluated** (with quality/confidence ratings)
- **ACH matrix** (the completed grid)
- **Analysis** (hypothesis with least inconsistencies, confidence level)
- **Key assumptions** (what the conclusion depends on)
- **Intelligence gaps** (what information would improve confidence)
- **Indicators for monitoring** (what would change the assessment)

## Common Pitfalls to Watch For

- **Confirmation bias**: Analyst only looking for evidence supporting their favored hypothesis
- **Anchoring**: First hypothesis dominates thinking
- **Availability bias**: Recent or vivid evidence weighted too heavily
- **Insufficient hypotheses**: Not considering enough alternatives
- **Misidentifying diagnostic evidence**: Treating evidence that's consistent with all hypotheses as if it discriminates
- **Binary thinking**: Forgetting that multiple hypotheses could be partially true (e.g., two groups collaborating)

## Adaptation Notes

**For quick/tactical analysis:** Use simplified 3-hypothesis version with reduced evidence list.

**For strategic/high-stakes analysis:** Expand to 6-8 hypotheses, conduct full evidence collection, involve multiple analysts, revisit periodically.

**For malware clustering:** Hypotheses = candidate threat groups; Evidence = malware characteristics and operational patterns.

**For attribution:** Hypotheses = potential actors/groups; Evidence = full intelligence picture including geopolitical context.
