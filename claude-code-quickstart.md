# Seva Claude Code Quickstart

This document contains everything you need to set up a powerful Seva investigation environment using Claude Code. Copy the prompts into Claude Code and let them run.

---

## Part 1: Core Toolkit Setup

Copy this entire prompt into Claude Code:

```
Set up a complete Seva investigation toolkit. This will install all dependencies for:
- Audio/video downloading and transcription
- Linguistic analysis
- Network graphing and visualization  
- Statistical validation
- Database storage

## Step 1: Install Python Packages

Install the following (use --break-system-packages flag if needed):

### Core Pipeline
pip install yt-dlp                    # Download audio/video from anywhere
pip install faster-whisper            # Local transcription (no API costs)
pip install sentence-transformers     # Semantic embeddings
pip install spacy                     # Industrial NLP
pip install scipy numpy pandas        # Statistics

### Investigation Tools
pip install networkx                  # Entity network graphs
pip install matplotlib plotly         # Visualization
pip install requests                  # API calls
pip install beautifulsoup4 lxml       # Web scraping

### Database & Storage
pip install chromadb                  # Vector database for embeddings
pip install sqlite3                   # (usually built-in)

### Linguistic Analysis
pip install nltk                      # Lexical resources
pip install textacy                   # spaCy extension

### Utilities
pip install rich                      # Nice terminal output
pip install tqdm                      # Progress bars
pip install python-dotenv             # Environment management

## Step 2: Download Language Models

python -m spacy download en_core_web_sm

python -c "
import nltk
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')
nltk.download('wordnet')
nltk.download('stopwords')
"

## Step 3: Create Directory Structure

Create the following directory structure:

seva-toolkit/
├── input/              # Raw audio/video files or URLs
├── transcripts/        # Transcribed text
├── embeddings/         # Vector database
├── analysis/           # Seva marker analysis output
├── evidence/           # Final evidence packages
├── investigations/     # Per-target investigation folders
│   └── template/       # Template for new investigations
├── prompts/            # Saved prompts
└── scripts/            # Utility scripts

## Step 4: Create Test Script

Create seva-toolkit/scripts/test_install.py:

```python
#!/usr/bin/env python3
"""Test that all Seva toolkit dependencies are installed correctly."""

import sys

def test_import(module_name, package_name=None):
    """Test if a module can be imported."""
    if package_name is None:
        package_name = module_name
    try:
        __import__(module_name)
        print(f"✓ {package_name}")
        return True
    except ImportError as e:
        print(f"✗ {package_name}: {e}")
        return False

def main():
    print("Testing Seva Toolkit Installation\n" + "="*40)
    
    results = []
    
    # Core Pipeline
    print("\n[Core Pipeline]")
    results.append(test_import("yt_dlp", "yt-dlp"))
    results.append(test_import("faster_whisper", "faster-whisper"))
    results.append(test_import("sentence_transformers", "sentence-transformers"))
    results.append(test_import("spacy"))
    results.append(test_import("scipy"))
    results.append(test_import("numpy"))
    results.append(test_import("pandas"))
    
    # Investigation Tools
    print("\n[Investigation Tools]")
    results.append(test_import("networkx"))
    results.append(test_import("matplotlib"))
    results.append(test_import("plotly"))
    results.append(test_import("requests"))
    results.append(test_import("bs4", "beautifulsoup4"))
    
    # Database & Storage
    print("\n[Database & Storage]")
    results.append(test_import("chromadb"))
    results.append(test_import("sqlite3"))
    
    # Linguistic Analysis
    print("\n[Linguistic Analysis]")
    results.append(test_import("nltk"))
    results.append(test_import("textacy"))
    
    # Utilities
    print("\n[Utilities]")
    results.append(test_import("rich"))
    results.append(test_import("tqdm"))
    results.append(test_import("dotenv", "python-dotenv"))
    
    # Summary
    print("\n" + "="*40)
    passed = sum(results)
    total = len(results)
    print(f"Result: {passed}/{total} packages installed")
    
    if passed == total:
        print("✓ All dependencies installed successfully!")
        return 0
    else:
        print("✗ Some packages failed. See above for details.")
        return 1

if __name__ == "__main__":
    sys.exit(main())
```

## Step 5: Create README

Create seva-toolkit/README.md explaining the directory structure.

## Step 6: Verify Installation

Run the test script and report results.

## Notes

- If pyannote-audio is needed later (speaker diarization), it requires PyTorch and can be finicky. Skip for now.
- faster-whisper works on CPU but is much faster with CUDA GPU
- If any package fails, note it but continue with the rest

Report what was installed successfully and what (if anything) failed.
```

---

## Part 2: API Access Setup

For investigation work, you'll want access to public data APIs. Copy this into Claude Code:

```
Set up API access for Seva investigations.

## ProPublica Nonprofit Explorer

No API key needed. Test access:

```python
import requests

# Test ProPublica API
response = requests.get(
    "https://projects.propublica.org/nonprofits/api/v2/search.json",
    params={"q": "test"}
)
print(f"ProPublica API: {'OK' if response.status_code == 200 else 'FAILED'}")
```

## CourtListener

Free API with rate limits. Test access:

```python
response = requests.get(
    "https://www.courtlistener.com/api/rest/v3/search/",
    params={"q": "test", "type": "o"}
)
print(f"CourtListener API: {'OK' if response.status_code == 200 else 'FAILED'}")
```

## OpenCorporates

Free tier available. Test:

```python
response = requests.get(
    "https://api.opencorporates.com/v0.4/companies/search",
    params={"q": "test"}
)
print(f"OpenCorporates API: {'OK' if response.status_code == 200 else 'FAILED'}")
```

## UK Companies House

Free API key available at https://developer.company-information.service.gov.uk/

Create a file at seva-toolkit/.env for API keys:
```
# Seva Toolkit API Keys
# Get UK Companies House key at: https://developer.company-information.service.gov.uk/
UK_COMPANIES_HOUSE_API_KEY=your_key_here

