---
name: criar-slide
description: Adiciona um novo slide à apresentação RAID seguindo o design system do projeto
---

# Criar Slide — Apresentação RAID

Use este skill ao adicionar ou modificar slides em `apresentacao-raid.html`.

## Layouts disponíveis

### `l-cover` — Capa
```html
<div class="slide-inner l-cover">
  <span class="eyebrow">Texto<span class="dot"></span>Contexto</span>
  <h1 class="display-xl">Título</h1>
  <div class="meta">
    <span class="body">Subtítulo</span>
    <span class="subtle">N slides</span>
  </div>
</div>
```

### `l-statement` — Conteúdo textual
```html
<div class="slide-inner l-statement">
  <span class="eyebrow">Apresentador<span class="dot"></span>Seção</span>
  <h2 class="display-md">Título</h2>
  <p class="lead">Parágrafo introdutório.</p>
  <ul class="bullet-list">
    <li>Ponto 1</li>
    <li>Ponto 2</li>
  </ul>
  <div class="use-section">
    <span class="use-section-label">Onde é utilizado</span>
    <div class="use-grid">
      <span class="use-card">Exemplo 1</span>
    </div>
  </div>
</div>
```

### `l-split` — Imagem + Conteúdo
```html
<div class="slide-inner l-split">
  <div class="split-content">
    <span class="eyebrow">Apresentador<span class="dot"></span>RAID X</span>
    <h2 class="title-section">Título</h2>
    <ul class="bullet-list">
      <li>Ponto</li>
    </ul>
    <div class="use-section">
      <span class="use-section-label">Onde é utilizado</span>
      <div class="use-grid">
        <span class="use-card">Exemplo</span>
      </div>
    </div>
  </div>
  <div class="split-image">
    <img src="RAID X.png" alt="Descrição" />
    <!-- ou SVG inline -->
  </div>
</div>
```

### `l-compare` — Dois cartões comparativos
```html
<div class="slide-inner l-compare">
  <span class="eyebrow">Apresentador<span class="dot"></span>Seção</span>
  <h2 class="title-section">Título</h2>
  <div class="grid-2">
    <div class="compare-card">
      <span class="compare-label">Label</span>
      <div class="compare-value">Valor</div>
      <ul class="bullet-list"><li>Item</li></ul>
    </div>
    <div class="compare-card dark"><!-- conteúdo --></div>
  </div>
</div>
```

### `l-diagram-below` — Diagrama SVG abaixo do conteúdo
```html
<div class="slide-inner l-diagram-below">
  <div class="diagram-content">
    <span class="eyebrow">…</span>
    <h2 class="title-section">Título</h2>
    <ul class="bullet-list"><li>Item</li></ul>
  </div>
  <div class="diagram-svg">
    <svg>…</svg>
  </div>
</div>
```

## Cores de SVG (padrão)
```
Corpo do disco: fill="#bed8f0" stroke="#6ea8d8"
Tampa superior: fill="#d8eeff" stroke="#6ea8d8"
Tampa inferior: fill="#a0c4e0" stroke="#6ea8d8"
Bloco de dados: fill="#a0c8e4" stroke="#5090ba"
Paridade P:     fill="#fcd34d" stroke="#d97706" text="#78350f"
Paridade Q:     fill="#fb923c" stroke="#ea580c" text="#7c2d12"
Label do disco: fill="#6d28d9" (roxo)
Texto do bloco: fill="#1a3a5c"
```

## Regras
1. Cada novo slide precisa de `data-slide="N"` e atualizar o total no JS/HTML (id="total")
2. O eyebrow deve conter o nome do apresentador + seção: `Nome<span class="dot"></span>RAID X`
3. Não adicionar emojis
4. Não adicionar comentários óbvios no código
