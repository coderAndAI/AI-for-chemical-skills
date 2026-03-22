# Chemical Process Simulation & Optimization

AI toolkit for chemical engineering process design, simulation, and optimization.

## Trigger Conditions
Use this skill when:
- User needs process flow diagrams (PFD) or P&ID design
- Requests mass/energy balance calculations
- Asks about reactor design or kinetics modeling
- Needs distillation, absorption, or separation design
- Wants process optimization or sensitivity analysis
- Requests heat exchanger or equipment sizing

## Core Capabilities

### 1. Process Simulation
- Mass and energy balances
- Phase equilibrium calculations (VLE, LLE)
- Thermodynamic property estimation
- Unit operation modeling (reactors, separators, heat exchangers)
- Flowsheet simulation and convergence

### 2. Reactor Design
- Batch, CSTR, PFR modeling
- Reaction kinetics and rate equations
- Heat transfer and temperature profiles
- Residence time distribution
- Catalyst deactivation models

### 3. Separation Processes
- Distillation column design (McCabe-Thiele, Fenske-Underwood)
- Absorption and stripping
- Extraction and crystallization
- Membrane separation
- Adsorption isotherms

### 4. Process Optimization
- Objective function definition (cost, yield, energy)
- Constraint handling (safety, environmental)
- Sensitivity analysis
- Pinch analysis for heat integration
- Economic evaluation (CAPEX, OPEX)

## Implementation Approach

### Python Stack
```python
# Core libraries
thermo  # Thermodynamic property calculations
chemicals  # Chemical property database
scipy.optimize  # Optimization algorithms
numpy, pandas  # Numerical computing
matplotlib  # Process diagrams and plots
cantera  # Chemical kinetics and thermodynamics
```

### Workflow Pattern
1. Define process specifications
2. Set up material and energy balances
3. Calculate thermodynamic properties
4. Simulate unit operations
5. Optimize process parameters
6. Generate reports and diagrams

## Example Interactions

**User**: "Design a distillation column to separate benzene-toluene"
**Action**:
- Calculate VLE data (Raoult's law or activity models)
- Determine minimum reflux ratio (Underwood)
- Calculate theoretical stages (Fenske or McCabe-Thiele)
- Size column diameter and height
- Estimate reboiler and condenser duties
- Calculate operating costs

**User**: "Optimize CSTR for esterification reaction"
**Action**:
- Define reaction kinetics (A + B ⇌ C + D)
- Set up mass balance equations
- Calculate residence time for target conversion
- Optimize temperature for maximum yield
- Consider equilibrium limitations
- Suggest reactor volume and cooling requirements

**User**: "Perform mass balance for ammonia synthesis plant"
**Action**:
- Parse process flowsheet (N2, H2 feeds, recycle)
- Calculate stoichiometric ratios
- Account for purge stream
- Determine fresh feed requirements
- Calculate product yield and selectivity
- Generate material balance table

## Knowledge Base
- Thermodynamic models (Peng-Robinson, NRTL, UNIQUAC)
- Unit operation design equations
- Chemical property databases
- Process safety guidelines
- Economic evaluation methods
- Industry standards (ASME, API)

## Safety & Best Practices
- Check operating conditions (P, T limits)
- Identify hazardous materials and conditions
- Consider pressure relief and safety systems
- Evaluate environmental impact
- Include safety factors in design
- Reference relevant codes and standards

## Output Format
- Process flow diagrams (PFD)
- Material and energy balance tables
- Equipment specification sheets
- Operating condition summaries
- Cost estimation breakdowns
- Optimization results with sensitivity plots
- Design recommendations with justifications
