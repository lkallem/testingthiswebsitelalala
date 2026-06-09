# SOP: Self-Contained Deployment Strategy for MoSAIC P-38 Website
**Target Theme:** Bulma Clean Theme (`chrisrhymes/bulma-clean-theme`)
**Branding Standard:** Lawrence Berkeley National Laboratory (LBNL) Visual Identity System
**Layout Style:** Columbia ESP Portal Emulation (`esp.cs.columbia.edu`)
**Target Project:** MoSAIC P-38 (Modular System for Acceleration Integration)

---

## 1. Directory Structure Blueprint
The agent must construct the workspace to match this exact layout. Do not omit any directories or files.

```text
.
├── _config.yml
├── Gemfile
├── _data/
│   └── navigation.yml
├── assets/
│   ├── css/
│   │   └── app.scss
│   └── images/
│       └── lbnl-logo.svg
├── index.md
├── architecture.md
├── getting-started.md
├── docs.md
└── team.md
```

---

## 2. Environment Configurations

### 2.1 File: `_config.yml`
```yaml
title: "MoSAIC P-38"
subtitle: "Modular System for Acceleration Integration"
description: "A multi-tiled architecture for fast exploration of message-driven computation developed at Lawrence Berkeley National Laboratory."
url: "https://lbnlcomputerarch.github.io"
baseurl: "/MoSAIC-P38"

remote_theme: chrisrhymes/bulma-clean-theme@v0.14.0

plugins:
  - jekyll-seo-tag
  - jekyll-paginate

author: "Lawrence Berkeley National Laboratory"
logo: "/assets/images/lbnl-logo.svg"
show_sidebar: false

paginate: 5
paginate_path: "/blog/page:num/"
sass:
  style: :compressed
```

### 2.2 File: `Gemfile`
```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.3"
gem "jekyll-remote-theme"
gem "jekyll-seo-tag"
gem "jekyll-paginate"
gem "webrick" # Ensures compatibility with modern Ruby runtimes
```

---

## 3. Asset & Styling Injection Layers

### 3.1 File: `assets/images/lbnl-logo.svg`
Write this raw inline SVG code to disk to serve as the authorized brand anchor asset in the navbar.
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 60" width="400" height="60">
  <rect width="100%" height="100%" fill="#00313C"/>
  <text x="20" y="38" font-family="Helvetica, Arial, sans-serif" font-size="24" font-weight="bold" fill="#ffffff">BERKELEY LAB</text>
  <text x="210" y="36" font-family="Helvetica, Arial, sans-serif" font-size="12" fill="#84BD00">MoSAIC P-38 ARCHITECTURE</text>
</svg>
```

### 3.2 File: `assets/css/app.scss`
```scss
---
---
// LBNL Official Visual Identity Specifications
$lbnl-dark-blue:  #00313C; // PMS 547 (Primary Brand Base)
$lbnl-teal:       #007681; // PMS 7474 (Interaction/Links)
$lbnl-light-gray: #B1B3B3; // PMS Cool Gray 5 (Borders/Dividers)
$lbnl-dark-gray:  #63666A; // PMS Cool Gray 10 (Body Copy Accent)
$lbnl-bright-grn: #84BD00; // PMS 376 (Hover Accents)

// Bulma Engine Framework Overrides
$primary:           $lbnl-teal;
$link:              $lbnl-teal;
$link-hover:        darken($lbnl-teal, 10%);
$dark:              $lbnl-dark-blue;
$text:              #212529; 
$border:            $lbnl-light-gray;

// Typography Directives
$font-family-sans-serif: "Helvetica Neue", Helvetica, Arial, sans-serif;
$body-family:            $font-family-sans-serif;
$title-family:           $font-family-sans-serif;

// Columbia ESP Navbar Emulation Rules
$navbar-background-color:           $lbnl-dark-blue;
$navbar-item-color:                 #ffffff;
$navbar-item-hover-color:           $lbnl-bright-grn;
$navbar-item-hover-background-color: transparent;
$navbar-item-active-color:          #ffffff;
$navbar-item-img-max-height:        3.0rem;

@import "main";

// Code and Syntax Highlighting Adjustments
pre, code {
  font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace;
  background-color: #f8f9fa;
  border: 1px solid $lbnl-light-gray;
  border-radius: 4px;
  color: #d33939;
}
pre code {
  color: #212529;
}
```

---

## 4. Navigation Architecture Mapping

### 4.1 File: `_data/navigation.yml`
```yaml
- name: "Home"
  link: "/"
- name: "Architecture"
  link: "/architecture/"
- name: "Getting Started"
  link: "/getting-started/"
- name: "Documentation"
  link: "/docs/"
- name: "Team"
  link: "/team/"
```

---

## 5. Site Content Markdown Generation

### 5.1 File: `index.md`
```markdown
---
layout: page
title: "MoSAIC P-38"
subtitle: "Modular System for Acceleration Integration"
---

<section class="section px-0 py-4">
  <div class="container">
    <div class="notification is-light" style="border-left: 4px solid #007681; background-color: #fafafa;">
      <p class="is-size-5">
        <strong>MoSAIC P-38</strong> is an advanced, multi-tiled heterogeneous hardware architecture built for fast and accurate exploration of message-driven computation workloads.
      </p>
    </div>
  </div>
