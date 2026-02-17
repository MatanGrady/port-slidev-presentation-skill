---
theme: ./
title: Port Theme Test
layout: cover
---

# Lorem ipsum dolor sit

<Subtitle>Consectetur adipiscing | February 17, 2026</Subtitle>

<ColorDots />

---

# Agenda

<Grid cols="2">
  <div class="space-y-4">
    <AgendaItem icon="🏢" color="blue">Sed ut perspiciatis</AgendaItem>
    <AgendaItem icon="🔥" color="pink">Nemo enim ipsam</AgendaItem>
    <AgendaItem icon="💡" color="green">Quis autem vel</AgendaItem>
  </div>
  <div class="space-y-4">
    <AgendaItem icon="👥" color="purple">At vero eos</AgendaItem>
    <AgendaItem icon="⚙️" color="yellow">Nam libero tempore</AgendaItem>
    <AgendaItem icon="✨" color="orange">Temporibus autem</AgendaItem>
  </div>
</Grid>

---
layout: section
number: "01"
---

# Sed ut perspiciatis

<Subtitle>Unde omnis iste natus</Subtitle>

---

# Accusantium doloremque

<Subtitle>Totam rem aperiam eaque ipsa</Subtitle>

<Grid cols="3">
  <MetricCard value="847+" label="Voluptatem" />
  <MetricCard value="23k" label="Consequuntur" />
  <MetricCard value="12" label="Ratione" />
  <MetricCard value="9" label="Adipisci" />
  <MetricCard value="2400" label="Dolorem" />
  <MetricCard value="∞" label="Explicabo" />
</Grid>

<ImpactBox center class="mt-6">
  Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit
</ImpactBox>

---

# Neque porro quisquam est

<Grid cols="3">
  <FeatureCard icon="👥" title="Dolorem ipsum" color="blue">
    Quia dolor sit amet consectetur adipisci velit
    <template #tags>
      <Tag color="purple">Numquam eius</Tag>
    </template>
  </FeatureCard>
  <FeatureCard icon="🤖" title="Sed quia non" color="pink">
    Tempora incidunt ut labore et dolore
    <template #tags>
      <Tag color="blue">Magnam aliquam</Tag>
      <Tag color="green">Quaerat</Tag>
    </template>
  </FeatureCard>
  <FeatureCard icon="⚙️" title="Ut enim ad minima" color="green">
    Veniam quis nostrum exercitationem ullam
    <template #tags>
      <Tag color="purple">Corporis</Tag>
      <Tag color="blue">Suscipit</Tag>
    </template>
  </FeatureCard>
</Grid>

---

# Quis autem vel eum iure

<Grid cols="3">
  <StepItem n="1" title="Reprehenderit">
    Qui in ea voluptate velit esse quam nihil molestiae
  </StepItem>
  <StepItem n="2" title="Consequatur">
    Vel illum qui dolorem eum fugiat quo voluptas
  </StepItem>
  <StepItem n="3" title="Nulla pariatur">
    Excepteur sint occaecat cupidatat non proident
  </StepItem>
</Grid>

---

# Steps layout: 2x2 variation

<Grid cols="2" class="max-w-3xl mx-auto">
  <StepItem n="1" title="Laboris">
    Nisi ut aliquid ex ea commodi consequatur
  </StepItem>
  <StepItem n="2" title="Voluptate">
    Autem vel eum iure reprehenderit qui in ea
  </StepItem>
  <StepItem n="3" title="Doloremque">
    Laudantium totam rem aperiam eaque ipsa quae
  </StepItem>
  <StepItem n="4" title="Inventore">
    Ab illo veritatis et quasi architecto beatae vitae
  </StepItem>
</Grid>

---

# Tags demo

<div class="flex flex-wrap gap-2">
  <Tag color="blue">Consectetur</Tag>
  <Tag color="purple">Adipiscing elit</Tag>
  <Tag color="green">Incididunt</Tag>
  <Tag color="pink">Laboris nisi</Tag>
  <Tag color="yellow">Aliquip ex</Tag>
  <Tag color="orange">Commodo</Tag>
  <Tag color="dark">Consequat</Tag>
</div>

---

# Sunt in culpa

<Grid cols="3" gap="4">
  <FeatureCard icon="📚" title="Fugiat nulla" color="blue" variant="pillar">
    Pariatur excepteur sint occaecat cupidatat
  </FeatureCard>
  <FeatureCard icon="📊" title="Deserunt mollit" color="green" variant="pillar">
    Anim id est laborum sed ut perspiciatis
  </FeatureCard>
  <FeatureCard icon="⚡" title="Unde omnis" color="pink" variant="pillar">
    Iste natus error sit voluptatem accusantium
  </FeatureCard>
  <FeatureCard icon="🔄" title="Doloremque" color="purple" variant="pillar">
    Laudantium totam rem aperiam eaque
  </FeatureCard>
  <FeatureCard icon="🤖" title="Ipsa quae" color="yellow" variant="pillar">
    Ab illo inventore veritatis et quasi
  </FeatureCard>
  <FeatureCard icon="🎨" title="Architecto" color="orange" variant="pillar">
    Beatae vitae dicta sunt explicabo
  </FeatureCard>
</Grid>

---

# Nemo enim

