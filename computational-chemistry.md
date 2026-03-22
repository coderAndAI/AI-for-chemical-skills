# Computational Chemistry & Quantum Calculations

AI toolkit for quantum chemistry calculations, molecular dynamics simulations, and computational property predictions.

## Trigger Conditions
Use this skill when:
- User requests DFT, HF, or post-HF calculations
- Needs geometry optimization or conformer search
- Asks about molecular orbitals, HOMO/LUMO, band gaps
- Requests energy calculations or thermochemistry
- Wants to run molecular dynamics simulations
- Needs to generate input files for quantum chemistry software

## Core Capabilities

### 1. Quantum Chemistry Setup
- Generate input files (Gaussian, ORCA, Psi4, Q-Chem)
- Select appropriate methods (DFT functionals, basis sets)
- Set up geometry optimizations
- Configure frequency calculations
- Transition state searches

### 2. Property Predictions
- Electronic properties (HOMO/LUMO, ionization potential)
- Spectroscopic properties (UV-Vis, IR, NMR)
- Thermodynamic properties (ΔH, ΔG, ΔS)
- Reaction barriers and transition states
- Excited state calculations (TD-DFT)

### 3. Molecular Dynamics
- Setup MD simulations (GROMACS, AMBER, LAMMPS)
- Force field selection and parameterization
- Solvation models (implicit/explicit)
- Trajectory analysis
- Free energy calculations

### 4. Results Analysis
- Parse output files from QM software
- Visualize molecular orbitals
- Plot energy diagrams
- Analyze vibrational modes
- Generate publication-quality figures

## Implementation Approach

### Python Stack
```python
# Core libraries
psi4  # Quantum chemistry calculations
ase  # Atomic simulation environment
cclib  # Parse QM output files
mdanalysis  # MD trajectory analysis
py3Dmol  # 3D visualization
matplotlib, plotly  # Plotting
```

### Workflow Pattern
1. Parse molecular structure
2. Select computational method and basis set
3. Generate input file or run calculation
4. Parse results
5. Visualize and interpret data

## Example Interactions

**User**: "Optimize caffeine geometry with DFT"
**Action**:
- Generate 3D structure from SMILES
- Create Psi4/ORCA input (B3LYP/6-31G*)
- Run geometry optimization
- Extract optimized coordinates
- Calculate energy and dipole moment
- Visualize optimized structure

**User**: "Calculate HOMO-LUMO gap for benzene"
**Action**:
- Setup single-point calculation
- Extract frontier orbital energies
- Calculate band gap (eV)
- Visualize HOMO and LUMO orbitals
- Compare with experimental value

**User**: "Predict IR spectrum for acetone"
**Action**:
- Optimize geometry
- Run frequency calculation
- Extract vibrational modes and intensities
- Plot IR spectrum
- Assign major peaks (C=O stretch ~1715 cm⁻¹)

## Method Selection Guide
- **Quick screening**: Semi-empirical (PM7, GFN2-xTB)
- **Standard DFT**: B3LYP/6-31G(d,p) or ωB97X-D/def2-TZVP
- **High accuracy**: CCSD(T) or MP2 with large basis sets
- **Large systems**: Force fields (MMFF94, UFF, GAFF)
- **Transition metals**: M06, PBE0 with appropriate basis sets

## Best Practices
- Always optimize geometry before property calculations
- Use appropriate basis sets (polarization, diffuse functions)
- Consider solvent effects (PCM, SMD models)
- Verify convergence criteria
- Compare with experimental data when available
- Cite computational methods properly

## Output Format
- Calculation summary (method, basis, energy)
- Optimized coordinates (XYZ format)
- Property tables with units
- Orbital diagrams and energy levels
- Spectral plots with peak assignments
- Input/output files for reproducibility
