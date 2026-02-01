# Seva User Guide: From Chat to Investigation

## What Seva Is

Seva is a linguistic detection framework for identifying coercive control patterns. It produces **signals, not verdicts** — evidence packages for human evaluation, not automated judgments.

There are two frameworks:
- **Seva (core):** 9 markers for high-control groups (cults, abusive organizations, toxic subcultures)
- **Seva-FIN:** 10 markers for financial manipulation (crypto scams, MLMs, guru grifts)

This guide shows you how to use Seva at three levels:
1. **Basic:** Paste-in-chat prompts for quick analysis
2. **Intermediate:** Cross-LLM validation for rigorous findings
3. **Advanced:** Claude Code + Python for investigative deep dives

---

## Level 1: Chat-Based Analysis

### The Simplest Workflow

1. Gather source material (transcripts, posts, recordings)
2. Paste the Seva prompt into Claude/ChatGPT/Gemini
3. Paste your source material
4. Read the analysis

**That's it.** For a quick read on whether something is concerning, this is enough.

### The Core Seva Prompt

```
You are analyzing content from a group or individual that has raised concerns 
about potential coercive control dynamics. Your task is to identify linguistic 
and behavioral patterns associated with high-control environments.

IMPORTANT: This is pattern detection, not diagnosis. You are producing an 
evidence package for human evaluation, not rendering a verdict.

## The Nine Markers

Scan the provided content for these patterns:

**M1: Authority Elevation**
- Leader/sponsor positioned as unquestionable authority
- Decisions require approval from authority figure
- Questioning authority = personal failure or spiritual deficiency

**M2: Self-Distrust Normalization**
- "Your best thinking got you here"
- Intelligence framed as liability
- Members taught to distrust their own perceptions

**M3: Outside Help Discouragement**
- Therapy dismissed or stigmatized
- Medication framed as weakness or lack of faith
- "We're the only thing that really works"

**M4: In-Group Superiority**
- This is the only true/real/authentic method
- Outsiders don't understand
- Superiority about commitment level

**M5: Exit Terror**
- Leaving framed as catastrophic (death, relapse, damnation)
- Stories of people who left and suffered
- Departure = betrayal or spiritual death

**M6: Thought-Terminating Clichés**
- Stock phrases that shut down questioning
- "That's your disease/ego talking"
- Loaded language that bypasses critical thinking

**M7: Relationship/Isolation Control**
- Authority figure directs who members can associate with
- Family/friends labeled as "toxic" or "unsupportive"
- Social life managed through group activities

**M8: Financial/Labor Exploitation**
- Pressure to give money or unpaid labor
- Financial decisions require approval
- Shame-based contribution expectations

**M9: Medical/Psychological Interference**
- Authority figure overrides professional medical guidance
- Medication decisions controlled by non-medical leader
- Mental health issues reframed as character defects

## Phase Estimation (0-5)

Based on marker density and intensity, estimate the control level:

- **Phase 0-1:** Healthy group. Low marker presence, autonomy respected.
- **Phase 2:** Boundary testing. Authority elevation begins, subtle self-distrust.
- **Phase 3:** Systematic control. Multiple markers present, architecture visible.
- **Phase 4:** Exit terror active. High density, leaving = catastrophe.
- **Phase 5:** Total control. M7+M8+M9 present, documented harm.

## Output Format

For each marker detected:
1. Quote the specific passage
2. Identify which marker it represents
3. Rate intensity: LOW / MODERATE / HIGH / CRITICAL
4. Note the source (speaker, timestamp, document)

Then provide:
- Overall phase estimate with confidence level
- Summary of most concerning patterns
- Any positive indicators (autonomy language, healthy boundaries)
- Limitations of this analysis

---

CONTENT TO ANALYZE:

[PASTE SOURCE MATERIAL HERE]
```

### The Seva-FIN Prompt (Financial Grift)

