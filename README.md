# BMAD sem mistério

Referência prática em Português do Brasil sobre BMad Method, seus caminhos de planejamento,
agentes, skills, workflows, artefatos e ciclo de desenvolvimento por stories.

## Acessar o guia

Após habilitar GitHub Pages:

<https://eusouleoandrade.github.io/guia-bmad-pt-br/>

Também é possível abrir `index.html` diretamente no navegador.

## Conteúdo

- Instalação do BMad Method.
- Como chamar skills no Codex.
- Diferença entre agente, skill, workflow, ação de menu e artefato.
- Como escolher entre Quick Flow, BMad Method e Enterprise.
- Quatro fases do método.
- PRD, Project Context, UX, arquitetura, épicos, stories e readiness.
- Catálogo pesquisável de funcionalidades e aliases depreciados.
- Ciclo completo: sprint planning, criação, validação, implementação e revisão por story.
- Roteiros de treinamento de 60 e 90 minutos.

## Publicar no GitHub Pages

1. Faça commit e push para branch `main`.
2. No GitHub, abra **Settings > Pages**.
3. Em **Source**, selecione **Deploy from a branch**.
4. Selecione branch `main` e pasta `/(root)`.
5. Salve e aguarde publicação.

## Estrutura

```text
guia-bmad-pt-br/
├── _bmad/
│   ├── config.toml
│   └── custom/config.toml
├── _bmad-output/
│   └── implementation-artifacts/
├── .gitignore
├── .nojekyll
├── index.html
├── README.md
└── LICENSE
```

`_bmad/` contém configuração compartilhável do método; internals gerados permanecem ignorados.
`_bmad-output/` contém artefatos produzidos e deve ser versionado.

## Versão

Guia `1.1.0`, auditado contra catálogo local BMad Method `6.10.0` e documentação oficial
consultada em julho de 2026.

Este é um material educacional independente e não oficial. Confirme comandos na documentação oficial quando sua instalação usar outra versão.

## Contribuição

Erros, dúvidas e melhorias podem ser registrados nas [Issues](https://github.com/eusouleoandrade/guia-bmad-pt-br/issues).

## Licença

Distribuído sob licença MIT. Consulte [LICENSE](LICENSE).
