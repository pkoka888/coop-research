# Research Templates

This directory contains standardized templates for different types of research conducted within the COOP framework.

## Available Templates

### 1. RESEARCH-TEMPLATE.md
**Purpose:** CLI/Tool research and analysis
**Use Case:** Studying command-line tools, their installation, configuration, and integration patterns
**Scope:** Technical tool assessment, non-interactive usage, fallback strategies

### 2. WEB-RESEARCH-TEMPLATE.md
**Purpose:** Web-based research using APIs and online sources
**Use Case:** Answering questions requiring external data from web APIs, search engines, and online communities
**Scope:** DuckDuckGo API, Stack Exchange, web scraping, API-based research methods

### 3. GITHUB-RESEARCH-TEMPLATE.md
**Purpose:** Code repository and community analysis
**Use Case:** Analyzing GitHub repositories, code patterns, community adoption, and implementation trends
**Scope:** Repository search, code search, metrics analysis, trend identification

## Template Structure

Each template follows a consistent structure:

1. **Research Query** - Clear definition of the research question
2. **Research Methods** - Specific approaches and tools to use
3. **Data Sources** - APIs, commands, and sources to query
4. **Implementation** - Code templates and execution methods
5. **Analysis Framework** - How to interpret and analyze results
6. **Results Synthesis** - How to combine findings into actionable insights
7. **COOP Integration** - How findings relate to COOP capabilities and workflows

## Usage Guidelines

### Selecting a Template
- **CLI Research:** Use when studying tools, commands, or technical utilities
- **Web Research:** Use for general questions requiring external data sources
- **GitHub Research:** Use when analyzing code ecosystems, community trends, or implementation patterns

### Research Process
1. Choose appropriate template based on research type
2. Fill in research query and customize data sources
3. Execute research using provided scripts/templates
4. Analyze results using framework provided
5. Synthesize findings and identify COOP integration points
6. Update relevant COOP skills/workflows based on findings

### Quality Standards
- Use multiple data sources when possible
- Validate findings across sources
- Document limitations and gaps
- Provide specific examples and metrics
- Identify concrete integration opportunities

## Researcher Role

The `researcher.json` role in `coop/roles/` is designed to execute these research templates with:
- Parallel research execution capabilities
- Multiple agent coordination (web-researcher, code-analyzer, data-synthesizer)
- Comprehensive quality gates for research validation
- Integration with COOP workflows and skills

## Adding New Templates

When creating new research templates:

1. Follow the established structure
2. Include implementation scripts/templates
3. Define analysis frameworks
4. Specify COOP integration points
5. Update this README
6. Add template reference to `researcher.json` role

## Research Workflow Integration

Research findings should be integrated into:
- `coop/skills/` - New capabilities discovered
- `coop/docs/` - Updated practices and workflows
- `coop/00-framework/` - Framework improvements
- `coop/roles/` - Role capability updates
