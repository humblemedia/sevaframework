# Gemini Data Structuring Prompt

Use this prompt with Gemini to convert raw Seva analysis outputs into structured data suitable for statistical validation.

---

I have analyzed multiple transcripts/documents for coercive control markers using the Seva framework. I need you to structure this data for statistical analysis.

## The Seva Marker System

**Negative Markers (M1-M9):**
- M1: Authority Elevation
- M2: Self-Distrust Normalization
- M3: Outside Help Discouragement
- M4: In-Group Superiority
- M5: Exit Terror
- M6: Thought-Terminating Clichés
- M7: Relationship/Isolation Control
- M8: Financial/Labor Exploitation
- M9: Medical/Psychological Interference

**Positive Indicators:**
- Choice language ("you can", "it's up to you")
- Encouraging outside help
- Healthy boundary modeling
- Humor and lightness
- Autonomy respect

## Your Task

From the raw analysis data I provide, create:

### 1. Speaker/Document Table (CSV format)

```
ID,Name,Group,Year,M1,M2,M3,M4,M5,M6,M7,M8,M9,Total_Negative,Positive_Present,Phase_Estimate
1,Speaker_A,Target,2020,3,2,1,2,4,3,2,1,0,18,0,4
2,Speaker_B,Target,2021,2,1,0,1,3,2,0,0,0,9,1,3
3,Speaker_C,Control,2019,0,0,0,0,0,1,0,0,0,1,1,1
...
```

**Columns:**
- ID: Sequential identifier
- Name: Speaker/document name (anonymize if needed)
- Group: "Target" or "Control"
- Year: Year of recording/publication
- M1-M9: Count of instances for each marker (0 if none)
- Total_Negative: Sum of M1-M9
- Positive_Present: 1 if positive indicators found, 0 if not
- Phase_Estimate: 0-5 based on analysis

### 2. Summary Statistics

For each group (Target vs Control), calculate:
- N (sample size)
- Mean total negative markers
- Standard deviation
- Median
- Range (min-max)
- Percentage with M7+M8+M9 present (Phase 5 indicators)

### 3. Marker Frequency Table

| Marker | Target Count | Control Count | Ratio |
|--------|--------------|---------------|-------|
| M1 | X | Y | X/Y |
| M2 | X | Y | X/Y |
| ... | ... | ... | ... |

### 4. Outlier Identification

Flag any:
- Control speakers scoring unusually high (possible misclassification)
- Target speakers scoring unusually low (possible outliers)
- Missing data or unclear classifications

### 5. Data Quality Notes

- Any ambiguous codings
- Sources that were difficult to analyze
- Confidence level in the structured data

---

## RAW ANALYSIS DATA:

[PASTE YOUR SEVA ANALYSIS OUTPUTS HERE]
