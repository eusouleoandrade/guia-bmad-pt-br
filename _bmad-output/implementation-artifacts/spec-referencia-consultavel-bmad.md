---
title: 'Transformar guia em referência consultável do BMAD'
type: 'feature'
created: '2026-07-13'
status: 'done'
review_loop_iteration: 0
baseline_commit: '9b6d83e2cfd573a708d7ef9477055d89ec1cf6e1'
context: []
---

<frozen-after-approval reason="human-owned intent — do not modify unless human renegotiates">

## Intent

**Problem:** O HTML apresenta boa introdução, mas mistura conceitos, omite partes do fluxo instalado e não oferece detalhes suficientes para consulta sobre tracks, skills, agentes, artefatos, entradas e saídas. Algumas simplificações contradizem o catálogo BMAD 6.10.0 local, especialmente validação de story e alcance do Quick Dev.

**Approach:** Reorganizar e ampliar a página como referência progressiva: visão simples para iniciantes, escolha de track por contexto, fluxo canônico completo e catálogo pesquisável com propósito, momento de uso e resultado. Validar conteúdo contra catálogo local 6.10.0 e documentação oficial atual, deixando divergências de versão explícitas.

## Boundaries & Constraints

**Always:** editar somente `index.html`; preservar linguagem Português Brasil e estilo visual atual; manter página estática e autocontida; distinguir sintaxe `$bmad-*` específica do Codex dos nomes canônicos `bmad-*`; identificar catálogo local 6.10.0 como base primária; tratar contagens de stories como orientação, não regra.

**Ask First:** mudanças de identidade visual, adoção de dependências externas, remoção de seções educacionais existentes ou alteração de arquivos além de `index.html`.

**Never:** apresentar todo projeto como obrigado a seguir PRD e arquitetura; misturar agente, skill e ação de menu como equivalentes; promover aliases depreciados como comandos recomendados; inventar filename quando output varia por versão; modificar mudanças não relacionadas no working tree.

## I/O & Edge-Case Matrix

| Scenario | Input / State | Expected Output / Behavior | Error Handling |
|----------|--------------|---------------------------|----------------|
| Consulta por objetivo | Pessoa não sabe qual recurso usar | Encontra track, fase ou função e vê quando usar, entrada e resultado | Direcionar para `bmad-help` quando contexto for insuficiente |
| Consulta por comando | Busca com ou sem acentos | Skill correta aparece com descrição e categoria | Exibir estado vazio acessível |
| Divergência de versão | Instalação diferente de 6.10.0 | Página deixa base auditada e necessidade de confirmar catálogo claras | Evitar garantias universais sobre nomes variáveis |

</frozen-after-approval>

## Code Map

- `index.html` -- documentação, layout, busca e interação de cópia em arquivo único.
- `_bmad/bmm/module-help.csv` -- fonte local para fases, precedências, obrigatoriedade e outputs.
- `_bmad/_config/skill-manifest.csv` -- catálogo local de skills, módulos e aliases depreciados.
- `_bmad/bmm/config.yaml` -- versão instalada, idioma e pastas configuradas.

## Tasks & Acceptance

**Execution:**
- [x] `index.html` -- adicionar identificação da versão, definição explícita e três tracks -- estabelecer escopo correto antes do fluxo.
- [x] `index.html` -- restaurar e completar fluxo de planejamento e story, incluindo readiness, sprint planning e validate story -- refletir catálogo 6.10.0.
- [x] `index.html` -- detalhar artefatos por pasta, propósito e variação de outputs -- tornar consulta operacional.
- [x] `index.html` -- separar agentes, workflows BMM, ferramentas core e ações de menu; completar skills úteis e aliases depreciados -- impedir confusão conceitual.
- [x] `index.html` -- manter busca/cópia acessíveis e adaptar categorias novas -- preservar usabilidade.

**Acceptance Criteria:**
- Given uma pessoa nova no BMAD, when lê introdução e tracks, then entende o que BMAD é, o que não é e qual caminho inicial escolher.
- Given catálogo local 6.10.0, when compara fluxo e comandos, then encontra create/validate/dev/review, readiness, sprint planning e utilitários principais sem contradições conhecidas.
- Given consulta a uma funcionalidade, when localiza item, then vê propósito, quando usar e principal resultado ou pasta.
- Given página em viewport móvel ou desktop, when navega, busca e copia, then conteúdo permanece legível e interações continuam acessíveis.

## Spec Change Log

## Verification

**Commands:**
- `git diff --check -- index.html` -- expected: sem erros de whitespace.
- `node --check` sobre script embutido -- expected: JavaScript válido.
- verificações com `rg` contra catálogo local -- expected: fluxo e skills prioritárias presentes.

**Manual checks:**
- Conferir hierarquia, leitura rápida, layout responsivo e clareza das categorias.

## Suggested Review Order

**Escopo e escolha do processo**

- Define base auditada e limites de compatibilidade da referência.
  [`index.html:481`](../../index.html#L481)

- Separa Quick Flow, BMad Method e Enterprise sem impor processo único.
  [`index.html:557`](../../index.html#L557)

**Modelo, fluxo e artefatos**

- Distingue agentes, workflows, skills, ações de menu e artefatos.
  [`index.html:661`](../../index.html#L661)

- Mostra fluxo BMad Method completo e exceções do Quick Flow.
  [`index.html:721`](../../index.html#L721)

- Mapeia outputs para pastas configuradas na instalação local.
  [`index.html:779`](../../index.html#L779)

**Consulta operacional**

- Explica responsabilidades e resultados dos seis agentes.
  [`index.html:893`](../../index.html#L893)

- Cataloga skills, categorias, ações e aliases depreciados.
  [`index.html:969`](../../index.html#L969)

- Preserva busca acessível, classificação e feedback de cópia.
  [`index.html:1312`](../../index.html#L1312)
