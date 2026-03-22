# Generative Molecular Design & De Novo Drug Design

AI toolkit for AI-driven molecular generation, optimization, and novel compound design.

## Trigger Conditions
Use this skill when:
- User requests to generate novel molecules with target properties
- Asks for molecular optimization or scaffold hopping
- Needs to explore chemical space systematically
- Wants to design molecules for specific applications
- Requests multi-objective molecular optimization
- Asks about generative models (VAE, GAN, Transformer, Diffusion)

## Core Capabilities

### 1. Generative Models
- SMILES-based generation (RNN, Transformer, GPT)
- Graph-based generation (GraphVAE, MoFlow)
- Fragment-based assembly
- Scaffold decoration and R-group enumeration
- Conditional generation with property constraints
- Diffusion models for 3D structure generation

### 2. Molecular Optimization
- Property-guided optimization (logP, QED, SA score)
- Multi-objective optimization (Pareto frontier)
- Constrained optimization (substructure preservation)
- Reinforcement learning for molecule design
- Genetic algorithms and evolutionary strategies
- Bayesian optimization in chemical space

### 3. Chemical Space Exploration
- Latent space interpolation
- Neighborhood sampling around lead compounds
- Diversity-oriented synthesis planning
- Novelty scoring and patent checking
- Synthesizability assessment
- Chemical space visualization (t-SNE, UMAP)

### 4. Application-Specific Design
- Drug-like molecule generation (Lipinski compliance)
- Materials design (polymers, MOFs, catalysts)
- Agrochemical design (pesticides, herbicides)
- Fragrance and flavor molecules
- PROTAC and molecular glue design
- Peptide and macrocycle generation

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Molecular manipulation
moses  # Molecular generation benchmarks
guacamol  # Generation evaluation
selfies  # Robust molecular representation
torch, tensorflow  # Deep learning frameworks
reinvent  # RL-based molecular design
```

### Workflow Pattern
1. Define target properties and constraints
2. Select or train generative model
3. Generate candidate molecules
4. Filter by drug-likeness and synthesizability
5. Predict properties and rank candidates
6. Validate top candidates with detailed calculations
7. Suggest synthesis routes

## Example Interactions

**User**: "Generate kinase inhibitors with MW < 400 and logP < 3"
**Action**:
- Load pre-trained kinase-focused generative model
- Set property constraints (MW, logP, kinase pharmacophore)
- Generate 1000 candidates
- Filter by Lipinski rules and PAINS
- Predict kinase binding affinity
- Rank by multi-parameter optimization score
- Return top 20 with predicted properties and synthesis routes

**User**: "Optimize this lead compound for better BBB penetration"
**Action**:
- Parse lead structure
- Identify optimization objectives (increase logP, reduce TPSA, maintain activity)
- Generate analogs via scaffold hopping and R-group substitution
- Predict BBB permeability (log BB, P-gp substrate)
- Calculate CNS MPO score
- Suggest modifications (reduce HBD, add lipophilic groups)
- Rank optimized candidates

**User**: "Design novel MOF linkers for CO2 capture"
**Action**:
- Define linker requirements (rigid, aromatic, carboxylate groups)
- Generate candidates with constrained generation
- Calculate geometric properties (length, angle, rigidity)
- Predict CO2 binding affinity
- Assess synthetic accessibility
- Suggest metal nodes and topology
- Rank by predicted CO2 uptake capacity

## Knowledge Base
- Generative model architectures and training strategies
- Molecular representations (SMILES, SELFIES, graphs)
- Property prediction models
- Synthesizability scoring (SA score, SCScore)
- Chemical space metrics (Tanimoto, FCD, FID)
- Benchmark datasets (ZINC, ChEMBL, QM9)

## Best Practices
- Validate generated molecules (valid SMILES, stable structures)
- Check for known toxicophores and reactive groups
- Assess synthetic accessibility early
- Use diverse training data to avoid mode collapse
- Balance exploration vs exploitation
- Verify novelty against patent databases
- Prioritize experimentally testable candidates

## Output Format
- Generated molecule structures (2D/3D)
- Property prediction tables with confidence
- Synthesizability scores and retrosynthetic routes
- Novelty assessment (Tanimoto to known compounds)
- Chemical space visualization
- Ranked candidate lists with rationale
- Suggested next steps for validation
