# RAID — Redundant Array of Independent Disks

Apresentação interativa sobre os principais tipos de RAID, desenvolvida como trabalho acadêmico para a disciplina de **Projetos de Sistemas da Informação (2026)**.

> Todo o conteúdo técnico desta apresentação foi baseado nas anotações de aula compiladas por **Lucas Mendes** no documento **TRABALHO_DE_RAID.pdf** — fonte primária de todo o material apresentado.

---

## Desenvolvido por

**Lucas Mendes** — autor das anotações de aula, do documento base e da implementação completa da apresentação interativa em HTML/CSS/JS.

---

## Equipe

| Integrante | Conteúdo |
|---|---|
| **Lucas Mendes** | O que é RAID · RAID 0 · Striping · Mirroring · Redundância & Paridade · Cálculo XOR · RAID 1 |
| **João Augusto** | RAID 2 · RAID 3 · RAID 4 |
| **Jhonatan Zago** | RAID 5 · RAID 6 |
| **Rhaidy Vieira** | RAIDs Combinados · RAID 10 · RAID 50 · Tabela Comparativa |

---

## Sobre o projeto

Apresentação em formato de slides com **39 slides** cobrindo do conceito básico de RAID até os tipos combinados, incluindo animações interativas de tolerância a falhas para cada tipo de RAID.

---

## Conteúdo da apresentação

| Slides | Tema |
|---|---|
| 01–02 | Capa e Integrantes |
| 03–09 | Introdução ao RAID, RAID 0, Striping, Mirroring, Redundância & Paridade, XOR, RAID 1 |
| 10–12 | RAID 2, RAID 3, RAID 4 |
| 13–14 | RAID 5, RAID 6 |
| 15–30 | Seção de Tolerância a Falhas (animações interativas para cada tipo) |
| 31–36 | RAIDs Combinados, RAID 10, RAID 50, Tabela Comparativa |
| 37–39 | Referências, Encerramento |

---

## Tecnologias utilizadas

- **HTML5** — estrutura e semântica dos slides
- **CSS3** — design system completo com variáveis CSS, animações e layout responsivo
- **JavaScript (Vanilla)** — sistema de navegação, animações de tolerância a falhas e controle de estado
- **SVG inline** — diagramas técnicos dos tipos de RAID (RAID 2, 5, 6, 10, 50)
- **Google Fonts** — tipografia Inter (corpo) e Outfit (títulos), carregadas via CDN
- **Imagens PNG locais** — diagramas de RAID 0, RAID 1, RAID 3, RAID 4

> Sem dependências externas de JavaScript. Sem frameworks. Sem build tools.  
> Um único arquivo HTML autocontido.

---

## Estrutura do projeto

```
Trabalho de RAID - 02/
├── apresentacao-raid.html    # Arquivo principal — toda a apresentação
├── TRABALHO_DE_RAID.pdf      # Anotações de aula do Lucas Mendes — fonte de todo o conteúdo
├── RAID 0.png                # Diagrama RAID 0
├── RAID 1.png                # Diagrama RAID 1
├── RAID 3.png                # Diagrama RAID 3
├── RAID 4.png                # Diagrama RAID 4
├── RAID 5.png                # Diagrama RAID 5
├── CLAUDE.md                 # Contexto do projeto para o agente Claude Code
└── README.md                 # Este arquivo
```

---

## Como executar

### Você já tem os arquivos do projeto?

**Sim** — já baixou ou recebeu a pasta do projeto → pule direto para uma das opções abaixo.

**Não** — precisa obter os arquivos primeiro → clone o repositório:

```bash
git clone https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git
cd SEU_REPOSITORIO
```

> Substitua `SEU_USUARIO/SEU_REPOSITORIO` pelo caminho real do repositório no GitHub.  
> Após clonar, entre na pasta criada e siga uma das opções abaixo.

---

### Opção 1 — Terminal (sem extensão)

**macOS**

O Python 3 já vem instalado. Abra o Terminal na pasta do projeto e rode:

```bash
python3 -m http.server 8000
```

**Windows**

Abra o Prompt de Comando ou PowerShell na pasta do projeto e rode:

```bash
python -m http.server 8000
```