</section>

<div class="columns is-variable is-8">
  <div class="column is-7">
    <h3 class="title is-4" style="color: #00313C;">System-Level Highlights</h3>
    <p>
      Developed by the Lawrence Berkeley National Laboratory Computer Architecture group, MoSAIC delivers an extensible grid ecosystem optimized for hardware accelerator deployment.
    </p>
    <div class="content">
      <ul>
        <li><strong>Multi-Tiled Topology:</strong> Supports customizable grid dimensions structured mapping arbitrary row/column nodes.</li>
        <li><strong>RISC-V Core Integration:</strong> Native compute layers containing decoupled processing pipelines paired directly to accelerators.</li>
        <li><strong>Network-on-Chip (NoC):</strong> High-throughput standard <code>AXIStream</code> transaction routing matrix.</li>
        <li><strong>Message Queues:</strong> Low-overhead dedicated hardware handling loops inside individual tiles.</li>
      </ul>
    </div>
  </div>

  <div class="column is-5" style="border-left: 1px solid #B1B3B3;">
    <h3 class="title is-4" style="color: #00313C;">Ecosystem Resources</h3>
    <div class="box" style="box-shadow: none; border: 1px solid #B1B3B3;">
      <span class="tag is-primary" style="background-color: #007681;">Source Code</span>
      <p class="mt-2 is-size-6">Access the complete hardware description environment and RTL layout tracks on GitHub.</p>
      <a class="button is-small is-link mt-2" href="https://github.com/lbnlcomputerarch/MoSAIC-P38" target="_blank">View Repository</a>
    </div>
    <div class="box" style="box-shadow: none; border: 1px solid #B1B3B3;">
      <span class="tag is-dark" style="background-color: #00313C;">Deployment Focus</span>
      <p class="mt-2 is-size-6">Tailored for scientific exploration workloads under standard Verilog and SystemVerilog tooling streams.</p>
    </div>
  </div>
</div>
```

### 5.2 File: `architecture.md`
```markdown
---
layout: page
title: "Architecture Design Topology"
permalink: /architecture/
---

### Multi-Tile Grid Organization

MoSAIC scales systematically across a 2D mesh grid layout ($r 	imes c$). Communication boundaries bypass processing resource starvation nodes via explicit message routing fabrics.

```
                  ┌──────────────────────┐
                  │   AXIStream NoC      │
                  └──────────▲───────────┘
                             │
            ┌────────────────▼────────────────┐
            │            MoSAIC Tile          │
            │  ┌────────────┐   ┌──────────┐  │
            │  │  PicoRV32  │   │ Hardware │  │
            │  │ Processor /│   │ Message  │  │
            │  │ Accelerator│   │  Queue   │  │
            │  └────────────┘   └──────────┘  │
            └─────────────────────────────────┘
```

#### Node Interconnect Features
1. **Compute Element Layer:** Embeds modular RISC-V compute microarchitectures or customized hardware blocks.
2. **Asynchronous Handshaking:** De-couples functional units from strict structural network latency via hardware message buffers.
3. **NoC Routing Protocol:** Implements deterministic dimensional layout algorithms to preserve packet ordering rules.
```

### 5.3 File: `getting-started.md`
```markdown
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
```

### 5.4 File: `docs.md`
```markdown
---
layout: page
title: "Technical Documentation"
permalink: /docs/
---

### MoSAIC P-38 Interface and Registry Specification

#### Memory Map Organization
Individual tiles maintain localized code/scratchpad visibility windows. External structural synchronization steps pass through memory-mapped IO registers.

| Base Register Address | Scope / Boundary Access | Core Functional Parameter |
|-----------------------|-------------------------|---------------------------|
| `0x40000000`          | Read/Write Access       | Network Packet Payload Out|
| `0x40000004`          | Read-Only State         | Incoming Buffer Length    |
| `0x40000008`          | Read/Write Control      | Tile Status Configuration |

#### Toolchain Compiler Prerequisites
To construct and emit valid target binary executable files compatibility layers, ensure your developer workstation includes:
* **RISC-V GNU Toolchain** (`riscv32-unknown-elf-gcc`)
* **Icarus Verilog** v11.0 or newer (or alternative SystemVerilog compliant simulator)
* **Perl Core Framework Interconnects**
```

### 5.5 File: `team.md`
```markdown
---
layout: page
title: "Project Team"
permalink: /team/
---

### Computer Architecture Group - Lawrence Berkeley National Laboratory

The MoSAIC architecture project is an open-source research initiative spearheaded by the LBNL Computer Architecture Laboratory.

#### Principal Collaborators

* **Research Architecture Leads**
  * Exploration and framework infrastructure planning.
  * Integration design layers and verification.
  * Network-on-Chip protocol development trackers.

For collaboration inquiries, technical feedback, or system integration issues, please engage through the project's primary public codebase tracking platforms.
```

---

## 6. Commands to Validate and Serve Locally
The agent or developer should issue these commands in sequence to check code integration safety before push processes.

```bash
# Step 1: Install dependencies locally
bundle install

# Step 2: Compile assets and run the web engine server
bundle exec jekyll serve --livereload
```
The site will become active locally at `http://127.0.0.1:4000/MoSAIC-P38/`. Validate element presentation metrics against the design checklists before concluding deployment operations.
