# Quality of Information Check for Cyber Threat Intelligence

## Overview

Quality of Information Check systematically evaluates the reliability, credibility, and relevance of information sources. In CTI, where intelligence may come from diverse sources (sensors, OSINT, industry reports, internal telemetry), understanding source quality is critical to avoiding analytic errors.

**Best used for:** Evaluating malware samples, assessing industry reports, validating OSINT, examining sensor data, questioning third-party intelligence.

## Guided Process

### Step 1: Inventory Information Sources

**Guide the analyst to list all information sources contributing to their analysis.**

Questions to ask:
- "What sources of information are you using for this analysis?"
- "Where did each piece of evidence come from?"
- "Are you using information from multiple independent sources, or could they be related/correlated?"

**CTI source types:**
- **Internal telemetry** (EDR, SIEM, network sensors, email security, proxy logs)
- **Malware samples** (live capture, sandbox, third-party sharing)
- **OSINT** (social media, public reports, pastebins, code repositories)
- **Industry reporting** (vendor reports, ISACs, sharing communities)
- **Third-party intelligence** (commercial feeds, government bulletins)
- **Human sources** (incident responders, insiders, partner notifications)

### Step 2: Evaluate Source Reliability

**For each source, guide the analyst to assess how trustworthy the source is.**

Questions to ask for each source:
- "How reliable has this source been in the past?"
- "What is this source's track record for accuracy?"
- "Does this source have any biases, motivations, or limitations we should consider?"
- "Could this source have been manipulated or compromised?"
- "Is this source corroborated by other independent sources?"

**Reliability scale:**
- **A - Completely reliable:** Proven track record, direct observation, trusted telemetry
- **B - Usually reliable:** Generally accurate, minor errors possible
- **C - Fairly reliable:** Correct more often than not, but significant errors occur
- **D - Not usually reliable:** Frequently wrong, unverified, or biased
- **E - Unreliable:** Known to be wrong, compromised, or fabricated
- **F - Cannot judge:** New source or insufficient history

**CTI-specific reliability considerations:**

*Internal telemetry:*
- "Are our sensors properly configured and up to date?"
- "Could there be blind spots in our collection?"
- "Has this data been verified or could it be from testing/authorized activity?"

*OSINT sources:*
- "Is this a known credible researcher or a random account?"
- "Could this be misinformation or disinformation?"
- "Has the source made verifiable claims in the past?"

*Industry reports:*
- "What is the vendor's reputation and methodology?"
- "Do they have commercial incentives that could bias their findings?"
- "Do they show their work or just make claims?"

*Malware samples:*
- "Was this captured in the wild or obtained from sharing?"
- "Could the sample have been modified or be a false submission?"
- "Is the provenance chain documented?"

### Step 3: Evaluate Information Credibility

**For each piece of information, assess how believable the specific claim is.**

Questions to ask:
- "Does this information make sense in context?"
- "Is it consistent with what we know from other sources?"
- "Is the information plausible given the threat actor's capabilities?"
- "Could this information be deceptive, manipulated, or a false flag?"
- "How direct is this information? Is it firsthand observation or analysis based on other data?"

**Credibility scale:**
- **1 - Confirmed:** Verified by multiple independent sources or direct observation
- **2 - Probably true:** Consistent with other information, logical
- **3 - Possibly true:** Plausible but uncorroborated
- **4 - Doubtful:** Contradicts other information or implausible
- **5 - Improbable:** Almost certainly false or disinformation
- **6 - Cannot judge:** Insufficient information to evaluate

**CTI-specific credibility considerations:**

*Technical indicators:*
- "Could these indicators be false positives (legitimate software, testing)?"
- "Are these indicators common/generic or specific to this actor?"
- "Could these be planted to mislead?"

*Attribution claims:*
- "Is the attribution based on strong or weak evidence?"
- "Are we seeing unique TTPs or commodity techniques anyone could use?"
- "Could this be deliberate misdirection or a false flag?"

*Timing and context:*
- "Does the timeline make sense?"
- "Are events correlated or causally related?"
- "Could coincidence explain the pattern?"

### Step 4: Identify Critical Information Gaps

**Guide the analyst to recognize what's missing.**