```
You are analyzing promotional content from a financial opportunity, investment, 
or business venture. Your task is to identify linguistic patterns associated 
with financial manipulation and potential fraud.

IMPORTANT: High scores indicate risk patterns, not proof of fraud. This is 
due diligence assistance, not legal determination.

## The Ten Markers

**M1: Income Mystification**
- Lifestyle flex without verifiable proof
- "Unlimited earning potential"
- Screenshots of earnings (easily faked)

**M2: Urgency Manufacturing**
- "Limited time," "closing soon," countdown timers
- FOMO-inducing language
- Artificial scarcity

**M3: Authority Fabrication**
- Unverifiable credentials or connections
- Name-dropping without substance
- "As seen on..." without verification

**M4: Exit-Blame Setup**
- Pre-blaming failures on participant effort
- "Only works if you work it"
- "Paper hands" / weak mindset framing

**M5: Thought-Termination**
- "FUD" (fear, uncertainty, doubt) as dismissal
- "Haters gonna hate"
- "DYOR" used to deflect, not inform

**M6: Complexity Shield**
- Jargon to obscure, not explain
- Technical language without substance
- Complexity as credibility theater

**M7: Community Capture**
- "We're family" / identity merger with investment
- Us vs. them framing
- Coordinated harassment of critics

**M8: Reflexive Economics**
- Value depends entirely on new buyers (Ponzi structure)
- Tokenomics that punish selling
- No external value creation

**M9: Charity Hijacking**
- Cause used as marketing cover
- Charity name in project title
- Emotional manipulation via social good

**M10: Celebrity Shield**
- Fame substituted for fundamentals
- "Would [celebrity] really scam?"
- Parasocial trust exploitation

## Scoring

Rate each marker 0-10 based on presence and intensity.
Sum for overall risk score (0-100).

- 0-20: Normal marketing enthusiasm
- 21-40: Yellow flags, proceed with caution
- 41-60: Significant concern, high due diligence needed
- 61-80: Strong grift indicators
- 81-100: Extreme risk, classic scam patterns

## Output

For each marker detected, quote the evidence and rate intensity.
Provide overall score with confidence level.
Note any legitimacy indicators that counterbalance concerns.

---

CONTENT TO ANALYZE:

[PASTE PROMOTIONAL MATERIAL, WHITEPAPER, DISCORD MESSAGES, ETC.]
```

---

## Level 2: Cross-LLM Validation

### Why Use Multiple Models?

Different LLMs have different biases:
- **Claude:** Strong on nuance and ethical reasoning
- **Gemini:** Good at data structuring, handles large contexts
- **DeepSeek:** Strong on statistical/mathematical analysis
- **ChatGPT:** Good general performance, different training data

**Findings that multiple systems confirm are more reliable.**

### The Workflow

```
Step 1: Claude — Initial marker detection
        ↓
Step 2: Gemini — Structure data into analyzable format
        ↓
Step 3: DeepSeek — Statistical validation
        ↓
Step 4: Claude — Synthesize into final report
```

### Gemini Data Structuring Prompt

```
I have transcript data from [X] speakers that I've analyzed for coercive 
control markers. I need you to structure this into a format suitable for 
statistical analysis.

For each speaker, I'll provide:
- Name/identifier
- Group membership (target group vs. control)
- Year of recording
- Quotes flagged for each of 9 markers

Please output:
1. CSV table with columns: Speaker, Group, Year, M1, M2, M3, M4, M5, M6, M7, M8, M9, Total_Negative, Positive_Present
2. Summary statistics for each group
3. Any data quality issues you notice

[PASTE ANALYZED DATA]
```

### DeepSeek Statistical Prompt

```
I have structured data comparing two populations on coercive control markers.

Group A: [Target group], N = [X]
Group B: [Control group], N = [Y]

Please calculate:
1. Cohen's d effect size for total negative markers
2. Mann-Whitney U test for statistical significance
3. Classification accuracy (can we reliably distinguish groups?)
4. Which markers most strongly differentiate the groups?

Present results with:
- Numerical values
- Plain-language interpretation
- Confidence intervals where applicable
- Caveats about sample size

[PASTE CSV DATA]
```

