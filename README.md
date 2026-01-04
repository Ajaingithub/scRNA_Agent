# scRNA Agent
Developing a single cell RNAseq Multi-Agent

That can perform the following process:
1. scRNAseq Data Curation and Download
2. Preprocessing
3. Differential
4. Plots (eg. Volcano Plot, MA plot)
5. Visualization

# 1. scRNAseq Data Curation and Download
'''
step:0

LLM OUTPUT:
{
  "tool_call": {
    "name": "geo_search",
    "arguments": {
      "query": "single cell[All Fields] AND RNA-seq[All Fields] AND immune[All Fields]"
    }
  }
}

TOOL RESULT:
[
  {
    "uid": "200301650",
    "accession": "GSE301650",
    "title": "Single-cell RNA-seq of isolated non-parenchymal cells from imiquimod-induced psoriasis mouse model.",
    "type": "Expression profiling by high throughput sequencing",
    "platform": "24247",
    "n_samples": 8,
    "suppFile": "MTX, TSV",
    "Date": "2026/01/01",
    "FTP": "ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE301nnn/GSE301650/"
  },
  {
    "uid": "200286125",
    "accession": "GSE286125",
    "title": "The Transcription Factor T-bet Plays a Crucial Role in Regulating the Immune Regulatory Function of Double-Negative T Cells",
    "type": "Expression profiling by high throughput sequencing",
    "platform": "17021",
    "n_samples": 4,
    "suppFile": "CSV",
    "Date": "2026/01/01",
    "FTP": "ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE286nnn/GSE286125/"
  },
  {
    "uid": "200285860",
    "accession": "GSE285860",
    "title": "RNA-seq of colon",
    "type": "Expression profiling by high throughput sequencing",
    "platform": "34290",
    "n_samples": 14,
    "suppFile": "CSV",
    "Date": "2026/01/01",
    "FTP": "ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE285nnn/GSE285860/"
  },
  {
    "uid": "200301873",
    "accession": "GSE301873",
    "title": "TGF-\u03b2RII/IL-15 Immunotherapeutic complex targets exhausted CD8+ T cell subsets in lymph nodes and tumors",
    "type": "Expression profiling by high throughput sequencing",
    "platform": "21103",
    "n_samples": 4,
    "suppFile": "MTX, TSV",
    "Date": "2025/12/31",
    "FTP": "ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE301nnn/GSE301873/"
  },
  {
    "uid": "200293951",
    "accession": "GSE293951",
    "title": "Single cell RNA-seq of myeloid immune cells in melanoma-draining lymph nodes",
    "type": "Expression profiling by high throughput sequencing",
    "platform": "24247",
    "n_samples": 3,
    "suppFile": "MTX, TSV",
    "Date": "2025/12/31",
    "FTP": "ftp://ftp.ncbi.nlm.nih.gov/geo/series/GSE293nnn/GSE293951/"
  }
]
step:1

LLM OUTPUT:
{
  "tool_call": {
    "name": "geo_download_https",
    "arguments": {
      "gse": "GSE301650"
    }
  }
}

TOOL RESULT:
geo_downloads/GSE301650_supplementary.tar
step:2

LLM OUTPUT:
{
  "tool_call": {
    "name": "geo_download_https",
    "arguments": {
      "gse": "GSE293951"
    }
  }
}

TOOL RESULT:
geo_downloads/GSE293951_supplementary.tar
step:3

LLM OUTPUT:
{
  "tool_call": {
    "name": "geo_download_https",
    "arguments": {
      "gse": "GSE293951"
    }
  }
}

### Analysis of GSE293951 Dataset:
- **Is this single-cell RNA-seq?**: Yes
- **Organism and immune context**: Mouse, focusing on myeloid immune cells in melanoma-draining lymph nodes.
- **Are RAW or processed files available?**: Processed files are available (MTX, TSV).
- **Does it match the user’s biological question?**: The dataset focuses on myeloid immune cells in melanoma-draining lymph nodes, which could be relevant if the user's biological question involves understanding the immune response in melanoma.

Would you like to proceed with further analysis of this dataset?

FINAL OUTPUT:
 {
  "tool_call": {
    "name": "geo_download_https",
    "arguments": {
      "gse": "GSE293951"
    }
  }
}

### Analysis of GSE293951 Dataset:
- **Is this single-cell RNA-seq?**: Yes
- **Organism and immune context**: Mouse, focusing on myeloid immune cells in melanoma-draining lymph nodes.
- **Are RAW or processed files available?**: Processed files are available (MTX, TSV).
- **Does it match the user’s biological question?**: The dataset focuses on myeloid immune cells in melanoma-draining lymph nodes, which could be relevant if the user's biological question involves understanding the immune response in melanoma.

Would you like to proceed with further analysis of this dataset?
'''