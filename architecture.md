---
layout: page
title: "Architecture Design Topology"
permalink: /architecture/
---

### Multi-Tile Grid Organization

MoSAIC scales systematically across a 2D mesh grid layout ($r \times c$). Communication boundaries bypass processing resource starvation nodes via explicit message routing fabrics.

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
