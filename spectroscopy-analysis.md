# Spectroscopy & Analytical Chemistry

AI toolkit for spectroscopic data analysis, peak assignment, and structural elucidation.

## Trigger Conditions
Use this skill when:
- User provides NMR, IR, MS, UV-Vis, or Raman spectra
- Requests peak assignment or spectral interpretation
- Asks about structure elucidation from spectroscopic data
- Needs to predict spectra from molecular structures
- Wants to compare experimental vs theoretical spectra
- Requests quantitative analysis or calibration curves

## Core Capabilities

### 1. NMR Analysis
- 1H/13C NMR peak assignment
- Chemical shift prediction and interpretation
- Coupling constant analysis (J-values, multiplicity)
- Integration and proton counting
- 2D NMR interpretation (COSY, HSQC, HMBC)
- Structure elucidation from NMR data

### 2. Mass Spectrometry
- Molecular ion identification (M+, M+H, M+Na)
- Fragmentation pattern analysis
- Isotope pattern matching
- Accurate mass and formula determination
- MS/MS interpretation
- Protein/peptide sequencing

### 3. Infrared Spectroscopy
- Functional group identification
- Peak assignment (stretching, bending modes)
- Fingerprint region analysis
- Hydrogen bonding effects
- Quantitative analysis (Beer-Lambert)

### 4. UV-Vis & Fluorescence
- Electronic transition assignment (π→π*, n→π*)
- Chromophore identification
- Concentration determination
- Kinetics monitoring
- Fluorescence quantum yield

## Implementation Approach

### Python Stack
```python
# Core libraries
nmrglue  # NMR data processing
pyopenms  # Mass spectrometry analysis
scipy.signal  # Peak detection and fitting
rdkit  # Structure-spectrum prediction
nmrshiftdb2  # NMR database
matplotlib, plotly  # Spectral plotting
```

### Workflow Pattern
1. Load or parse spectral data
2. Perform baseline correction and peak picking
3. Assign peaks to structural features
4. Compare with predicted/reference spectra
5. Propose structure or confirm identity
6. Generate annotated spectra

## Example Interactions

**User**: "Interpret this 1H NMR: peaks at 7.3 (5H), 3.7 (2H), 2.1 (3H) ppm"
**Action**:
- Identify aromatic protons (7.3 ppm, 5H → monosubstituted benzene)
- Assign CH2 adjacent to electron-withdrawing group (3.7 ppm, 2H)
- Identify CH3 group (2.1 ppm, 3H)
- Propose structure: benzyl acetate or similar
- Predict coupling patterns
- Suggest confirming with 13C NMR

**User**: "Analyze this IR spectrum with peaks at 3300, 1650, 1550 cm⁻¹"
**Action**:
- 3300 cm⁻¹: N-H stretch (amide or amine)
- 1650 cm⁻¹: C=O stretch (amide I band)
- 1550 cm⁻¹: N-H bend + C-N stretch (amide II band)
- Conclusion: secondary amide functional group
- Suggest structure contains -CONH- moiety
- Recommend NMR for complete structure

**User**: "Identify compound from MS: M+ = 180, fragments at 152, 107, 77"
**Action**:
- M+ = 180 suggests molecular formula (e.g., C10H12O3)
- Loss of 28 (180→152): CO loss
- Fragment 107: likely C7H7O+ (tropylium-like)
- Fragment 77: C6H5+ (phenyl cation)
- Propose aromatic compound with ester/acid group
- Suggest structure: methyl cinnamate or similar
- Recommend NMR confirmation

## Knowledge Base
- Chemical shift ranges for functional groups
- Characteristic IR absorption frequencies
- Common fragmentation patterns in MS
- UV-Vis absorption maxima for chromophores
- Coupling constant values (3J, 2J)
- Spectroscopic databases and references

## Best Practices
- Consider all spectroscopic data together
- Account for solvent effects on chemical shifts
- Check for impurities and artifacts
- Validate proposed structures with multiple techniques
- Use reference spectra when available
- Report uncertainties and alternative interpretations

## Output Format
- Annotated spectra with peak assignments
- Peak tables (position, intensity, assignment)
- Proposed structures with confidence levels
- Comparison plots (experimental vs predicted)
- Step-by-step interpretation logic
- Alternative structures if ambiguous
- Recommendations for additional experiments
