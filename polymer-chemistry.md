# Polymer Chemistry & Macromolecular Science

AI toolkit for polymer structure analysis, property prediction, and materials design.

## Trigger Conditions
Use this skill when:
- User mentions polymers, macromolecules, or monomers
- Requests polymer property predictions (Tg, Tm, mechanical properties)
- Asks about polymerization mechanisms or kinetics
- Needs to design copolymers or polymer blends
- Wants to analyze polymer structures (tacticity, molecular weight)
- Requests rheology or processing simulations

## Core Capabilities

### 1. Polymer Structure Analysis
- Parse polymer SMILES and repeat units
- Identify polymer class (thermoplastic, thermoset, elastomer)
- Analyze tacticity (isotactic, syndiotactic, atactic)
- Calculate degree of polymerization and molecular weight
- Determine end groups and branching

### 2. Property Prediction
- Thermal properties (Tg, Tm, Td, heat capacity)
- Mechanical properties (modulus, tensile strength, elongation)
- Solubility parameters (Hansen, Hildebrand)
- Dielectric properties and conductivity
- Barrier properties (permeability, diffusion)

### 3. Polymerization Design
- Mechanism selection (free radical, ionic, condensation, ROMP)
- Monomer reactivity ratios
- Kinetics modeling (conversion, rate, MW distribution)
- Copolymer composition prediction (Mayo-Lewis)
- Living/controlled polymerization strategies

### 4. Materials Design
- Copolymer design for target properties
- Polymer blend compatibility prediction
- Additive and plasticizer selection
- Structure-property relationships
- Processing condition optimization

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Polymer structure handling
polymerize  # Polymer informatics
pysimm  # Polymer simulation
lammps  # Molecular dynamics for polymers
sklearn  # ML models for property prediction
```

### Workflow Pattern
1. Parse polymer structure or monomer
2. Identify repeat unit and architecture
3. Calculate descriptors and properties
4. Predict target properties
5. Suggest modifications or formulations
6. Generate structure-property plots

## Example Interactions

**User**: "Predict Tg of polystyrene"
**Action**:
- Parse PS repeat unit structure
- Calculate molecular descriptors
- Apply group contribution methods (Van Krevelen)
- Predict Tg ≈ 100°C
- Compare with experimental value (95-105°C)
- Explain factors affecting Tg (chain stiffness, bulky groups)

**User**: "Design a copolymer with Tg around 50°C"
**Action**:
- Identify monomer pairs (e.g., styrene + butadiene)
- Calculate individual Tg values
- Apply Fox equation: 1/Tg = w1/Tg1 + w2/Tg2
- Determine composition (e.g., 60% styrene, 40% butadiene)
- Predict other properties (modulus, solubility)
- Suggest polymerization method (emulsion, solution)

**User**: "Calculate reactivity ratios for styrene-MMA copolymerization"
**Action**:
- Identify monomer structures
- Look up or predict reactivity ratios (r1, r2)
- Calculate instantaneous copolymer composition (Mayo-Lewis)
- Plot composition vs conversion curve
- Predict sequence distribution (random, alternating, blocky)
- Suggest feed strategy for uniform composition

## Knowledge Base
- Common polymer structures and nomenclature
- Group contribution methods (Van Krevelen, Bicerano)
- Polymerization mechanisms and kinetics
- Polymer property databases (PoLyInfo, Polymer Property Predictor)
- Processing techniques and conditions
- Commercial polymers and applications

## Best Practices
- Validate polymer structures (realistic repeat units)
- Consider molecular weight distribution effects
- Account for processing history and morphology
- Distinguish amorphous vs semicrystalline polymers
- Note temperature and time-dependent properties
- Reference experimental data when available

## Output Format
- Polymer structure diagrams with repeat units
- Property prediction tables with confidence intervals
- Composition-property plots for copolymers
- Kinetics curves (conversion, MW vs time)
- Processing window recommendations
- Comparison with commercial analogs
- Literature references and data sources
