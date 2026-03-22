# Flow Chemistry & Continuous Manufacturing

AI toolkit for flow chemistry design, continuous process development, and microreactor optimization.

## Trigger Conditions
Use this skill when:
- User asks about flow chemistry or continuous manufacturing
- Requests microreactor design or optimization
- Needs to convert batch process to continuous flow
- Asks about residence time distribution or plug flow
- Wants to design multi-step flow sequences
- Requests intensification strategies for hazardous reactions

## Core Capabilities

### 1. Flow Reactor Design
- Microreactor geometry and channel design
- Residence time calculation (τ = V/Q)
- Flow regime analysis (laminar vs turbulent)
- Heat transfer in microchannels
- Mixing efficiency (T-mixer, Y-mixer, packed bed)
- Pressure drop and pumping requirements

### 2. Batch-to-Flow Conversion
- Translate batch conditions to flow parameters
- Scale flow rate and reactor volume
- Optimize temperature and concentration
- Handle solids and heterogeneous reactions
- Design inline workup and separation
- Telescoping multi-step sequences

### 3. Process Intensification
- Hazardous reaction containment (small volume)
- High temperature/pressure operation
- Photochemistry with LED arrays
- Electrochemistry in flow
- Gas-liquid reactions (slug flow)
- Cryogenic reactions with precise control

### 4. Continuous Process Optimization
- Residence time distribution (RTD) analysis
- Steady-state operation and control
- Inline analytics and feedback control
- Fouling prevention and cleaning strategies
- Multi-objective optimization (yield, throughput, quality)
- Economic evaluation vs batch

## Implementation Approach

### Python Stack
```python
# Core libraries
scipy  # Flow calculations and optimization
numpy  # Numerical methods
matplotlib  # Flow profiles and RTD plots
fluids  # Fluid mechanics
control  # Process control systems
```

### Workflow Pattern
1. Analyze batch process (reaction time, conditions, issues)
2. Design flow reactor (volume, geometry, materials)
3. Calculate flow parameters (residence time, flow rate)
4. Optimize conditions for continuous operation
5. Design control strategy and inline monitoring
6. Evaluate economics and throughput
7. Plan validation and scale-up

## Example Interactions

**User**: "Convert this 2-hour batch reaction to flow"
**Action**:
- Batch: 100 mL, 2 hours, 80°C, 90% yield
- Target throughput: 1 kg/day product
- Calculate required flow rate: Q = V/τ
- Design reactor: 10 mL coil, τ = 10 min (test shorter residence time)
- Flow rate: 1 mL/min → 1.44 L/day
- Optimize: increase concentration 5x, reduce τ to 10 min
- Result: 10 mL reactor, 1 mL/min, 92% yield (improved heat transfer)
- Recommend: pilot with 50 mL reactor for validation

**User**: "Design flow photochemistry setup for this reaction"
**Action**:
- Reaction requires 365 nm UV light, 1 hour batch irradiation
- Design: FEP tubing (1.6 mm ID) wrapped around LED array
- Calculate: reactor volume 5 mL, residence time 5 min
- LED setup: 365 nm strip, 20 W, uniform irradiation
- Flow rate: 1 mL/min for 5 min residence time
- Advantages: better light penetration, scalable, safer
- Predict: 95% conversion (vs 85% batch) due to uniform irradiation
- Provide: reactor design drawing and LED specifications

**User**: "Why is my flow reactor giving lower yield than batch?"
**Action**:
- Investigate common issues:
  1. Insufficient mixing (check mixer design, Re number)
  2. Residence time too short (verify τ calculation)
  3. Temperature control issues (check heat transfer)
  4. Dispersion (non-ideal flow, dead volumes)
  5. Fouling or precipitation (check inline filters)
- Diagnose: likely insufficient mixing (slow reaction)
- Solution: add static mixer or increase channel turbulence
- Alternative: increase residence time or temperature
- Recommend: RTD study to characterize flow profile

## Knowledge Base
- Flow reactor types (coil, chip, packed bed, tubular)
- Mixing principles in microchannels
- Heat transfer correlations for microreactors
- Flow chemistry applications and case studies
- Commercial flow equipment (Vapourtec, Corning, Ehrfeld)
- Safety advantages of flow chemistry
- Regulatory considerations for continuous manufacturing

## Best Practices
- Start with well-understood batch process
- Use inline analytics for real-time monitoring
- Design for easy cleaning and maintenance
- Consider material compatibility (solvents, reagents)
- Plan for steady-state operation (startup, shutdown)
- Validate with extended runs (>10 residence times)
- Document all operating parameters and deviations

## Output Format
- Flow reactor design specifications (volume, geometry, materials)
- Process parameters (flow rate, temperature, pressure, residence time)
- P&ID with inline analytics and control loops
- RTD curves and flow characterization
- Comparison tables (batch vs flow: yield, throughput, safety, cost)
- Equipment recommendations and suppliers
- Economic analysis (CAPEX, OPEX, payback period)
- Scale-up strategy and validation plan
