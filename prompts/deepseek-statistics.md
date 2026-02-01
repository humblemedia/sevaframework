# DeepSeek Statistical Analysis Prompt

Use this prompt with DeepSeek to perform rigorous statistical validation of Seva findings. Paste the CSV data from Gemini where indicated.

---

I have structured data from a linguistic analysis comparing two populations on coercive control markers. I need comprehensive statistical validation.

## Data Description

**Group A (Target):** Suspected high-control group, N = [X]
**Group B (Control):** Healthy comparison group, N = [Y]

For each speaker/document, I have counts of 9 negative markers (M1-M9) and a binary positive indicator.

**Marker definitions:**
- M1: Authority elevation (leader as unquestionable)
- M2: Self-distrust normalization (your thinking is dangerous)
- M3: Outside help discouragement (therapy dismissed)
- M4: In-group superiority (we're the only real method)
- M5: Exit-terror (leaving = death/catastrophe)
- M6: Thought-terminating clichés (phrases that shut down questioning)
- M7: Relationship/isolation control (authority manages social contact)
- M8: Financial/labor exploitation (authority controls money/time)
- M9: Medical interference (authority overrides medical guidance)
- Positive: Autonomy language, healthy boundaries, humor

**Phase model (0-5):**
- 0-1: Normal group (low markers, positive present)
- 2: Authority elevation begins
- 3: Multiple markers, architecture visible
- 4: Exit-terror active, high density
- 5: Total control (M7+M8+M9 present together)

---

## ANALYSIS REQUESTED

### 1. Descriptive Statistics

For each population (Target vs Control), calculate:
- Mean and standard deviation of total negative markers
- Mean and standard deviation of positive indicator
- Median and IQR for total negative markers
- Distribution shape description (normal? skewed?)

### 2. Effect Size Analysis

Calculate and interpret:
- **Cohen's d** for difference in total negative markers between groups
- **Cohen's d** for difference in negative/positive ratio
- 95% confidence intervals for effect sizes
- Plain-language interpretation:
  - d < 0.2: negligible
  - 0.2 ≤ d < 0.5: small
  - 0.5 ≤ d < 0.8: medium
  - 0.8 ≤ d < 1.2: large
  - d ≥ 1.2: very large

### 3. Significance Testing

- **Mann-Whitney U test** for total negative markers (non-parametric, doesn't assume normality)
- **Chi-square test** for Phase 4+ classification (proportion comparison)
- **Fisher's exact test** for M9 presence (if cell counts are small)
- Report exact p-values and interpret at α = 0.05 and α = 0.01

### 4. Classification Analysis

Using total negative markers as predictor:
- **ROC curve analysis:** Can we distinguish groups?
- **Optimal threshold:** What cutoff maximizes accuracy?
- **Sensitivity and specificity** at optimal threshold
- **Classification accuracy:** Overall percentage correct

### 5. Marker-Level Analysis

For each marker M1-M9:
- Frequency in Target vs Control
- Chi-square or Fisher's exact test for each
- Which markers most strongly differentiate groups?
- Are any markers *categorically absent* from Control?

### 6. Temporal Analysis (if year data available)

- **Linear regression:** Has Target group rhetoric changed over time?
- Slope coefficient and significance
- Interpretation: linguistic stasis vs. drift

### 7. Correlation Structure

- Marker co-occurrence matrix for Target group
- Which markers cluster together?
- Does M5 (exit terror) correlate with M1 (authority)?

### 8. Phase Threshold Calibration

Based on the data:
- What total negative marker count best separates Phase 3 from Phase 4?
- What marker combination reliably indicates Phase 5?
- Recommended empirical thresholds

---

## OUTPUT FORMAT

For each analysis:
1. **Method:** Statistical test or measure used
2. **Result:** Numerical output with appropriate precision
3. **Interpretation:** Plain-language meaning
4. **Confidence:** Caveats, limitations, sample size concerns

### Summary Table

| Measure | Target | Control | Difference | Effect Size | p-value |
|---------|--------|---------|------------|-------------|---------|
| Mean negative markers | | | | | |
| Median negative markers | | | | | |
| Phase 4+ percentage | | | | | |
| M9 presence | | | | | |

### Key Findings

1. **Population difference:** Are Target and Control statistically distinguishable?
2. **Effect magnitude:** How large is the difference?
3. **Temporal trend:** Has Target changed over time?
4. **Predictive markers:** Which markers best distinguish populations?
5. **Classification accuracy:** Can we reliably sort speakers?
6. **Recommended thresholds:** What cutoffs define each phase?

---

## HYPOTHESES TO TEST

| Hypothesis | Test | Expected if H1 true |
|------------|------|---------------------|
| Target ≠ Control on negative markers | Mann-Whitney U | p < 0.001 |
| Large effect size | Cohen's d | d > 0.8 |
| No temporal trend in Target | Linear regression | slope ≈ 0, p > 0.05 |
| High classification accuracy | ROC analysis | AUC > 0.90 |
| M7+M8+M9 absent from Control | Frequency count | Count = 0 |

**Note:** If any finding contradicts expectations, report it honestly. The goal is to ground qualitative observations in quantitative evidence, not to force a predetermined conclusion.

---

## DATA

[PASTE CSV DATA FROM GEMINI HERE]
