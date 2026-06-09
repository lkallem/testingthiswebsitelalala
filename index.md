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