---

## Level 3: Claude Code Investigations

This is where Seva becomes genuinely powerful.

### The NXIVM Case Study

In January 2026, we tested Seva's financial investigation capabilities on NXIVM — a known high-control group with extensive public records.

**What we started with:** The Seva framework and a question: "What could automated analysis have caught before the 2018 arrests?"

**What we found in ~4 hours:**
- 92 corporate entities across 6 jurisdictions
- A $47 million unforfeited asset (Wakaya Island, Fiji)
- The likely hidden asset manager (Alejandro Betancourt)
- 6 financial red flags detectable by 2004 — 14 years before conviction
- Evidence that the asset is actively generating revenue while Raniere serves 120 years

**None of this required special access.** It came from ProPublica nonprofit filings, CourtListener court records, UK Companies House, and public news sources.

### The Methodology: Conversational Steering

The power isn't just in the prompts — it's in how you steer the investigation.

**Starting prompt to Claude Code:**

```
I want to do a retrospective financial analysis of NXIVM to demonstrate 
what automated detection could have caught before the 2018 arrests.

Phase 1: Search ProPublica Nonprofit Explorer for NXIVM-related 990 filings
Phase 2: Search CourtListener for litigation patterns
Phase 3: Build a network graph of entities and officers
Phase 4: Generate a red flag report

Known entity names: [list]
Known individuals: [list]
```

**What Claude Code delivered:**
- SQLite database with all findings
- Network visualization of entity connections
- Red flag analysis with specific anomalies
- Timeline showing when each flag became visible

**Then we started steering:**

> "The nonprofit filings show almost no money. Where did the $150M from the Bronfmans actually go?"

This led to investigating the for-profit entities — which don't file public returns.

> "What about international operations? They had centers in Mexico."

This led to discovering the Wakaya Island purchase structure (Delaware → Singapore → Fiji).

> "Who is the 'A' in ACK? The ownership structure says ACK Knowledge LLC."

This led to identifying Alejandro Betancourt — a Mexican banking family heir who was never charged despite 9 years on NXIVM's Executive Board.

> "Is Wakaya still operating? Was it ever forfeited?"

This revealed that the resort is actively operating at $2,500-$11,000/night, and Raniere's 1/3 stake was **never seized** — Bronfman paid $6M to preserve the entire asset.

### The Pattern: Probe → Discover → Probe Deeper

Each Claude Code prompt generates findings. Those findings raise questions. Those questions become the next prompt.

**Investigation flow:**

```
Initial prompt: "Analyze NXIVM financials"
     ↓
Finding: "Only $220K visible in nonprofit filings"
     ↓
Follow-up: "Where's the rest of the money?"
     ↓
Finding: "Wakaya Island purchase for $47M"
     ↓
Follow-up: "Who owns it? Is it forfeited?"
     ↓
Finding: "ACK = Alex, Clare, Keith. Not forfeited."
     ↓
Follow-up: "Who is Alex? Why wasn't he charged?"
     ↓
Finding: "Betancourt. Mexican banking family. Only unrestricted partner."
     ↓
Follow-up: "Is the resort still operating? Who's managing Raniere's stake?"
     ...
```

### Example Claude Code Prompts

**Financial Entity Discovery:**

```
Search for all corporate entities connected to [ORGANIZATION/PERSON].

Data sources to check:
- ProPublica Nonprofit Explorer (990 filings)
- OpenCorporates (corporate registrations)
- CourtListener (litigation)
- SEC EDGAR (if publicly traded connections)
- UK Companies House (if UK entities)

For each entity found:
- Entity name and type
- Jurisdiction of registration
- Officers/directors
- Related entities
- Any red flags (shared addresses, overlapping officers, etc.)

Build a network graph showing connections.
Output findings to [directory].
```

**Litigation Pattern Analysis:**