Questions to ask:
- "What information are you lacking that would strengthen your analysis?"
- "What alternative explanations exist that you can't rule out due to missing information?"
- "Are there key questions that remain unanswered?"
- "What would be the most valuable piece of information to obtain?"

**Common gaps in CTI:**
- Missing historical context or previous actor behavior
- Incomplete timeline (early stages of attack, parallel activity)
- Lack of corroboration between different source types
- Unknown victim perspective or impact
- Missing technical details (full malware functionality, exfiltrated data)

### Step 5: Assess Overall Information Quality

**Help the analyst evaluate the total body of information.**

Questions to ask:
- "Looking at all your sources and information together, how strong is your evidential base?"
- "Do you have multiple independent sources confirming key judgments?"
- "Are there contradictions in your information that need to be resolved?"
- "What is the weakest link in your information chain?"
- "If your least reliable source turned out to be wrong, how would that affect your conclusion?"

**Information quality indicators:**
- **Strong:** Multiple independent reliable sources, high credibility, few gaps
- **Moderate:** Mix of source reliability, some corroboration, notable gaps
- **Weak:** Single source, low reliability or credibility, significant gaps

### Step 6: Adjust Confidence and Communicate Uncertainty

**Guide them to calibrate their confidence based on information quality.**

Questions to ask:
- "Given the quality of your information, what's your confidence in your conclusion? (High/Moderate/Low)"
- "How should you communicate the limitations of your sources?"
- "What caveats or qualifiers should accompany your assessment?"
- "If you're making recommendations based on this analysis, how does information quality affect those recommendations?"

**Confidence levels in CTI:**
- **High confidence:** Multiple reliable sources, corroborated technical evidence, fits established patterns
- **Moderate confidence:** Mix of source quality, some gaps, logical but not fully confirmed
- **Low confidence:** Limited sources, significant gaps, plausible but speculative

### Step 7: Document Quality Assessment

**Help them create a transparent record.**

Questions to ask:
- "How will you document which sources contributed to which conclusions?"
- "Should you note source limitations in your reporting?"
- "How will you flag information that still needs verification?"

## Documentation Template

Help the analyst capture:
- **Source Inventory** (list of all sources with type and description)
- **Source Reliability Assessment** (A-F rating with justification)
- **Information Credibility Assessment** (1-6 rating with justification)
- **Source/Information Matrix** (which sources support which findings)
- **Critical Gaps** (what information is missing)
- **Overall Quality Assessment** (strength of evidential base)
- **Confidence Level** (based on information quality)
- **Caveats** (limitations to communicate)

## Example Source/Information Matrix

```
Finding: APT29 attribution

Source               | Reliability | Info Credibility | Contribution
---------------------|-------------|------------------|----------------------------------
EDR telemetry        | A           | 1 - Confirmed    | TTPs match known APT29 patterns
3rd party report     | B           | 2 - Probable     | Claims similar targeting
OSINT researcher     | C           | 3 - Possible     | Identified overlapping infra
Malware sample       | A           | 1 - Confirmed    | Code reuse from previous APT29
Industry rumor       | D           | 4 - Doubtful     | Contradicts other evidence
```

## Common Pitfalls to Watch For

- **Uncritical acceptance**: Treating all information as equally valid
- **Source conflation**: Not realizing multiple "sources" are actually the same information repackaged
- **Confirmation bias**: Accepting low-quality information that supports preferred hypothesis
- **Ignoring absence**: Not noting what evidence is missing that you would expect to see
- **Circular reporting**: Citing sources that are citing each other (echo chamber)
- **Recency bias**: Overweighting the most recent information
- **Authority bias**: Accepting information uncritically because it comes from a prestigious source

## Adaptation Notes

**For tactical/rapid analysis:** Quick reliability check of top 2-3 sources only.

**For strategic/high-stakes analysis:** Full systematic evaluation of all sources, document methodology.

**For malware analysis:** Focus on sample provenance and technical validation.

**For attribution:** Emphasize independence of sources and potential for deception.

**For influence operations:** Critical evaluation of OSINT sources and narrative analysis.

**As a quality gate:** Use before finalizing any major intelligence product to ensure analytic rigor.