# Optional: Other API keys as needed
# COURTLISTENER_API_KEY=your_key_here
```

Run all tests and report which APIs are accessible.
```

---

## Part 3: Your First Investigation

Once setup is complete, here's how to start an investigation. Copy into Claude Code:

```
I want to investigate [ORGANIZATION NAME] using the Seva framework.

## Phase 1: Create Investigation Folder

Create: seva-toolkit/investigations/[org-name]/
With subfolders: sources/, transcripts/, analysis/, evidence/

## Phase 2: Gather Public Records

### Nonprofit Data (if applicable)
Search ProPublica Nonprofit Explorer for any 990 filings:
- Organization name variations
- Known leader names
- Related entity names

### Corporate Filings
Search OpenCorporates for corporate registrations:
- All jurisdictions
- Officer/director names
- Related entities

### Litigation
Search CourtListener for court cases:
- As plaintiff (who do they sue?)
- As defendant (who sues them?)
- Key individuals

### News/Media
Search for coverage, criticism, survivor accounts.

## Phase 3: Build Network Graph

Using data collected:
- Create nodes for people and organizations
- Create edges for relationships (officer-of, sued-by, related-to)
- Visualize with NetworkX
- Identify clusters and key connectors

## Phase 4: Run Seva Analysis

If audio/video sources are available:
- Download with yt-dlp
- Transcribe with faster-whisper
- Run linguistic marker detection

## Phase 5: Generate Evidence Package

Compile:
- Entity list with relationships
- Network visualization
- Litigation timeline
- Red flags identified
- Seva marker analysis (if applicable)
- Source documentation

Save to: seva-toolkit/investigations/[org-name]/evidence/REPORT.md
```

---

## Part 4: Example Workflow — The NXIVM Investigation

This is the exact workflow that discovered the $47M Wakaya Island asset:

```
I want to do a retrospective financial analysis of NXIVM to demonstrate 
what automated detection could have caught before the 2018 arrests.

## Known Entity Names
- NXIVM Corporation
- Executive Success Programs (ESP)
- First Principles Inc / First Principles Incorporated
- Ethical Science Foundation
- World Ethical Foundations Consortium
- Jness (women's group)
- Society of Protectors (men's group)
- Rainbow Cultural Garden
- ACK Knowledge LLC
- ACK Management PTE Ltd

## Known Individuals
- Keith Raniere (founder)
- Nancy Salzman (president)
- Clare Bronfman (funder)
- Sara Bronfman (funder)
- Alejandro Betancourt (executive board)
- Emiliano Salinas (ESP Mexico)

## Tasks

1. Search ProPublica for nonprofit filings
2. Search CourtListener for litigation patterns
3. Build entity/officer network graph
4. Search OpenCorporates for corporate registrations
5. Search UK Companies House for any UK entities
6. Generate red flag report showing what was visible by 2015

Store everything in seva-toolkit/investigations/nxivm/
```

**What we found through iterative prompting:**
- 92 corporate entities across 6 jurisdictions
- $47M Wakaya Island purchase (ACK = Alex, Clare, Keith)
- Betancourt identified as likely hidden asset manager
- 6 financial red flags visible by 2004
- Asset was never forfeited despite conviction

---

## Part 5: The Iterative Investigation Method

The power isn't in single prompts — it's in conversational steering.

**Pattern:**
```
Initial prompt → Finding → Follow-up question → Deeper finding → Follow-up...
```

**Example sequence:**

1. "Analyze NXIVM financials"
   → Finding: Only $220K visible in nonprofit filings

2. "The Bronfmans invested $150M. Where's the rest?"
   → Finding: Money flowed through for-profit entities, offshore structures

3. "What offshore structures?"
   → Finding: Wakaya Island purchase, $47M, through ACK entities

4. "Who is ACK?"
   → Finding: ACK = Alex (Betancourt), Clare (Bronfman), Keith (Raniere)

5. "Was Wakaya forfeited?"
   → Finding: No — Bronfman paid $6M to preserve it

6. "Who is Betancourt? Why wasn't he charged?"
   → Finding: Mexican banking family, never charged despite 9 years on board

**Each finding generates the next question.**

---

## Troubleshooting

### Package Installation Fails

```
pip install [package] --break-system-packages
```

### GPU Not Detected for Whisper

faster-whisper works on CPU, just slower. For GPU:
- Need CUDA installed
- Need compatible PyTorch

### API Rate Limited

- CourtListener: Add delays between requests
- OpenCorporates: Free tier has limits, consider paid for heavy use

### Can't Download from YouTube

Some content is restricted. Try:
- Different URL format
- VPN (if geoblocked)
- Alternative source

---

## Quick Reference

| Task | Command/Prompt |
|------|----------------|
| Download audio | `yt-dlp -x --audio-format mp3 "URL"` |
| Transcribe | `python -c "from faster_whisper import WhisperModel; ..."` |
| Search nonprofits | ProPublica API (no auth) |
| Search litigation | CourtListener API |
| Search corporations | OpenCorporates API |
| Build network | NetworkX + matplotlib |

---

## What You Can Do Now

With this setup, you can:

1. **Download and transcribe** any public audio/video
2. **Search public records** (nonprofits, court cases, corporate filings)
3. **Build network graphs** showing entity relationships
4. **Run statistical analysis** on linguistic patterns
5. **Generate evidence packages** documenting findings

The toolkit gives Claude Code the power to do in hours what would take weeks manually.

Start with Part 1 (Core Setup), then work through Parts 2-4 as needed for your investigation.
