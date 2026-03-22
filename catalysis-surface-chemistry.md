# Catalysis & Surface Chemistry

AI toolkit for catalyst design, reaction mechanism analysis, and surface interaction modeling.

## Trigger Conditions
Use this skill when:
- User asks about catalysts, catalytic cycles, or reaction mechanisms
- Requests catalyst screening or optimization
- Needs surface adsorption or binding energy calculations
- Asks about heterogeneous or homogeneous catalysis
- Wants to analyze active sites or coordination environments
- Requests turnover frequency (TOF) or selectivity predictions

## Core Capabilities

### 1. Catalyst Analysis
- Identify active sites and coordination environments
- Analyze metal centers and ligand effects
- Calculate oxidation states and d-electron counts
- Evaluate steric and electronic properties
- Screen catalyst libraries

### 2. Mechanism Elucidation
- Map catalytic cycles and intermediates
- Identify rate-determining steps
- Calculate energy profiles and barriers
- Analyze competing pathways
- Predict selectivity and side reactions

### 3. Surface Chemistry
- Model surface adsorption (Langmuir, BET)
- Calculate binding energies and geometries
- Analyze surface coverage and site blocking
- Predict desorption temperatures
- Evaluate support effects

### 4. Catalyst Design
- Ligand optimization for selectivity
- Metal substitution and doping strategies
- Support material selection
- Particle size and morphology effects
- Promoter and poison identification

## Implementation Approach

### Python Stack
```python
# Core libraries
ase  # Atomic simulation environment
catkit  # Catalysis toolkit
pymatgen  # Materials analysis
psi4, orca  # Quantum chemistry
networkx  # Reaction network analysis
```

### Workflow Pattern
1. Define catalyst structure and reaction
2. Identify possible intermediates and pathways
3. Calculate energies and barriers
4. Analyze rate-determining steps
5. Predict activity and selectivity
6. Suggest optimization strategies

## Example Interactions

**User**: "Analyze Wilkinson's catalyst for hydrogenation"
**Action**:
- Parse [RhCl(PPh3)3] structure
- Identify Rh(I) d8 square planar complex
- Map catalytic cycle (oxidative addition → migratory insertion → reductive elimination)
- Calculate key intermediate energies
- Identify rate-determining step
- Explain trans effect of PPh3 ligands

**User**: "Design a catalyst for CO2 reduction"
**Action**:
- Survey known CO2 reduction catalysts (Cu, Fe, Ni complexes)
- Identify key requirements (low overpotential, selectivity)
- Screen metal centers (d-electron count, redox potential)
- Suggest ligand frameworks (porphyrins, bipyridines)
- Predict binding modes (η1-C, η2-C,O)
- Rank candidates by predicted activity

**User**: "Calculate CO adsorption energy on Pt(111)"
**Action**:
- Generate Pt(111) surface slab model
- Place CO in different sites (atop, bridge, hollow)
- Optimize geometries with DFT
- Calculate adsorption energies (Eads = Eslab+CO - Eslab - ECO)
- Predict most stable site (atop, ~1.5 eV)
- Analyze electronic structure (d-band center)

## Knowledge Base
- Common catalytic cycles (Heck, Suzuki, metathesis, hydrogenation)
- Organometallic complexes and nomenclature
- Surface science concepts (adsorption isotherms, TPD)
- Descriptor-based catalyst design (d-band theory, Sabatier principle)
- Industrial catalysts and processes
- Catalyst characterization techniques

## Best Practices
- Consider both thermodynamics and kinetics
- Account for solvent and support effects
- Validate with experimental data when available
- Check for catalyst deactivation pathways
- Consider scalability and cost
- Reference literature precedents

## Output Format
- Catalyst structure diagrams with active sites highlighted
- Catalytic cycle schemes with intermediates
- Energy profiles and reaction coordinates
- Activity/selectivity predictions with confidence
- Optimization recommendations with rationale
- Comparison with benchmark catalysts
- Literature references and experimental data
