---
name: melhorar-visual
description: Guia de design system para melhorar elementos visuais da apresentação RAID
---

# Design System — Apresentação RAID

## Variáveis CSS
```css
--bg: #f7f6f2       /* off-white quente */
--surface: #ffffff  /* branco puro (cards) */
--ink: #0a0a0a      /* preto principal */
--ink-2: #1c1c1c    /* preto secundário */
--muted: #6b6b66    /* cinza médio */
--muted-2: #9a988f  /* cinza claro */
--line: #e8e6e0     /* borda sutil */
--line-strong: #d4d2c9 /* borda forte */
--radius: 12px
```

## Accent color
Amber `#f59e0b` — usar em: labels "Onde é utilizado", bordas de destaque, barra da capa.

## Tipografia (tamanhos responsivos)
| Classe | Fonte | Uso |
|--------|-------|-----|
| `.display-xl` | Outfit 300 | Título da capa |
| `.display-md` | Outfit 400 | Título de seção grande |
| `.title-section` | Outfit 400 | Título de slide normal |
| `.lead` | Inter 400 | Parágrafo introdutório |
| `.body` | Inter 400 | Texto secundário |
| `.eyebrow` | Outfit 500, uppercase | Nome do apresentador + seção |

## Classes de destaque
```css
.use-section-label  /* amber, uppercase, tracking — "Onde é utilizado" */
.use-card           /* borda esquerda amber, fundo bg */
.tag-yes            /* verde suave — "Sim" */
.tag-no             /* vermelho suave — "Não" */
.perf-vhigh         /* verde — performance muito alta */
.perf-high          /* azul — performance alta */
.perf-medhigh       /* amber — performance média-alta */
.perf-med           /* rosa — performance média */
```

## Cards
```css
/* Card claro */
.compare-card { background: var(--surface); border: 1px solid var(--line); }

/* Card escuro (contraste) */
.compare-card.dark { background: var(--ink); color: var(--bg); }
/* Dentro do dark card: .bullet-list li fica rgba(247,246,242,0.82) */
```

## Animações
- Transição de slides: `opacity 360ms ease`
- Entrada de conteúdo: `translateY(8px→0) + opacity, 520ms`
- Hover em cards: `translateY(-3px) + box-shadow`
- Barra de progresso: `scaleX, 480ms ease`

## O que NÃO usar
- Emojis
- Gradientes de fundo pesados (use apenas dot-grid sutil na capa)
- Bordas coloridas fortes exceto o accent amber
- Mais de 2 tipos de badge por slide
