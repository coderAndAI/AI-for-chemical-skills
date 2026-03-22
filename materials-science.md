# Materials Science & Solid State Chemistry

AI toolkit for materials property prediction, crystal structure analysis, and materials design.

## Trigger Conditions
Use this skill when:
- User mentions crystal structures, unit cells, space groups
- Requests materials property predictions (band gap, conductivity, hardness)
- Asks about phase diagrams or thermodynamic stability
- Needs to analyze XRD, XPS, or other materials characterization data
- Wants to design new materials or alloys
- Requests battery/catalyst/semiconductor materials

## Core Capabilities

### 1. Crystal Structure Analysis
- Parse CIF files and visualize crystal structures
- Calculate lattice parameters and unit cell volumes
- Identify space groups and symmetry operations
- Generate supercells and surfaces
- Analyze coordination environments

### 2. Property Prediction
- Electronic properties (band gap, DOS, band structure)
- Mechanical properties (bulk modulus, hardness, elastic constants)
- Thermal properties (melting point, thermal conductivity)
- Magnetic properties (magnetic moments, ordering)
- Optical properties (absorption, refractive index)

### 3. Materials Design
- High-throughput screening
- Composition optimization
- Defect engineering
- Doping strategies
- Structure-property relationships

### 4. Characterization Data Analysis
- XRD pattern analysis and phase identification
- XPS peak fitting and elemental analysis
- SEM/TEM image analysis
- Raman/FTIR spectral interpretation
- BET surface area calculations

## Implementation Approach

### Python Stack
```python
# Core libraries
pymatgen  # Materials analysis and structure manipulation
ase  # Atomic simulation environment
matminer  # Materials data mining and ML
mp_api  # Materials Project database
jarvis-tools  # JARVIS database access
aflow  # AFLOW database
```

### Workflow Pattern
1. Parse structure (CIF, POSCAR, XYZ)
2. Analyze symmetry and properties
3. Query materials databases
4. Predict properties or screen candidates
5. Visualize results with publication-quality figures

## Example Interactions

**User**: "Analyze this perovskite CIF file"
**Action**:
- Parse CIF structure
- Identify space group (e.g., Pm-3m)
- Calculate lattice parameters
- Visualize 3D structure with polyhedral coordination
- Predict band gap and stability

**User**: "Find cathode materials for Li-ion batteries"
**Action**:
- Query Materials Project for Li-containing compounds
- Filter by voltage window (3-4.5V vs Li/Li+)
- Screen for stability and capacity
- Rank candidates by energy density
- Suggest LiCoO2, LiFePO4, NMC variants

**User**: "Predict band gap of ZnO with Al doping"
**Action**:
- Generate doped structure models
- Calculate electronic structure (DFT or ML model)
- Plot DOS and band structure
- Compare with undoped ZnO
- Suggest optimal doping concentration

## Knowledge Base
- Crystal systems and space groups (230 groups)
- Common structure types (perovskite, spinel, wurtzite, etc.)
- Materials databases (MP, OQMD, AFLOW, JARVIS)
- Characterization techniques and interpretation
- Materials applications (batteries, catalysts, semiconductors)

## Best Practices
- Validate structure files before analysis
- Use standardized primitive cells
- Cross-reference multiple databases
- Consider experimental vs computational data
- Account for temperature and pressure effects
- Cite data sources and computational methods

## Output Format
- Crystal structure visualizations (3D interactive)
- Property tables with units and uncertainties
- Phase diagrams and stability plots
- Comparison charts across materials
- CIF/POSCAR files for further calculations
- Database links and references
