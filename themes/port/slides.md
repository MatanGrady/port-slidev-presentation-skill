---
theme: ./
title: Port Theme Test
layout: cover
---

# Port product overview

<Subtitle>Session for HR team | February 17, 2026</Subtitle>

<ColorDots />

---

# Agenda

<Grid cols="2">
  <div class="space-y-4">
    <AgendaItem icon="🏢" color="blue">Who we are</AgendaItem>
    <AgendaItem icon="🔥" color="pink">The problem we solve</AgendaItem>
    <AgendaItem icon="💡" color="green">The solution</AgendaItem>
  </div>
  <div class="space-y-4">
    <AgendaItem icon="👥" color="purple">R&D team structure</AgendaItem>
    <AgendaItem icon="⚙️" color="yellow">Tech stack</AgendaItem>
    <AgendaItem icon="✨" color="orange">What makes Port R&D unique</AgendaItem>
  </div>
</Grid>

---
layout: section
number: "01"
---

# Who we are

<Subtitle>Port at a glance</Subtitle>

---

# Engineering chaos

<Subtitle>Modern cloud-native environments created complexity</Subtitle>

<Grid cols="3">
  <MetricCard value="1000+" label="Microservices" />
  <MetricCard value="10k" label="Cloud resources" />
  <MetricCard value="7" label="Observability tools" />
  <MetricCard value="6" label="Security tools" />
  <MetricCard value="1500" label="Repos" />
  <MetricCard value="∞" label="Environments" />
</Grid>

<ImpactBox center class="mt-6">
  Developers move between dozens of tools, ask for permissions, search for missing information
</ImpactBox>

---

# Port orchestrates people, agents, and tools

<Grid cols="3">
  <FeatureCard icon="👥" title="For technical teams" color="blue">
    Developers, SREs, security engineers, managers
    <template #tags>
      <Tag color="purple">Human-agent collaboration</Tag>
    </template>
  </FeatureCard>
  <FeatureCard icon="🤖" title="For AI agents" color="pink">
    Claude, Cursor, Copilot, etc.
    <template #tags>
      <Tag color="blue">Context Lake</Tag>
      <Tag color="green">AI guardrails</Tag>
    </template>
  </FeatureCard>
  <FeatureCard icon="⚙️" title="Platform engineers" color="green">
    Define all autonomous workflows
    <template #tags>
      <Tag color="purple">Governance</Tag>
      <Tag color="blue">Velocity</Tag>
    </template>
  </FeatureCard>
</Grid>

---

# What does this mean?

<Grid cols="3">
  <StepItem n="1" title="Context Lake">
    Agents get organizational context to make the right decisions
  </StepItem>
  <StepItem n="2" title="Governed Actions">
    Agents operate within organizational guardrails and standards
  </StepItem>
  <StepItem n="3" title="Human-AI Collaboration">
    Teams can approve, review, and oversee what agents are doing
  </StepItem>
</Grid>

---

# Steps layout: 2x2 variation

<Grid cols="2" class="max-w-3xl mx-auto">
  <StepItem n="1" title="Discovery">
    Understand customer problems through continuous research
  </StepItem>
  <StepItem n="2" title="Definition">
    Define solutions with clear success metrics
  </StepItem>
  <StepItem n="3" title="Delivery">
    Build and ship incrementally with feedback loops
  </StepItem>
  <StepItem n="4" title="Iteration">
    Measure, learn, and improve based on outcomes
  </StepItem>
</Grid>

---

# Tags demo

<div class="flex flex-wrap gap-2">
  <Tag color="blue">Context Lake</Tag>
  <Tag color="purple">Human-agent collaboration</Tag>
  <Tag color="green">AI guardrails</Tag>
  <Tag color="pink">Governance</Tag>
  <Tag color="yellow">Velocity</Tag>
  <Tag color="orange">Platform</Tag>
  <Tag color="dark">Dark tag</Tag>
</div>
