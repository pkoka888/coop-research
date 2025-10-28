# Web Research Template

## Research Query
**Question:** [Specific research question]

## Research Methods
- [ ] DuckDuckGo Instant Answers API
- [ ] Google Custom Search API (if available)
- [ ] Web scraping of specific sites
- [ ] API-based searches (Stack Exchange, Reddit, etc.)

## Data Sources
1. **Search Engines & APIs**
   - DuckDuckGo: `https://api.duckduckgo.com/?q={query}&format=json&no_html=1&skip_disambig=1`
   - Stack Exchange: `https://api.stackexchange.com/2.3/search?order=desc&sort=relevance&intitle={query}&site=stackoverflow`

2. **Code Repositories**
   - GitHub Search API
   - GitLab, Bitbucket searches

3. **Academic & Research**
   - arXiv API
   - Papers with Code
   - Google Scholar (limited API access)

## Implementation Script Template
```python
import requests
import json

# Research query
query = "[RESEARCH_QUERY]"

# API endpoints and parameters
sources = {
    "duckduckgo": {
        "url": "https://api.duckduckgo.com/",
        "params": {
            "q": query,
            "format": "json",
            "no_html": 1,
            "skip_disambig": 1
        }
    },
    "stackoverflow": {
        "url": "https://api.stackexchange.com/2.3/search",
        "params": {
            "order": "desc",
            "sort": "relevance",
            "intitle": query,
            "site": "stackoverflow",
            "pagesize": 10
        }
    }
}

results = {}

for source_name, config in sources.items():
    try:
        response = requests.get(config["url"], params=config["params"], timeout=10)
        data = response.json()

        # Parse results based on source
        if source_name == "duckduckgo":
            parsed = parse_duckduckgo_results(data)
        elif source_name == "stackoverflow":
            parsed = parse_stackoverflow_results(data)

        results[source_name] = parsed

    except Exception as e:
        results[source_name] = {"error": str(e)}

print(json.dumps(results, indent=2))
```

## Results Analysis
- **Key Findings:** [Summarize main discoveries]
- **Data Quality:** [Assess reliability of sources]
- **Gaps Identified:** [What information is missing]
- **Follow-up Research:** [Additional questions raised]

## Integration with COOP
- **Relevant Skills:** [Which COOP skills this research informs]
- **Workflow Updates:** [How this affects existing processes]
- **New Capabilities:** [Tools or methods discovered]

## Checklist
- [ ] Multiple data sources queried
- [ ] Results validated for accuracy
- [ ] Findings documented clearly
- [ ] Integration points identified
- [ ] Follow-up research planned
