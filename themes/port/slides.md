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

---

# Product pillars

<Grid cols="3" gap="4">
  <FeatureCard icon="📚" title="Software Catalog" color="blue" variant="pillar">
    Central source of truth for all engineering assets
  </FeatureCard>
  <FeatureCard icon="📊" title="Scorecards" color="green" variant="pillar">
    Measure and track standards compliance
  </FeatureCard>
  <FeatureCard icon="⚡" title="Actions" color="pink" variant="pillar">
    Self-service operations with guardrails
  </FeatureCard>
  <FeatureCard icon="🔄" title="Workflow Orchestrator" color="purple" variant="pillar">
    Event-driven automation chains
  </FeatureCard>
  <FeatureCard icon="🤖" title="AI Agents" color="yellow" variant="pillar">
    Autonomous workflows with human oversight
  </FeatureCard>
  <FeatureCard icon="🎨" title="Interface Designers" color="orange" variant="pillar">
    Custom portals and dashboards
  </FeatureCard>
</Grid>

<div class="flex justify-center gap-4 mt-6">
  <Tag color="blue">Access Controls</Tag>
  <Tag color="green">60+ Integrations</Tag>
</div>

---

# Data

<Grid cols="2" gap="6">
  <div class="bg-blue-50 rounded-2xl p-6">
    <h3 class="text-xl font-bold mb-2">What they build</h3>
    <p class="text-gray-600 mb-4">The data layer of Port</p>
    <div class="space-y-3">
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Integrations</span>
        <span class="text-gray-700">60+ connectors (GitHub, Jira, PagerDuty)</span>
      </div>
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Data connectors</span>
        <span class="text-gray-700">Like Airbyte for engineering data</span>
      </div>
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Datalake</span>
        <span class="text-gray-700">Metrics, analytics, aggregations</span>
      </div>
    </div>
  </div>
  <div class="bg-white rounded-2xl p-6 shadow-sm">
    <h3 class="text-xl font-bold mb-4">Challenges they solve</h3>
    <div class="space-y-3">
      <div class="flex items-center gap-3">
        <span>📈</span>
        <span class="text-gray-700">Scale (millions of entities)</span>
      </div>
      <div class="flex items-center gap-3">
        <span>🔗</span>
        <span class="text-gray-700">Ecosystem connectivity</span>
      </div>
      <div class="flex items-center gap-3">
        <span>📊</span>
        <span class="text-gray-700">Engineering intelligence</span>
      </div>
    </div>
  </div>
</Grid>

---

# The agentic chaos

<Subtitle>1000x bigger problem</Subtitle>

<Grid cols="2" gap="4">
  <div class="bg-white rounded-xl p-5 border-l-4 border-orange-400 shadow-sm">
    <p class="font-semibold text-gray-800">Agents run free, connected haphazardly to tools</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-orange-500 shadow-sm">
    <p class="font-semibold text-gray-800">Context is messy and scattered</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-red-400 shadow-sm">
    <p class="font-semibold text-gray-800">No guardrails, no human oversight, no visibility</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-red-500 shadow-sm">
    <p class="font-semibold text-gray-800">Platform teams lose control</p>
  </div>
</Grid>

<ImpactBox class="mt-6">
  <Grid cols="2" gap="8">
    <div class="text-center">
      <p class="font-bold">No visibility</p>
      <p class="font-bold mt-2">Bad decisions</p>
    </div>
    <div class="text-center">
      <p class="font-bold">No human control</p>
      <p class="font-bold mt-2">No AI guardrails</p>
    </div>
  </Grid>
</ImpactBox>

---

# Tech stack

<Grid cols="3" gap="4">
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">⚛️</div>
    <h3 class="font-bold text-lg mb-3">Frontend</h3>
    <Tag color="purple">React</Tag>
  </div>
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">🔧</div>
    <h3 class="font-bold text-lg mb-3">Backend</h3>
    <div class="flex justify-center gap-2">
      <Tag color="blue">Node.js</Tag>
      <Tag color="yellow">Python</Tag>
    </div>
  </div>
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">🤖</div>
    <h3 class="font-bold text-lg mb-3">AI</h3>
    <div class="bg-purple-100 text-purple-700 px-3 py-2 rounded-lg text-sm">
      Build with AI + Build AI products
    </div>
  </div>
</Grid>

<div class="bg-green-50 rounded-2xl p-6 mt-4">
  <h3 class="font-bold text-xl mb-4">AI-native development</h3>
  <Grid cols="3" gap="6">
    <div class="text-center">
      <p class="font-bold mb-1">Engineers use AI tools daily</p>
      <p class="text-gray-600 text-sm">Claude, Cursor</p>
    </div>
    <div class="text-center">
      <p class="font-bold mb-1">Build AI products</p>
      <p class="text-gray-600 text-sm">Prompts, skills, MCP tools</p>
    </div>
    <div class="text-center">
      <p class="font-bold mb-1">Dogfooding</p>
      <p class="text-gray-600 text-sm">Building agentic platform with agentic tools</p>
    </div>
  </Grid>
</div>

---

# The developer role is changing

<Grid cols="4" gap="3">
  <div class="bg-blue-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2000</p>
    <p class="text-gray-700">IT</p>
  </div>
  <div class="bg-yellow-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2010</p>
    <p class="text-gray-700">DevOps</p>
  </div>
  <div class="bg-purple-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2023</p>
    <p class="text-gray-700">Platform Engineering</p>
  </div>
  <div class="bg-green-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2025</p>
    <p class="text-gray-700">Agentic Platforms</p>
  </div>
</Grid>

<div class="bg-white rounded-2xl p-6 mt-6 shadow-sm">
  <Grid cols="2" gap="8">
    <div>
      <p class="text-gray-500 mb-2">Then</p>
      <p class="font-bold text-lg">Coding only</p>
    </div>
    <div>
      <p class="text-gray-500 mb-2">Now</p>
      <p class="font-bold text-lg">Coding, shipping, incidents, testing, security + optimize AI outputs</p>
    </div>
  </Grid>
</div>
