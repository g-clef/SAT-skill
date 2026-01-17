# Key Assumptions Check for Cyber Threat Intelligence

## Overview

Key Assumptions Check systematically identifies and evaluates the foundational assumptions underlying an analysis. It's particularly valuable in CTI where analysts often make implicit assumptions about threat actor capabilities, motivations, or technical details.

**Best used for:** Validating attribution reasoning, challenging malware clustering logic, questioning threat actor capability assessments, examining collection biases.

## Guided Process

### Step 1: Articulate the Current Analytic Line

**Help the analyst clearly state their current conclusion or working hypothesis.**

Questions to ask:
- "What's your current assessment or conclusion about this threat?"
- "In one sentence, what do you believe is happening and why?"
- "What are the key judgments you're making?"

**CTI Examples:**
- "We assess with moderate confidence that APT29 is responsible for this campaign targeting defense contractors."
- "This malware sample belongs to the FIN7 threat group's toolkit."
- "The infrastructure observed is consistent with a command-and-control network for banking trojans."

### Step 2: Identify Underlying Assumptions

**Guide them to surface the implicit and explicit assumptions supporting their conclusion.**

Questions to ask:
- "What are you taking for granted to reach this conclusion?"
- "What would have to be true for your assessment to be correct?"
- "What facts or patterns are you assuming will continue or remain true?"
- "What assumptions are you making about the threat actor's capabilities, resources, or motivations?"
- "What assumptions are you making about your data or collection methods?"

**Types of assumptions in CTI:**

**Technical assumptions:**
- "The malware compilation timestamp is accurate and not manipulated"
- "Similar code means shared authorship"
- "The observed C2 infrastructure is actively controlled by the threat actor"
- "The TTPs we're seeing represent the actor's preferred methods, not just what we can detect"

**Behavioral assumptions:**
- "The threat actor will continue using the same tools and techniques"
- "The targeting pattern reflects strategic objectives"
- "Operational security practices are consistent across campaigns"
- "The actor's capabilities haven't changed since our last observation"

**Attribution assumptions:**
- "Language artifacts in malware are intentional and not false flags"
- "Infrastructure hosting choices reflect the actor's home country"
- "Timing of operations aligns with threat actor's timezone"
- "Similar techniques indicate the same threat actor"

**Collection assumptions:**
- "Our detection methods capture most relevant activity"
- "Absence of evidence equals evidence of absence"
- "Our visibility is representative of the full picture"
- "Sources are reliable and unbiased"

**Contextual assumptions:**
- "Geopolitical relationships drive cyber operations"
- "The actor's past behavior predicts future behavior"
- "Industry reporting about this actor is accurate"

**Aim for 8-15 key assumptions.** More than 20 becomes unwieldy.

### Step 3: Evaluate Each Assumption

**For each assumption, guide the analyst to evaluate its strength.**

Questions to ask for each assumption:
- "How confident are you that this assumption is valid? (High/Medium/Low)"
- "What evidence supports this assumption?"
- "What could challenge or invalidate this assumption?"
- "How consequential would it be if this assumption were wrong?"
- "Have you checked this assumption, or are you accepting it based on convention/past practice?"

**Evaluation criteria:**
- **Confidence:** How certain are we this is true?
- **Impact:** If wrong, how much does it change our conclusion?
- **Checkability:** Can we verify this assumption?
- **Stability:** Is this likely to remain true over time?

**Impact × Confidence Matrix:**
Guide them to categorize assumptions:
- **High Impact + Low Confidence** = Critical vulnerability (most important to address)
- **High Impact + High Confidence** = Foundational but should still be monitored
- **Low Impact + Low Confidence** = Can likely accept the uncertainty
- **Low Impact + High Confidence** = Solid foundation

### Step 4: Challenge Key Assumptions

**Focus on high-impact or low-confidence assumptions. Guide the analyst to question them.**

Questions to ask:
- "What's the alternative? If this assumption is wrong, what would that mean?"
- "Is there any evidence that contradicts this assumption?"
- "Could this assumption be a result of confirmation bias or availability bias?"
- "What would a red team or devil's advocate say about this assumption?"
- "Are we assuming this because it's convenient or because we've verified it?"

**Specific challenges for CTI:**
- "Are we assuming similar TTPs means same actor, when it could be tool sharing, mimicry, or coincidence?"
- "Are we assuming technical sophistication when the actor might be using publicly available tools?"
- "Are we assuming rational behavior when the actor might have different objectives than we think?"
- "Are we assuming our timeline is complete when we might be missing earlier or parallel activity?"

### Step 5: Refine Assumptions or Conclusions

**Based on the challenges, guide the analyst to make adjustments.**

Questions to ask:
- "Do any of these assumptions need to be revised based on our examination?"
- "Does questioning these assumptions change your confidence in your overall conclusion?"
- "Should your conclusion be modified, or its confidence level adjusted?"
- "Which assumptions should you try to verify or gather more information about?"
- "Are there any alternative explanations that become more plausible when you relax certain assumptions?"

### Step 6: Document and Monitor

**Help them create an actionable output.**

Questions to ask:
- "Which assumptions are most critical to track going forward?"
- "What would indicate one of these key assumptions is failing?"
- "What information could you collect to validate or challenge these assumptions?"
- "How should you communicate the dependency of your conclusion on these assumptions?"

## Documentation Template

Help the analyst capture:
- **Current Assessment** (the conclusion or judgment being examined)
- **List of Assumptions** (categorized by type: technical, behavioral, attribution, collection, contextual)
- **Assumption Evaluation** (confidence level, impact if wrong, evidence for/against)
- **Critical Vulnerabilities** (high-impact, low-confidence assumptions)
- **Recommendations** (which assumptions to verify, how to strengthen the analysis)
- **Monitoring Plan** (what would signal assumption failure)

## Common Pitfalls to Watch For

- **Hidden assumptions**: Not surfacing the most fundamental assumptions because they seem "obvious"
- **Accepting assumptions uncritically**: Not questioning assumptions that have become standard in the community
- **Circular reasoning**: Using the conclusion to support the assumptions that support the conclusion
- **Overconfidence**: Marking all assumptions as "high confidence" without genuine evaluation
- **Analysis paralysis**: Getting stuck trying to verify every minor assumption
- **Ignoring collection bias**: Not examining assumptions about data completeness or representativeness

## Adaptation Notes

**For rapid analysis:** Focus only on 3-5 most critical assumptions and do quick confidence checks.

**For strategic assessments:** Full assumption inventory with formal evaluation and validation planning.

**For malware analysis:** Focus on technical assumptions (compilation artifacts, code similarity, infrastructure attribution).

**For campaign attribution:** Focus on behavioral and contextual assumptions about threat actor patterns.

**As a team exercise:** Have different analysts identify assumptions independently, then compare lists to find blind spots.
