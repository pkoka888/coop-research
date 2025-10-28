# GitHub Research Template

## Research Query
**Question:** [Specific research question about GitHub repositories/code]

## Research Scope
- **Repository Search:** `gh search repos "[query]" --json fullName,description,url,stargazersCount,language --limit [N]`
- **Code Search:** `gh search code "[query]" --json repository,name,path,sha,textMatches --limit [N]`
- **Issues/PRs:** `gh search issues "[query]" --json title,url,repository,state,createdAt --limit [N]`

## Implementation Script Template
```python
import subprocess
import json
import sys

def run_gh_command(command):
    """Execute GitHub CLI command and return parsed JSON"""
    try:
        result = subprocess.run(command, shell=True, capture_output=True, text=True, timeout=30)
        if result.returncode == 0:
            return json.loads(result.stdout)
        else:
            return {"error": result.stderr.strip()}
    except Exception as e:
        return {"error": str(e)}

# Research queries
repo_queries = [
    "[PRIMARY_QUERY]",
    "[RELATED_QUERY_1]",
    "[RELATED_QUERY_2]"
]

code_queries = [
    "[CODE_PATTERN_1]",
    "[CODE_PATTERN_2]"
]

# Execute repository searches
repo_results = {}
for i, query in enumerate(repo_queries):
    command = f'gh search repos "{query}" --json fullName,description,url,stargazersCount,language --limit 20'
    repo_results[f"query_{i+1}"] = run_gh_command(command)

# Execute code searches
code_results = {}
for i, query in enumerate(code_queries):
    command = f'gh search code "{query}" --json repository,name,path,textMatches --limit 10'
    code_results[f"code_query_{i+1}"] = run_gh_command(command)

# Combine results
research_results = {
    "repositories": repo_results,
    "code_search": code_results,
    "metadata": {
        "total_repos_found": sum(len(r.get("data", [])) for r in repo_results.values() if "error" not in r),
        "total_code_matches": sum(len(r.get("data", [])) for r in code_results.values() if "error" not in r)
    }
}

print(json.dumps(research_results, indent=2))
```

## Analysis Framework
### Repository Analysis
- **Popularity Metrics:** Stars, forks, recent activity
- **Language Distribution:** Primary languages used
- **Activity Patterns:** Recent commits, issues, PRs
- **Community Size:** Contributors, maintainers

### Code Pattern Analysis
- **Implementation Frequency:** How often patterns appear
- **Quality Indicators:** Code structure, documentation
- **Adoption Trends:** New vs. established repositories
- **Integration Patterns:** How features are combined

## Key Metrics to Track
```python
def analyze_repositories(repos):
    metrics = {
        "total_stars": sum(r.get("stargazersCount", 0) for r in repos),
        "avg_stars": sum(r.get("stargazersCount", 0) for r in repos) / len(repos) if repos else 0,
        "languages": {},
        "top_repos": sorted(repos, key=lambda x: x.get("stargazersCount", 0), reverse=True)[:5]
    }

    for repo in repos:
        lang = repo.get("language", "Unknown")
        metrics["languages"][lang] = metrics["languages"].get(lang, 0) + 1

    return metrics
```

## Results Synthesis
- **Trends Identified:** [Common patterns across repositories]
- **Best Practices:** [Successful implementation approaches]
- **Gaps in Ecosystem:** [Missing tools or features]
- **Innovation Opportunities:** [Potential improvements]

## COOP Integration Points
- **Skill Updates:** [New capabilities discovered]
- **Workflow Enhancements:** [Process improvements identified]
- **Research Expansion:** [Additional areas to investigate]

## Checklist
- [ ] Repository search executed with multiple queries
- [ ] Code patterns analyzed for implementation quality
- [ ] Metrics calculated and trends identified
- [ ] Findings documented with specific examples
- [ ] Integration recommendations provided
- [ ] Follow-up research questions defined