> Caso o Python não esteja instalado no Windows, baixe em [python.org/downloads](https://www.python.org/downloads/) e marque a opção **"Add Python to PATH"** durante a instalação.

Acesse no navegador: [http://localhost:8000/apresentacao-raid.html](http://localhost:8000/apresentacao-raid.html)

Para encerrar o servidor: `Ctrl + C`

---

### Opção 2 — Live Server (VS Code)

Funciona igual em macOS e Windows.

1. Instale a extensão **Live Server** de Ritwick Dey no VS Code
2. Abra a pasta do projeto no VS Code
3. Clique com o botão direito em `apresentacao-raid.html`
4. Selecione **"Open with Live Server"**
5. O navegador abrirá automaticamente na apresentação

> **Vantagem do Live Server:** recarrega a página automaticamente ao salvar alterações no arquivo.

---

### Opção 3 — Abrir direto no navegador

> ⚠️ **Não funciona pelo GitHub.** O GitHub exibe o HTML como código-fonte, não como página. É necessário ter a pasta do projeto localmente (após o `git clone`).

**macOS**
```bash
open apresentacao-raid.html
```

**Windows**

Clique duas vezes no arquivo `apresentacao-raid.html` ou arraste-o para o navegador.

> As fontes do Google Fonts exigem conexão com a internet. Sem conexão, o navegador usa as fontes de fallback do sistema.

---

## Navegação

| Ação | Comando |
|---|---|
| Próximo slide | `→` ou `Espaço` ou `Page Down` |
| Slide anterior | `←` ou `Page Up` |
| Primeiro slide | `Home` |
| Último slide | `End` |
| Swipe mobile | Deslize para esquerda/direita |
| Botões na tela | Anterior / Próximo |

---

## Animações de tolerância a falhas

A seção de tolerância a falhas (slides 17–30) conta com animações interativas para cada tipo de RAID. Para cada cenário:

1. Clique em **"Disparar animação"** para ver a falha acontecer
2. O disco com falha chacoalha, fica vermelho e é ejetado
3. O resultado aparece — **verde** (volume íntegro) ou **vermelho** (volume perdido)
4. Clique em **"Resetar"** para reiniciar e repetir

### Cenários cobertos

| RAID | Cenário OK | Cenário de falha |
|---|---|---|
| RAID 0 | — | 1 disco → volume perdido |
| RAID 1 | 1 disco → volume íntegro | — |
| RAID 2 | 1 disco → ECC recupera | — |
| RAID 3 | 1 disco → paridade recupera | — |
| RAID 4 | 1 disco → paridade recupera | — |
| RAID 5 | 1 disco → volume íntegro | 2 discos → volume perdido |
| RAID 6 | 2 discos → volume íntegro | 3 discos → volume perdido |
| RAID 10 | 1 disco por grupo → íntegro | 2 discos mesmo grupo → perdido |
| RAID 50 | 1 disco por grupo → íntegro | 2 discos mesmo grupo → perdido |

---

## Design system

| Variável | Valor | Uso |
|---|---|---|
| `--bg` | `#f7f6f2` | Fundo off-white quente |
| `--ink` | `#0a0a0a` | Texto principal |
| `--accent` | `#f59e0b` | Amber — destaques e labels |
| `--surface` | `#ffffff` | Cards e superfícies |
| `--radius` | `12px` | Bordas arredondadas |

Fontes: **Outfit** (títulos e display) + **Inter** (corpo e texto corrido)

---

## Referências

- **MENDES, Lucas.** *TRABALHO_DE_RAID.pdf* — Anotações de aula compiladas, 2026. **Fonte primária de todo o conteúdo desta apresentação.**
- PATTERSON, D.; GIBSON, G.; KATZ, R. *A Case for Redundant Arrays of Inexpensive Disks (RAID)*. ACM SIGMOD, UC Berkeley, 1988.
- DATACLINIC. *RAID Parity Calculation using XOR Operation*. dataclinic.co.uk
- COMMANDLINUX. *RAID Configuration Usage Statistics on Linux Servers*. 2026.
- TECHTARGET. *What is RAID?* techtarget.com/searchstorage
- WIKIPEDIA. *Standard RAID levels*. en.wikipedia.org/wiki/Standard_RAID_levels
- THE GEEK STUFF. *RAID 0, 1, 2, 3, 4, 5, 6 Explained with Diagrams*. thegeekstuff.com

---

*Trabalho desenvolvido para a disciplina de Projetos de Sistemas da Informação — 2026.*  
*Desenvolvido por Lucas Mendes.*
