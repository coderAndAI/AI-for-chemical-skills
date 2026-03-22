# AspenPlus Process Simulation

Use this skill when users want to work with Aspen Plus process simulations, including running simulations, modifying flowsheets, reading/writing process data, or building chemical process models.

## Triggers
- "run aspen simulation"
- "modify aspen flowsheet"
- "add equipment to aspen"
- "get stream data from aspen"
- "create process simulation"
- "aspen plus calculation"
- Any mention of Aspen Plus, process simulation, or chemical engineering calculations

## Prerequisites
- Windows OS with Aspen Plus installed
- AspenPlus MCP Server configured in Claude Desktop
- Simulation files (.bkp or .apw format)

## Core Capabilities

### 1. Basic Simulation Operations
- Open and close simulation files
- Run simulations and check convergence
- Read process data (temperatures, pressures, flow rates, compositions)
- Modify input parameters (feed conditions, equipment specs)

### 2. Enhanced Flowsheet Editing
- Add equipment blocks (Mixer, Heater, Flash2, Radfrac, Pump, etc.)
- Create material and energy streams
- Connect streams to equipment ports
- Delete blocks and streams
- Save modified simulations

## Workflow Patterns

### Pattern 1: Parameter Study
```
1. Open simulation
2. Set input parameters
3. Run simulation
4. Extract results
5. Repeat for different conditions
6. Close simulation
```

### Pattern 2: Flowsheet Modification
```
1. Open simulation (enhanced mode)
2. Add/remove equipment blocks
3. Create streams
4. Connect streams to blocks
5. Save simulation
6. Run and verify
```

## Node Path Structure

Aspen Plus uses hierarchical paths to access data:

**Stream Properties:**
- Temperature: `\\Data\\Streams\\[NAME]\\Output\\TEMP_OUT\\MIXED`
- Pressure: `\\Data\\Streams\\[NAME]\\Output\\PRES_OUT\\MIXED`
- Flow rate: `\\Data\\Streams\\[NAME]\\Output\\MASSFLMX\\MIXED`
- Composition: `\\Data\\Streams\\[NAME]\\Output\\MOLEFRAC\\MIXED\\[COMPONENT]`

**Block Parameters:**
- Heater duty: `\\Data\\Blocks\\[NAME]\\Input\\QCALC`
- Flash temperature: `\\Data\\Blocks\\[NAME]\\Input\\TEMP`
- Column stages: `\\Data\\Blocks\\[NAME]\\Input\\NSTAGE`

**Input vs Output:**
- Use `\\Input\\` for setting parameters
- Use `\\Output\\` for reading results

## Equipment Types

Common equipment blocks:
- `Mixer` - Stream mixing
- `Heater` - Heating/cooling
- `Flash2` - Flash separation
- `Radfrac` - Distillation column
- `Pump` - Pressure increase
- `Valve` - Pressure reduction
- `HeatX` - Heat exchanger
- `Sep` - Component separator

## Stream Types
- `MATERIAL` - Material streams
- `HEAT` - Energy streams
- `WORK` - Work streams

## Best Practices

1. **Always use absolute paths** for file locations on Windows
2. **Check simulation convergence** after running
3. **Use enhanced mode** only when modifying flowsheet structure
4. **Save frequently** when making multiple changes
5. **Close simulations** when done to free resources
6. **Handle errors gracefully** - simulations may not converge

## Error Handling

Common issues:
- Simulation not converging → Check input specs and initial estimates
- Path not found → Verify node path syntax and component names
- COM errors → Ensure Aspen Plus is properly installed
- File access errors → Use absolute paths with proper escaping

## Example Workflows

### Example 1: Temperature Sensitivity Study
```
User: "Run my distillation simulation at different feed temperatures from 20°C to 80°C"

Steps:
1. open_simulation with file path
2. Loop through temperatures:
   - set_value for feed temperature
   - run_simulation
   - get_value for key outputs (top/bottom compositions)
3. Compile results
4. close_simulation
```

### Example 2: Add Heat Exchanger
```
User: "Add a heat exchanger to cool stream S1 before the reactor"

Steps:
1. open_simulation (enhanced mode)
2. place_block (HeatX type)
3. place_stream for outlet
4. connect_stream (S1 to HX inlet)
5. connect_stream (HX outlet to reactor)
6. set_value for outlet temperature
7. save_simulation
8. run_simulation to verify
```

## Tips for Users

- Provide full file paths to simulation files
- Specify exact stream/block names from your flowsheet
- Indicate whether you need basic operations or flowsheet modifications
- Mention specific properties you want to read/write
- State convergence criteria if non-standard

## Limitations

- Windows-only (COM interface requirement)
- Requires Aspen Plus license
- Enhanced mode may be slower for large flowsheets
- Some advanced Aspen features may not be accessible via MCP

## When NOT to Use This Skill

- User wants general chemical engineering calculations (use Python/SciPy instead)
- Non-Windows environment
- Aspen Plus not installed
- Working with other simulation software (HYSYS, ProMax, etc.)
