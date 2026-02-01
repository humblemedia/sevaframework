# Seva

**Linguistic detection framework for coercive control patterns.**

Seva produces **signals, not verdicts** — evidence packages for human evaluation, not automated judgments.

---

## What It Does

Seva analyzes text for patterns associated with high-control groups and financial manipulation. It works at three levels:

| Level | Method | Use Case |
|-------|--------|----------|
| **Basic** | Paste prompt + content into any LLM | Quick read on a concerning group |
| **Rigorous** | Cross-LLM validation pipeline | Publishable analysis with statistics |
| **Investigation** | Claude Code + Python toolkit | Deep dive with public records |

---

## Two Frameworks

### Seva (Core)
9 markers for high-control groups:
- Authority Elevation
- Self-Distrust Normalization  
- Outside Help Discouragement
- In-Group Superiority
- Exit Terror
- Thought-Terminating Clichés
- Relationship/Isolation Control
- Financial/Labor Exploitation
- Medical/Psychological Interference

### Seva-FIN
10 markers for financial manipulation:
- Income Mystification
- Urgency Manufacturing
- Authority Fabrication
- Exit-Blame Setup
- Thought-Termination
- Complexity Shield
- Community Capture
- Reflexive Economics
- Charity Hijacking
- Celebrity Shield

---

## Quick Start

### Option 1: Chat-Based Analysis

1. Copy the contents of `prompts/seva-standalone.md`
2. Paste into Claude, ChatGPT, or Gemini
3. Add your source material below the prompt
4. Read the analysis

### Option 2: Claude Code Investigation

1. Copy the setup prompt from `docs/claude-code-quickstart.md`
2. Paste into Claude Code to install the toolkit
3. Use the investigation templates to analyze any target

---

## Repository Structure

```
seva/
├── README.md                    # This file
├── LICENSE                      # MIT License
│
├── prompts/                     # Copy-paste prompts
│   ├── seva-standalone.md       # Core 9-marker detection
│   ├── seva-fin.md              # Financial grift detection
│   ├── gemini-structuring.md    # Data structuring for Gemini
│   └── deepseek-statistics.md   # Statistical analysis for DeepSeek
│
├── docs/                        # Documentation
│   ├── user-guide.md            # Complete usage guide
│   ├── claude-code-quickstart.md # Setup and investigation templates
│   └── methodology.md           # How Seva works (coming soon)
│
└── examples/                    # Example analyses (coming soon)
    └── README.md
```

---

## Validated Case Studies

| Target | Finding | Validation |
|--------|---------|------------|
| Atlantic Group (AA) | Phase 4-5, Cohen's d = 1.84 | 97.6% classification accuracy vs healthy AA |
| Landmark Worldwide | Phase 4-5, all 9 markers | Physical abuse testimony confirmed |
| NXIVM | Phase 5, all markers HIGH | $47M unforfeited asset discovered |
| SafeMoon | Seva-FIN 9.5/10 | CEO convicted May 2025 |
| CryptoZoo | Seva-FIN 8.0/10 | Pattern supports "scam" characterization |

---

## The NXIVM Discovery

Using Seva's financial investigation methodology, we found:

- **92 corporate entities** across 6 jurisdictions
- **$47 million Wakaya Island** — actively operating, never forfeited
- **Alejandro Betancourt** — likely hidden asset manager, never charged
- **6 financial red flags** visible by 2004 — 14 years before conviction

This demonstrates that automated analysis of public records can surface concerning patterns years before traditional investigation.

---

## Ethical Use

**Do:**
- Analyze organizations, not private individuals
- Use substantial corpus (50,000+ words for statistical work)
- Verify sources and document methodology
- Present findings as patterns, not conclusions
- Respect survivor privacy

**Don't:**
- Declare something "is a cult" — present the evidence
- Use thin evidence to make strong claims
- Weaponize against individuals
- Ignore limitations and alternative interpretations

---

## Limitations

Seva **can**:
- Identify linguistic patterns associated with coercive control
- Surface financial red flags in public records
- Quantify differences between groups
- Generate reproducible, documented analyses

Seva **cannot**:
- Prove something is a cult
- Determine legal liability
- Replace professional investigation
- Access private records
- Make definitive diagnoses

---

## Contributing

This is early-stage work. Contributions welcome:

- **Case studies**: Run Seva on groups you have corpus for
- **Marker refinement**: Suggest additions or modifications
- **Tool development**: Build on the methodology
- **Validation**: Challenge or extend the findings

---

## License

MIT License — use freely, attribute appropriately.

---

## Contact

[Your contact information]

---

*Seva (सेवा) is Sanskrit for "selfless service." This framework exists to help people protect themselves and others from manipulation.*
