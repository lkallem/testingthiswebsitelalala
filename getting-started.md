---
layout: page
title: "Getting Started Guide"
permalink: /getting-started/
---

### Environment Deployment and Testcase Generation

Follow these execution parameters to build a design target profile configuration and instantiate simulation passes.

#### Step 1: Establish Environment Matrix
Construct an execution runtime properties script within your generation tooling folders (e.g., `mosaic_2x2.pl`):

```perl
# Grid Matrix Proportions
$param{'r'} = 2; 
$param{'c'} = 2; 

# Map Tile Configuration Layout
@tile_array = (['pico', 'spad'], ['loop', 'pico']);

# Track Target Application Execution Blobs
@pico_program = ('pico_scratchpad.hex', '', '', 'test_tile_nop.hex');

$param{'run_sim'} = 1;
```

#### Step 2: Execute Simulation Compilation Pipeline
Trigger the local compilation wrapper directly using your terminal interface:

```bash
cd tools/generate/
perl ./mosaic_2x2.pl
```
The generator builds SystemVerilog configuration arrays and proceeds to run validation passes within your local target environment framework.
