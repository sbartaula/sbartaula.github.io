---
layout: default
title: Case Studies
permalink: /case-studies/
---

<section class="page-header">
  <h1>Case Studies</h1>
  <p>Evidence-first project breakdowns for technical due diligence, hiring panels, and investor review.</p>
</section>

<section class="panel writing-callout">
  <h2>How to read these</h2>
  <p>
    Each case study follows a fixed structure: problem, constraints, architecture, implementation choices,
    measurable behavior, failure modes, and next milestones. The goal is to make execution quality legible.
  </p>
</section>

<section class="project-grid">
  <article class="panel project-card">
    <h2>Tenslam Gym</h2>
    <p class="meta">Stage: Active prototype</p>
    <h3>Scope</h3>
    <p>Real-time motion feedback for everyday workouts on mobile hardware.</p>
    <h3>Evidence pack</h3>
    <ul class="clean-list compact-list signal-list">
      <li>System architecture and core feedback loop</li>
      <li>Latency budget and observed constraints</li>
      <li>Rep-count logic and posture feedback heuristics</li>
      <li>Failure modes with mitigation status</li>
    </ul>
    <p><a class="text-link" href="{{ '/projects/' | relative_url }}">See project overview</a></p>
  </article>

  <article class="panel project-card">
    <h2>Tenslam Vision Motion Engine</h2>
    <p class="meta">Stage: Pipeline development</p>
    <h3>Scope</h3>
    <p>Video-to-structured-motion pipeline for fitness, sports, and physical AI applications.</p>
    <h3>Evidence pack</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Representation design and feature schema</li>
      <li>Signal stability checks across varied conditions</li>
      <li>Downstream integration points and product interfaces</li>
      <li>Data quality risks and reliability roadmap</li>
    </ul>
    <p><a class="text-link" href="{{ '/projects/' | relative_url }}">See project overview</a></p>
  </article>

  <article class="panel project-card">
    <h2>Local LLM Learning Lab</h2>
    <p class="meta">Stage: Ongoing experimentation</p>
    <h3>Scope</h3>
    <p>Local model runtime evaluation under consumer hardware constraints.</p>
    <h3>Evidence pack</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Inference throughput by model and quantization choice</li>
      <li>Memory behavior and usability thresholds</li>
      <li>Prompt/context tradeoff analysis</li>
      <li>Operational implications for product design</li>
    </ul>
    <p><a class="text-link" href="{{ '/writing/' | relative_url }}">See related writing</a></p>
  </article>
</section>

<section class="panel">
  <h2>Case study rubric</h2>
  <p>This is the same rubric I use internally to pressure-test technical quality.</p>
  <table>
    <thead>
      <tr>
        <th>Dimension</th>
        <th>Question</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Technical validity</td>
        <td>Does the system behave consistently under realistic constraints?</td>
      </tr>
      <tr>
        <td>Product utility</td>
        <td>Does the output change user decisions or workflow quality?</td>
      </tr>
      <tr>
        <td>Operational reliability</td>
        <td>Are failure modes measurable, observable, and mitigated?</td>
      </tr>
      <tr>
        <td>Build velocity</td>
        <td>Can the loop from hypothesis to validated iteration run quickly?</td>
      </tr>
      <tr>
        <td>Strategic leverage</td>
        <td>Does this component compound into reusable infrastructure?</td>
      </tr>
    </tbody>
  </table>
</section>
