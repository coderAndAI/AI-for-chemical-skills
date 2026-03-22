# Molecular Chemistry Analysis

Comprehensive toolkit for molecular structure analysis, visualization, and property prediction in computational chemistry.

## Trigger Conditions
Use this skill when:
- User mentions SMILES, InChI, molecular formulas, or chemical structures
- Requests to visualize molecules, draw structures, or generate 3D coordinates
- Asks about molecular properties (MW, logP, TPSA, etc.)
- Needs to convert between chemical formats
- Wants to analyze functional groups or substructures
- Requests similarity searches or molecular fingerprints

## Core Capabilities

### 1. Structure Input/Output
- Parse SMILES, InChI, InChIKey, molecular formulas
- Generate canonical SMILES
- Convert between formats
- Validate chemical structures

### 2. Visualization
- Generate 2D structure diagrams (SVG/PNG)
- Create 3D molecular models
- Highlight substructures and functional groups
- Interactive HTML visualizations with 3Dmol.js

### 3. Property Calculation
- Basic: MW, formula, exact mass
- Physicochemical: logP, TPSA, H-bond donors/acceptors
- Structural: rotatable bonds, aromatic rings, stereocenters
- Descriptors: molecular fingerprints, MACCS keys

### 4. Analysis Tools
- Substructure search and SMARTS matching
- Functional group identification
- Similarity calculations (Tanimoto, Dice)
- Murcko scaffold extraction

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Molecular manipulation and property calculation
py3Dmol  # 3D visualization
matplotlib  # 2D plotting
pubchempy  # Database queries
```

### Workflow Pattern
1. Parse input structure (SMILES/InChI/name)
2. Validate and canonicalize
3. Perform requested analysis
4. Generate visualizations
5. Output results with chemical context

## Example Interactions

**User**: "Analyze aspirin structure"
**Action**:
- Fetch SMILES from PubChem
- Calculate properties (MW=180.16, logP=1.19, TPSA=63.6)
- Generate 2D structure with highlighted functional groups
- Identify: carboxylic acid, ester, aromatic ring

**User**: "Compare caffeine and theobromine"
**Action**:
- Parse both structures
- Calculate Tanimoto similarity
- Highlight structural differences
- Compare properties side-by-side

**User**: "Generate 3D structure of morphine"
**Action**:
- Parse SMILES
- Generate 3D coordinates with force field optimization
- Create interactive 3Dmol.js visualization
- Show stereochemistry

## Safety & Best Practices
- Validate all chemical inputs before processing
- Handle stereochemistry carefully
- Cite data sources (PubChem, ChEMBL, etc.)
- Warn about computational vs experimental values
- Check for hazardous compounds and provide safety info

## Output Format
- Clear property tables
- High-quality structure images
- Interactive visualizations when possible
- Chemical identifiers for reproducibility
- References to databases/literature
