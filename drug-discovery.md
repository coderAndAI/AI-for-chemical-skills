# Drug Discovery & Pharmacology

AI toolkit for drug design, ADMET prediction, target identification, and pharmacological analysis.

## Trigger Conditions
Use this skill when:
- User asks about drug-likeness or Lipinski's Rule of Five
- Requests ADMET predictions (absorption, distribution, metabolism, excretion, toxicity)
- Needs molecular docking or protein-ligand binding analysis
- Asks about drug targets, mechanisms of action
- Wants to design drug analogs or optimize lead compounds
- Requests pharmacokinetic/pharmacodynamic modeling

## Core Capabilities

### 1. Drug-Likeness Assessment
- Lipinski's Rule of Five compliance
- Veber rules and oral bioavailability
- PAINS (Pan-Assay Interference) filters
- Synthetic accessibility scores
- Lead-likeness and fragment-likeness

### 2. ADMET Prediction
- Absorption: Caco-2 permeability, HIA, bioavailability
- Distribution: BBB penetration, plasma protein binding, Vd
- Metabolism: CYP450 substrate/inhibitor prediction
- Excretion: clearance, half-life
- Toxicity: hERG liability, hepatotoxicity, mutagenicity

### 3. Target Interaction
- Molecular docking (AutoDock, Vina)
- Binding affinity prediction
- Protein-ligand interaction analysis
- Target identification and validation
- Off-target prediction

### 4. Lead Optimization
- Structure-activity relationship (SAR) analysis
- Scaffold hopping and bioisosteric replacement
- R-group optimization
- Multi-parameter optimization (MPO)
- De novo drug design

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Cheminformatics and descriptors
deepchem  # ML models for drug discovery
oddt  # Molecular docking
biopython  # Protein structure handling
admet_ai  # ADMET prediction models
molvs  # Molecule validation and standardization
```

### Workflow Pattern
1. Parse drug molecule (SMILES/structure)
2. Calculate physicochemical properties
3. Predict ADMET properties
4. Assess drug-likeness and toxicity
5. Suggest optimization strategies
6. Rank candidates

## Example Interactions

**User**: "Evaluate aspirin as a drug candidate"
**Action**:
- Calculate Lipinski parameters (MW=180, HBD=1, HBA=4, logP=1.2)
- Check Rule of Five compliance (PASS)
- Predict ADMET: high GI absorption, no BBB penetration
- Identify COX-1/COX-2 as targets
- Assess safety profile (GI bleeding risk)
- Suggest: good oral drug, but consider GI protection

**User**: "Design analogs of ibuprofen with better selectivity"
**Action**:
- Analyze ibuprofen structure and SAR
- Identify key pharmacophore (propionic acid + aromatic)
- Suggest modifications for COX-2 selectivity
- Generate analogs (e.g., add sulfonamide group)
- Predict binding affinity and selectivity
- Rank by predicted COX-2/COX-1 ratio

**User**: "Predict BBB penetration for this compound"
**Action**:
- Calculate molecular descriptors (MW, logP, TPSA, HBD)
- Apply BBB prediction models
- Estimate log(BB) or permeability
- Identify structural features affecting penetration
- Suggest modifications if needed (reduce TPSA, increase lipophilicity)

## Knowledge Base
- Drug-likeness rules (Lipinski, Veber, Ghose)
- ADMET models and datasets
- Common drug targets and mechanisms
- Toxicophores and structural alerts
- Bioisosteric replacements
- Approved drugs and clinical candidates

## Safety & Ethics
- Flag potential toxicity concerns
- Identify structural alerts (mutagenic, carcinogenic)
- Consider therapeutic index
- Highlight off-target effects
- Note regulatory considerations
- Emphasize need for experimental validation

## Output Format
- Drug-likeness scorecards
- ADMET property tables with confidence scores
- Molecular structure with highlighted features
- SAR analysis and optimization suggestions
- Docking poses and interaction diagrams
- Ranked candidate lists with rationale
- References to similar approved drugs