<Grid cols="2" gap="6">
  <div class="bg-blue-50 rounded-2xl p-6">
    <h3 class="text-xl font-bold mb-2">Ipsam voluptatem</h3>
    <p class="text-gray-600 mb-4">Quia voluptas sit aspernatur</p>
    <div class="space-y-3">
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Temporibus</span>
        <span class="text-gray-700">Autem quibusdam et aut officiis</span>
      </div>
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Debitis aut</span>
        <span class="text-gray-700">Rerum necessitatibus saepe eveniet</span>
      </div>
      <div class="flex items-center gap-3">
        <span class="bg-white px-3 py-1 rounded-full text-sm font-medium">Voluptates</span>
        <span class="text-gray-700">Repudiandae sint et molestiae non</span>
      </div>
    </div>
  </div>
  <div class="bg-white rounded-2xl p-6 shadow-sm">
    <h3 class="text-xl font-bold mb-4">Recusandae itaque</h3>
    <div class="space-y-3">
      <div class="flex items-center gap-3">
        <span>📈</span>
        <span class="text-gray-700">Earum rerum hic tenetur</span>
      </div>
      <div class="flex items-center gap-3">
        <span>🔗</span>
        <span class="text-gray-700">Sapiente delectus ut aut</span>
      </div>
      <div class="flex items-center gap-3">
        <span>📊</span>
        <span class="text-gray-700">Reiciendis voluptatibus maiores</span>
      </div>
    </div>
  </div>
</Grid>

---

# Omnis voluptas assumenda

<Subtitle>Dolor repellendus 1000x</Subtitle>

<Grid cols="2" gap="4">
  <div class="bg-white rounded-xl p-5 border-l-4 border-orange-400 shadow-sm">
    <p class="font-semibold text-gray-800">Temporibus autem quibusdam et aut officiis debitis</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-orange-500 shadow-sm">
    <p class="font-semibold text-gray-800">Rerum necessitatibus saepe eveniet</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-red-400 shadow-sm">
    <p class="font-semibold text-gray-800">Ut et voluptates repudiandae sint et molestiae</p>
  </div>
  <div class="bg-white rounded-xl p-5 border-l-4 border-red-500 shadow-sm">
    <p class="font-semibold text-gray-800">Non recusandae itaque earum rerum</p>
  </div>
</Grid>

<ImpactBox class="mt-6">
  <Grid cols="2" gap="8">
    <div class="text-center">
      <p class="font-bold">Hic tenetur</p>
      <p class="font-bold mt-2">Sapiente delectus</p>
    </div>
    <div class="text-center">
      <p class="font-bold">Aut reiciendis</p>
      <p class="font-bold mt-2">Voluptatibus maiores</p>
    </div>
  </Grid>
</ImpactBox>

---

# Alias consequatur

<Grid cols="3" gap="4">
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">⚛️</div>
    <h3 class="font-bold text-lg mb-3">Perferendis</h3>
    <Tag color="purple">Doloribus</Tag>
  </div>
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">🔧</div>
    <h3 class="font-bold text-lg mb-3">Asperiores</h3>
    <div class="flex justify-center gap-2">
      <Tag color="blue">Repellat</Tag>
      <Tag color="yellow">Provident</Tag>
    </div>
  </div>
  <div class="bg-white rounded-xl p-5 text-center shadow-sm">
    <div class="text-3xl mb-2">🤖</div>
    <h3 class="font-bold text-lg mb-3">Similique</h3>
    <div class="bg-purple-100 text-purple-700 px-3 py-2 rounded-lg text-sm">
      Sunt in culpa qui officia
    </div>
  </div>
</Grid>

<div class="bg-green-50 rounded-2xl p-6 mt-4">
  <h3 class="font-bold text-xl mb-4">Deserunt mollitia</h3>
  <Grid cols="3" gap="6">
    <div class="text-center">
      <p class="font-bold mb-1">Animi id est laborum</p>
      <p class="text-gray-600 text-sm">Dolorum fuga</p>
    </div>
    <div class="text-center">
      <p class="font-bold mb-1">Et harum quidem</p>
      <p class="text-gray-600 text-sm">Rerum facilis</p>
    </div>
    <div class="text-center">
      <p class="font-bold mb-1">Expedita distinctio</p>
      <p class="text-gray-600 text-sm">Nam libero tempore</p>
    </div>
  </Grid>
</div>

---

# Cumque nihil impedit

<Grid cols="4" gap="3">
  <div class="bg-blue-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2000</p>
    <p class="text-gray-700">Lorem</p>
  </div>
  <div class="bg-yellow-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2010</p>
    <p class="text-gray-700">Ipsum</p>
  </div>
  <div class="bg-purple-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2023</p>
    <p class="text-gray-700">Dolor sit amet</p>
  </div>
  <div class="bg-green-100 rounded-xl p-5 text-center">
    <p class="font-bold text-xl mb-1">2025</p>
    <p class="text-gray-700">Consectetur</p>
  </div>
</Grid>

<div class="bg-white rounded-2xl p-6 mt-6 shadow-sm">
  <Grid cols="2" gap="8">
    <div>
      <p class="text-gray-500 mb-2">Ante</p>
      <p class="font-bold text-lg">Minus id quod</p>
    </div>
    <div>
      <p class="text-gray-500 mb-2">Post</p>
      <p class="font-bold text-lg">Maxime placeat facere possimus omnis voluptas assumenda</p>
    </div>
  </Grid>
</div>
