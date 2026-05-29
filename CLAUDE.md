# Trabalho de RAID — CLAUDE.md (raiz)

## Arquivo principal
`apresentacao-raid.html` — arquivo único, 1 arquivo HTML, sem build, sem dependências locais além das imagens PNG.

## Imagens locais (PNG)
- `RAID 0.png`, `RAID 1.png`, `RAID 3.png`, `RAID 4.png`, `RAID 5.png`
- RAID 2, 6, 10 usam SVG inline no HTML
- RAID 50 usa SVG inline (2 variantes: slides 17 e 18)

## Design system
- Background `#f7f6f2`, Ink `#0a0a0a`, Accent `#f59e0b` (amber)
- Fontes: Inter (corpo) + Outfit (títulos/display) via Google Fonts
- Radius 12px, ease `cubic-bezier(.22,.61,.36,1)`

## Layouts disponíveis (classes)
- `.l-cover` — capa/encerramento
- `.l-statement` — texto corrido com bullets
- `.l-split` — dois colunas (conteúdo | imagem/SVG)
- `.l-compare` + `.grid-2` + `.compare-card` — cards comparativos
- `.l-fault` — tolerância a falhas com animação interativa
- `.l-transition` — slide de transição entre apresentadores
- `.l-table` + `.raid-table` — tabela comparativa
- `.l-xor` + `.xbt` — slide de cálculo XOR

## Padrão de animação fault-tolerance (ft-slides)
Todos os slides com `class="slide ft-slide"` ganham botões Play/Reset automaticamente via JS.

Estrutura obrigatória:
```html
<article class="slide ft-slide" data-slide="ft-XX">
  <div class="slide-inner l-fault">
    <span class="eyebrow">Tolerância a Falhas<span class="dot"></span>RAID N</span>
    <h2 class="title-section">RAID N — Cenário</h2>
    <div class="ft-scene">
      <div class="ft-anim">
        <div class="ft-disk-row">
          <!-- discos: .ft-disk.disk-fail ou .ft-disk.disk-survivor -->
          <!-- cada disco tem: .ft-cap, .ft-body (com .ft-blk), .ft-fail-x (só disk-fail), .ft-name -->
        </div>
        <div class="ft-result result-ok|result-fail">Mensagem final</div>
      </div>
      <div class="ft-panel">
        <!-- .ft-card com .ft-card-lbl + .ft-card-txt -->
        <!-- último card: border-left:3px solid #22c55e (ok) ou #ef4444 (fail) -->
      </div>
    </div>
  </div>
</article>
```

Classes de bloco disponíveis: `.ft-blk` (azul/dado), `.ft-blk.p` (amarelo/paridade P), `.ft-blk.q` (laranja/paridade Q), `.ft-blk.ecc` (roxo/Hamming ECC)

Para discos agrupados (RAID 10, RAID 50): usar `.ft-group` > `.ft-group-label` + `.ft-group-disks` > discos

## Slides e responsáveis (por array position no JS)
| Pos | data-slide | Conteúdo | Responsável |
|-----|-----------|----------|-------------|
| 0 | 1 | Capa | — |
| 1 | 2 | Integrantes | — |
| 2 | t1 | Transição | — |
| 3–9 | 3–9 | RAID intro, RAID 0, Striping, Mirroring, Red&Par, XOR, RAID 1 | Lucas |
| 10 | t2 | Transição | — |
| 11–13 | 10–12 | RAID 2, 3, 4 | João |
| 14 | t3 | Transição | — |
| 15–16 | 13–14 | RAID 5, 6 | Jhonatan |
| 17 | ft0 | Intro tolerância a falhas | — |
| 18–19 | ft1, ft2 | FT RAID 0, RAID 1 | — |
| 20–22 | ft-r2, ft-r3, ft-r4 | FT RAID 2, 3, 4 (recuperação) | — |
| 23–24 | ft3, ft3b | FT RAID 5 (ok + falha 2 discos) | — |
| 25–26 | ft4, ft4b | FT RAID 6 (ok + falha 3 discos) | — |
| 27–28 | ft5, ft5b | FT RAID 10 (ok + falha 2 mesmo grupo) | — |
| 29–30 | ft6, ft6b | FT RAID 50 (ok + falha 2 mesmo grupo) | — |
| 31 | t4 | Transição | — |
| 32–36 | 15–19 | Combinados, RAID 10, RAID 50×2, Tabela | Rhaidy |
| 37 | refs | Referências | — |
| 38 | closing | Encerramento | — |

**Total: 39 slides** (atualizado na capa)

## Regras
- Leia APENAS os trechos do HTML relevantes para a tarefa atual — o arquivo tem ~2100 linhas
- Não adicionar dependências externas (CDN, bibliotecas JS)
- Não alterar o JS de navegação ou o sistema de animação ft — só adicionar slides seguindo o padrão
- Commits apenas quando o usuário pedir explicitamente

## O que está feito
- [x] Todos os slides de conteúdo (RAID 0–6, 10, 50)
- [x] Sistema de animação fault-tolerance (botão play/reset automático)
- [x] FT slides: RAID 0, 1, 2, 3, 4, 5, 5-fail, 6, 6-fail, 10, 10-fail, 50, 50-fail
- [x] Diagramas RAID 50 com tamanho aumentado (26vh)
- [x] Tabela comparativa, referências, encerramento

## Pendente / possíveis melhorias
- Verificar se os slides de falha (ft3b, ft4b, ft5b, ft6b) precisam de ajuste visual após revisão presencial
- Slide de RAID 2 FT usa 5 discos — verificar se aparece bem em tela pequena
