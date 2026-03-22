# Process Scale-Up & Technology Transfer

AI toolkit for chemical process scale-up from lab to pilot to production, including risk assessment and optimization.

## Trigger Conditions
Use this skill when:
- User needs to scale up from lab (mg) to pilot (kg) to production (ton)
- Asks about scale-up factors and dimensionless numbers
- Requests equipment sizing for different scales
- Needs to identify scale-up risks and bottlenecks
- Wants to optimize process parameters for larger scale
- Asks about technology transfer and manufacturing readiness

## Core Capabilities

### 1. Scale-Up Principles
- Geometric similarity and scale-up ratios
- Dimensionless numbers (Re, Pr, Nu, Gr, We)
- Heat and mass transfer scaling
- Mixing time and power per volume
- Residence time distribution
- Pressure drop and fluid dynamics

### 2. Equipment Sizing
- Reactor volume and geometry (L/D ratio)
- Heat exchanger area and duty
- Agitator design (impeller type, speed, power)
- Pump and piping sizing
- Separation equipment (columns, filters, centrifuges)
- Storage and handling requirements

### 3. Risk Assessment
- Thermal runaway and exotherm management
- Mixing limitations and mass transfer bottlenecks
- Foaming and phase separation issues
- Equipment material compatibility
- Safety hazards at scale (pressure, temperature)
- Quality and yield variability

### 4. Process Optimization
- Parameter screening (DoE, Taguchi methods)
- Critical process parameters (CPPs) identification
- Operating window definition
- Robustness testing
- Cost optimization (raw materials, utilities, labor)
- Cycle time reduction

## Implementation Approach

### Python Stack
```python
# Core libraries
scipy  # Engineering calculations
numpy, pandas  # Data analysis
pyomo  # Process optimization
matplotlib  # Scale-up charts
fluids  # Fluid mechanics calculations
thermo  # Thermodynamic properties
```

### Workflow Pattern
1. Analyze lab-scale data (yields, conditions, issues)
2. Identify scale-dependent parameters
3. Calculate dimensionless numbers
4. Size equipment for target scale
5. Predict scale-up risks
6. Recommend process modifications
7. Define validation experiments

## Example Interactions

**User**: "Scale up this batch reaction from 1L to 100L"
**Action**:
- Analyze lab conditions (T, agitation, addition rate)
- Calculate Reynolds number at both scales
- Determine if mixing regime changes (laminar→turbulent)
- Size agitator (maintain tip speed or P/V)
- Calculate heat transfer requirements (jacket area, cooling capacity)
- Assess addition time scaling (maintain concentration profile)
- Identify risks: exotherm control, mixing time increase
- Recommend: staged addition, improved cooling, pilot run at 10L

**User**: "Why did yield drop from 95% (lab) to 80% (pilot)?"
**Action**:
- Investigate scale-dependent factors
- Check mixing time vs reaction time (Da number)
- Analyze heat transfer (Biot number, temperature gradients)
- Evaluate mass transfer (gas-liquid, solid dissolution)
- Check residence time distribution (bypassing, dead zones)
- Identify likely cause: insufficient mixing or heat removal
- Suggest: increase agitation, improve heat exchanger, optimize feed point

**User**: "Design pilot plant for 50 kg/batch production"
**Action**:
- Calculate reactor volume (accounting for fill level, headspace)
- Size reactor: 200L vessel (L/D = 1.5, jacketed)
- Select agitator: pitched blade turbine, 100 rpm, 2 kW
- Design heat exchanger: 5 m² jacket area, -10°C coolant
- Size pumps and piping (flow rates, pressure drop)
- Specify instrumentation (T, P, pH, level sensors)
- Estimate CAPEX and OPEX
- Provide P&ID and equipment specifications

## Knowledge Base
- Scale-up heuristics and rules of thumb
- Dimensionless number correlations
- Equipment design standards (ASME, API)
- Heat transfer coefficients by system type
- Mixing correlations (Np, Nq, blend time)
- Safety factors for scale-up (1.5-3x)
- Industry case studies and failure modes

## Best Practices
- Always run pilot-scale trials before full production
- Maintain constant dimensionless numbers when possible
- Over-design heat transfer capacity (safety margin)
- Monitor critical parameters continuously
- Document all scale-up assumptions
- Plan for worst-case scenarios (runaway, equipment failure)
- Involve process safety and QA early

## Output Format
- Scale-up calculation tables (lab → pilot → production)
- Equipment specification sheets
- P&ID diagrams with scale comparison
- Risk assessment matrix (likelihood × severity)
- Recommended operating ranges for each scale
- Validation protocol and acceptance criteria
- Cost estimates (CAPEX, OPEX) by scale
- Timeline for technology transfer