```
Search CourtListener and PACER for all cases involving [ORGANIZATION/PERSON].

Document:
- Case name, court, year
- Was subject plaintiff or defendant?
- Who did they sue? (individuals vs. organizations)
- Case type (defamation, IP, breach of contract, etc.)
- Outcome if available

Look for patterns:
- Do they sue former members? Critics? Journalists?
- Is there a litigation spike after negative press?
- Are the same attorneys used repeatedly?

Generate timeline visualization and pattern report.
```

**International Asset Tracing:**

```
[PERSON] may have international assets. Search for:

UK: Companies House filings
Canada: CRA charity data, OpenCorporates
Singapore: ACRA (note: some data requires purchase)
Fiji: (note: land records not digitized)
Mexico: OpenCorporates Mexican registries

Known connections to search:
- [Names of associates]
- Known entity names in any jurisdiction
- Addresses from other filings

Document anything found, including "struck off" or dissolved entities.
Note which jurisdictions have weak disclosure requirements.
```

### The Human-in-the-Loop Advantage

Claude Code can pull data and find connections. It cannot:
- Recognize which findings are genuinely surprising
- Know which threads to pull harder
- Make judgment calls about significance
- Decide when something is "enough"

**You bring:**
- Domain knowledge ("That's the son of a Mexican president")
- Investigative instinct ("Why would they register in Singapore?")
- Ethical judgment ("This is getting into personal territory, let's stop")
- The ability to say "This is the real story"

**The combination is more powerful than either alone.**

---

## Putting It Together

### Quick Analysis (30 minutes)

1. Gather 10-20 pages of source material
2. Paste Seva prompt + material into Claude
3. Read the marker analysis
4. Note phase estimate and key concerns
5. Done

**Use case:** "My sister is in this group, should I be worried?"

### Rigorous Analysis (4-8 hours)

1. Gather comprehensive corpus (50,000+ words)
2. Run initial Seva analysis in Claude
3. Structure data in Gemini
4. Run statistics in DeepSeek
5. Synthesize findings back in Claude
6. Document methodology and limitations

**Use case:** Preparing evidence for a journalist or researcher

### Full Investigation (Days to weeks)

1. Start with Seva linguistic analysis
2. Use Claude Code to pull financial/legal records
3. Build entity network and timeline
4. Follow threads that emerge
5. Cross-reference with public reporting
6. Document everything
7. Package for appropriate audience

**Use case:** The NXIVM investigation, Landmark financials

---

## What Seva Can and Cannot Do

### Seva CAN:

- Identify linguistic patterns associated with coercive control
- Surface financial red flags in public records
- Organize evidence for human review
- Quantify differences between target and control groups
- Build network maps of entity relationships
- Generate reproducible, documented analyses

### Seva CANNOT:

- Prove something is a cult
- Determine legal liability
- Replace professional investigation
- Access private records
- Make definitive diagnoses
- Substitute for survivor testimony

### Ethical Use

- **Groups, not individuals:** Analyze organizations, not private people
- **Substantial corpus:** Don't draw conclusions from thin evidence
- **Verify sources:** Confirm quotes and documents are authentic
- **Present fairly:** Include limitations and alternative interpretations
- **Respect survivors:** Their experiences aren't content for scoring

---

## Getting Started

**Minimum viable start:**
1. Copy the Seva prompt above
2. Paste into Claude with some source material
3. Read what comes back

**If you want to go deeper:**
1. Fork the GitHub repo
2. Run the example notebooks
3. Adapt prompts for your domain
4. Join the community

**If you find something significant:**
- Document your methodology
- Note your limitations
- Consider who should see it (journalist? researcher? advocacy org?)
- Don't publish accusations — publish patterns

---

## Resources

- **Substack:** [link] — Case studies and methodology articles
- **GitHub:** [link] — Prompts, notebooks, example analyses
- **Contact:** [link] — For researchers and journalists

---

*Seva is named from the Sanskrit word for "selfless service." It exists to help people protect themselves and others from manipulation.*
