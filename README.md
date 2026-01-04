# scRNA Agent
Developing a single cell RNAseq Multi-Agent

That can perform the following process:
1. scRNAseq Data Curation and Download
2. Preprocessing
3. Differential
4. Plots (eg. Volcano Plot, MA plot)
5. Visualization

# scRNAseq Data Curation and Download
An LLM-assisted agent to search, evaluate, and download relevant single-cell RNA-seq datasets from GEO based on a biological query.

### Features
- Query GEO using natural language or structured search terms
- Identify single-cell RNA-seq datasets
- Prefer processed data formats (MTX, TSV, CSV)
- Automatically download supplementary files
- Provide dataset-level biological context summaries

### Example Usage

```python
query = (
    "single cell[All Fields] AND RNA-seq[All Fields] AND immune[All Fields]"
)

final_output = run_agent(query)
print("\nFINAL OUTPUT:\n", final_output)
```

### Processing
The agent performs the following steps:
1. Search GEO
2. Identify relevant datasets
3. Download processed data
4. Summarize biological relevance

### Output
Downloaded supplementary files are stored locally: