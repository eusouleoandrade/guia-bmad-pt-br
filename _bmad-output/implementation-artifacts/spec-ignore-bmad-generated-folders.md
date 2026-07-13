---
title: 'Ignorar pastas BMAD geradas'
type: 'chore'
created: '2026-07-13'
status: 'done'
route: 'one-shot'
---

# Ignorar pastas BMAD geradas

## Intent

**Problem:** Integrações geradas em `.agent/` e `.github/agents/` apareciam como arquivos não rastreados, enquanto exceções de configuração sob `_bmad/` não funcionavam porque o diretório pai estava totalmente ignorado.

**Approach:** Ignorar integrações geradas e reabrir somente `_bmad/config.toml` e `_bmad/custom/config.toml`, mantendo restante interno e configurações pessoais fora do Git.

## Suggested Review Order

- Centraliza regras BMAD e preserva somente configurações compartilháveis.
  [`.gitignore:23`](../../.gitignore#L23)
