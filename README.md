# DevTOLAS

O DevTOLAS é uma base de engenharia de software para uso com Codex no VS Code.
Seu objetivo é oferecer um método consistente, documentado, reutilizável e
evolutivo para o desenvolvimento de diferentes sistemas.

O DevTOLAS não é:

- um sistema de negócio;
- um framework de aplicação;
- apenas uma coleção de prompts;
- substituto da documentação de cada projeto.

## Estrutura inicial

```text
DevTOLAS/
├── AGENTS.md
├── README.md
├── CHANGELOG.md
├── docs/
│   ├── principios.md
│   ├── governanca.md
│   ├── metodo-de-desenvolvimento.md
│   ├── evolucao-do-conhecimento.md
│   ├── sistema-de-desenvolvimento.md
│   ├── criacao-de-projetos.md
│   ├── continuidade.md
│   └── migracoes/
│       ├── gptolas.md
│       ├── fs-comum.md
│       └── transicao-concluida.md
└── templates/
    └── projeto/
        ├── AGENTS.md.template
        └── projeto.code-workspace.template
```

## Responsabilidades

- `AGENTS.md`: orienta a atuação do Codex neste repositório.
- `docs/`: registra o sistema de desenvolvimento, seus princípios, seu método e
  a governança do conhecimento.
- `templates/`: contém os materiais reutilizáveis para integração de projetos.
- `CHANGELOG.md`: registra mudanças relevantes na base.

## Estado atual

O DevTOLAS é a fonte da verdade do método de engenharia utilizado pelos projetos
consumidores. Os workspaces ativos usam o projeto específico e o DevTOLAS como
referência de método.

Skills e automações serão adicionadas apenas quando houver uma necessidade
concreta.
