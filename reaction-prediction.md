# Chemical Reaction Prediction & Retrosynthesis

AI-powered toolkit for predicting reaction outcomes, suggesting synthetic routes, and optimizing reaction conditions.

## Trigger Conditions
Use this skill when:
- User asks to predict reaction products
- Requests retrosynthetic analysis or synthetic routes
- Needs reaction condition recommendations
- Wants to balance chemical equations
- Asks about reaction mechanisms or feasibility
- Requests yield prediction or optimization

## Core Capabilities

### 1. Forward Reaction Prediction
- Predict major and minor products
- Estimate reaction feasibility
- Suggest optimal conditions (temp, solvent, catalyst)
- Identify competing pathways
- Balance equations automatically

### 2. Retrosynthetic Analysis
- Generate synthetic routes from target molecule
- Suggest starting materials and reagents
- Multi-step synthesis planning
- Commercial availability checks
- Route scoring and ranking

### 3. Reaction Classification
- Identify reaction types (substitution, addition, elimination, etc.)
- Recognize named reactions (Diels-Alder, Grignard, etc.)
- Mechanism prediction
- Functional group transformations

### 4. Condition Optimization
- Solvent selection based on polarity/reactivity
- Temperature and pressure recommendations
- Catalyst suggestions
- Workup procedures

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Reaction SMARTS and transformations
rxnmapper  # Atom mapping
chembl_structure_pipeline  # Standardization
```

### Workflow Pattern
1. Parse reactants (SMILES/structures)
2. Apply reaction templates or ML models
3. Generate products with stereochemistry
4. Rank by likelihood/feasibility
5. Suggest conditions and references

## Example Interactions

**User**: "What happens when benzene reacts with Br2 and FeBr3?"
**Action**:
- Identify electrophilic aromatic substitution
- Predict bromobenzene as major product
- Explain mechanism with FeBr3 as Lewis acid catalyst
- Suggest conditions: room temp, no light

**User**: "Design synthesis for ibuprofen"
**Action**:
- Retrosynthetic analysis from target
- Suggest 3-step route from isobutylbenzene
- Friedel-Crafts acylation → reduction → carboxylation
- List reagents and conditions for each step
- Estimate overall yield

**User**: "Will this Grignard reaction work in water?"
**Action**:
- Identify incompatibility (Grignard + H2O → alkane)
- Explain why reaction fails
- Suggest anhydrous conditions
- Recommend alternative if needed

## Knowledge Base
- Common reaction templates (>1000 patterns)
- Named reactions database
- Solvent properties and compatibility
- Reagent reactivity and selectivity
- Literature precedents

## Safety & Best Practices
- Flag hazardous reagents (pyrophoric, toxic, explosive)
- Warn about incompatible combinations
- Suggest safer alternatives when available
- Include proper PPE and handling notes
- Reference safety data sheets

## Output Format
- Reaction schemes with structures
- Step-by-step mechanisms
- Condition tables (temp, time, solvent, catalyst)
- Expected yields and selectivity
- Literature references
- Safety warnings highlighted
