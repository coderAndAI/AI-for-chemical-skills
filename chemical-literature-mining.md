# Chemical Literature & Data Mining

AI toolkit for extracting chemical data from scientific literature, searching databases, and synthesizing research findings.

## Trigger Conditions
Use this skill when:
- User needs to search chemical databases (PubChem, ChEMBL, PDB)
- Requests literature review or paper summarization
- Wants to extract chemical data from PDFs/papers
- Asks about compound bioactivity or drug information
- Needs patent searches or prior art analysis
- Requests spectroscopic data (NMR, IR, MS)

## Core Capabilities

### 1. Database Queries
- PubChem: compound properties, bioassays, patents
- ChEMBL: drug targets, bioactivity data
- PDB: protein structures, ligand interactions
- ChemSpider: chemical structure search
- Reaxys/SciFinder: reaction and synthesis data

### 2. Literature Mining
- Extract chemical structures from papers
- Parse experimental procedures
- Identify reaction conditions and yields
- Extract spectroscopic data tables
- Summarize synthesis routes

### 3. Data Extraction
- NMR peak assignments from text
- IR/MS spectral data parsing
- Crystallographic data (CIF files)
- Melting points, boiling points, physical properties
- Biological activity (IC50, EC50, Ki values)

### 4. Research Synthesis
- Compare compounds across studies
- Aggregate property data from multiple sources
- Identify structure-activity relationships
- Generate literature summaries
- Find similar compounds and analogs

## Implementation Approach

### Python Stack
```python
# Core libraries
pubchempy  # PubChem API
chembl_webresource_client  # ChEMBL queries
biopython  # PDB access
pypdf2, pdfplumber  # PDF parsing
beautifulsoup4  # Web scraping
pandas  # Data organization
```

### Workflow Pattern
1. Parse user query (compound name, CAS, structure)
2. Query relevant databases
3. Extract and validate data
4. Cross-reference multiple sources
5. Present organized results with citations

## Example Interactions

**User**: "Find all bioactivity data for aspirin"
**Action**:
- Query PubChem for compound ID
- Search ChEMBL for bioassay results
- Extract IC50/EC50 values with targets
- Compile data table with references
- Highlight key findings (COX-1/COX-2 inhibition)

**User**: "Extract synthesis procedure from this paper [PDF]"
**Action**:
- Parse PDF experimental section
- Identify reagents, conditions, yields
- Extract spectroscopic characterization
- Format as structured protocol
- Highlight safety concerns

**User**: "Compare solubility data for ibuprofen from literature"
**Action**:
- Search multiple databases and papers
- Extract solubility values (different solvents/conditions)
- Aggregate data with sources
- Identify outliers or discrepancies
- Present summary table with citations

## Knowledge Integration
- Chemical nomenclature (IUPAC, common names, CAS)
- Database identifiers (CID, ChEMBL ID, InChI)
- Journal abbreviations and citation formats
- Spectroscopic interpretation basics
- Pharmacology terminology

## Data Quality
- Cross-validate data from multiple sources
- Flag conflicting values
- Distinguish experimental vs predicted data
- Note measurement conditions and methods
- Provide confidence levels

## Output Format
- Structured data tables with units
- Source citations (DOI, PubMed ID)
- Chemical identifiers for reproducibility
- Visual summaries (plots, structure comparisons)
- Downloadable datasets (CSV, JSON)
- Links to original sources
