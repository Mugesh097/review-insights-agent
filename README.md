# Review Insights Agent (GitHub CLI)

## Overview
Review Insights Agent is a GitHub CLI (`gh`) based tool that analyzes Pull Request review comments from a specified approver and generates a consolidated report of recurring review patterns.

## Workflow
1. Execute the CLI command.
2. Validate GitHub authentication and input parameters.
3. Load team members from a TXT or JSON file.
4. Discover repositories in the specified organization.
5. Retrieve PRs created by the listed developers within the selected period.
6. Retrieve review comments for each PR.
7. Filter comments made by the specified approver.
8. Normalize and categorize similar comments.
9. Split analysis into Front-End and Back-End based on the team file.
10. Generate statistics and recommendations.
11. Produce a Markdown report (`review-analysis.md`).

## Project Structure

```
review-insights-agent/
├── cli/
├── github/
├── loaders/
├── analysis/
├── reports/
├── config/
├── utils/
└── docs/
```

## Suggested CLI

```bash
gh review-insights \
  --org my-org \
  --approver "Saranya" \
  --team-file team-members.json \
  --period current-month
```

## Supported Inputs
- Organization
- Approver
- Team file (.txt/.json)
- Current month
- Last month
- Custom date range

## Output
- review-analysis.md
- review-analysis.json
- review-analysis.txt

## Setup

### Prerequisites
- GitHub CLI installed
- Python 3.11+
- GitHub authentication:
  ```bash
  gh auth login
  ```

### Install
```bash
git clone <repository>
cd review-insights-agent
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### Run
```bash
python cli/main.py --org my-org --approver Saranya --team-file team-members.json --period current-month
```

## Future Enhancements
- AI-based semantic clustering
- HTML dashboard
- GitHub Action integration
- VS Code extension
- Predictive PR checklist
