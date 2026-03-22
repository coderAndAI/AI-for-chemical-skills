# Chemical Safety & Hazard Assessment

AI toolkit for chemical hazard identification, risk assessment, and process safety management.

## Trigger Conditions
Use this skill when:
- User asks about chemical hazards or safety data
- Requests risk assessment for reactions or processes
- Needs to identify incompatible chemicals
- Asks about thermal stability or runaway reactions
- Wants to design safety systems (relief, containment)
- Requests HAZOP, FMEA, or safety reviews

## Core Capabilities

### 1. Hazard Identification
- Chemical hazard classification (GHS, NFPA)
- Toxicity and exposure limits (LD50, LC50, PEL, TLV)
- Physical hazards (flammability, explosivity, reactivity)
- Incompatibility screening
- Peroxide formers and shock-sensitive compounds
- Carcinogens, mutagens, reproductive toxins

### 2. Thermal Safety Assessment
- Adiabatic temperature rise (ΔTad)
- Time to Maximum Rate (TMR)
- Thermal stability screening (DSC, ARC)
- Runaway reaction scenarios
- Cooling failure analysis
- Decomposition and exotherm prediction

### 3. Process Safety Analysis
- HAZOP (Hazard and Operability Study)
- FMEA (Failure Mode and Effects Analysis)
- Layer of Protection Analysis (LOPA)
- Consequence modeling (dispersion, fire, explosion)
- Inherently safer design principles
- Safety instrumented systems (SIS)

### 4. Risk Mitigation
- Engineering controls (ventilation, containment)
- Administrative controls (procedures, training)
- PPE selection and requirements
- Emergency response planning
- Waste disposal and decontamination
- Regulatory compliance (OSHA, EPA, DOT)

## Implementation Approach

### Python Stack
```python
# Core libraries
rdkit  # Structural alerts and toxicophores
thermo  # Thermodynamic properties
scipy  # Thermal calculations
pandas  # Safety data management
```

### Workflow Pattern
1. Identify all chemicals and reactions
2. Retrieve safety data (SDS, literature)
3. Assess hazards (physical, health, environmental)
4. Calculate thermal risks (ΔTad, TMR)
5. Identify failure modes and consequences
6. Design mitigation measures
7. Document safety case and procedures

## Example Interactions

**User**: "Assess safety of this nitration reaction"
**Action**:
- Identify hazards: HNO3/H2SO4 (corrosive, oxidizer), nitro compounds (explosive)
- Calculate adiabatic temperature rise: ΔTad = ΔHrxn × [substrate] / Cp
- Example: ΔTad = 250°C (highly exothermic, runaway risk)
- Assess: TMR at 80°C = 8 hours (sufficient for batch)
- Recommend controls:
  - Slow addition with temperature monitoring
  - Emergency cooling and quench system
  - Pressure relief sized for runaway scenario
  - Conduct in blast-resistant facility
- Provide: safe operating envelope (T < 60°C, addition rate < 5 mL/min)

**User**: "Check if these chemicals are compatible for storage"
**Action**:
- Chemical A: Acetic anhydride (flammable, corrosive)
- Chemical B: Hydrogen peroxide (oxidizer, unstable)
- Compatibility check: INCOMPATIBLE (oxidizer + organic)
- Risk: violent reaction, fire, explosion
- Recommendation: separate storage (>6 m distance)
- Storage requirements:
  - Acetic anhydride: flammable cabinet, cool, dry
  - H2O2: oxidizer cabinet, cool, dark, vented
- Provide: segregation matrix and storage plan

**User**: "Conduct HAZOP for this batch reactor"
**Action**:
- Define nodes: feed, reactor, cooling, discharge
- Parameters: flow, temperature, pressure, level, composition
- Guide words: more, less, none, reverse, other than
- Example deviations:
  1. "More temperature" → runaway reaction → explosion
     - Causes: cooling failure, exotherm, agitator failure
     - Consequences: overpressure, vessel rupture, toxic release
     - Safeguards: high-T alarm, emergency cooling, relief valve
     - Recommendations: add redundant cooling, SIS for quench
  2. "Less flow" (feed) → incomplete reaction → off-spec product
     - Causes: pump failure, line blockage
     - Consequences: low yield, impurities
     - Safeguards: flow meter with alarm
     - Recommendations: add low-flow interlock
- Provide: complete HAZOP table with action items

## Knowledge Base
- GHS hazard classifications and pictograms
- NFPA diamond ratings (health, flammability, reactivity)
- Chemical incompatibility matrices
- Thermal safety criteria (Stoessel, CCPS guidelines)
- Process safety standards (IEC 61511, ISA 84)
- Incident databases (CSB, ARIA, FACTS)
- Inherently safer design principles (minimize, substitute, moderate, simplify)

## Best Practices
- Always assume worst-case scenarios
- Use multiple layers of protection (defense in depth)
- Prefer inherently safer designs over add-on safety
- Involve safety experts early in development
- Document all safety decisions and rationale
- Train personnel on hazards and emergency procedures
- Review and update safety assessments regularly
- Learn from incidents (internal and industry)

## Output Format
- Hazard summary tables (chemical, physical, health)
- Thermal safety calculations (ΔTad, TMR, cooling capacity)
- HAZOP/FMEA worksheets with risk rankings
- P&ID with safety systems highlighted
- Safe operating procedures (SOPs)
- Emergency response plans
- Risk matrices (likelihood × severity)
- Regulatory compliance checklists
- Training materials and safety briefings
