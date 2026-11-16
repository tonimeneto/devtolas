# DevTOLAS

O DevTOLAS é uma metodologia de desenvolvimento assistido por IA. Seu objetivo é
oferecer um método consistente, documentado, reutilizável e evolutivo para o
desenvolvimento de diferentes sistemas, independentemente da ferramenta
utilizada.

Atualmente, sua aplicação operacional ocorre principalmente com o Codex no
VS Code. O Codex é um executor da metodologia, não parte de sua definição.

O DevTOLAS não é:

- um sistema de negócio;
- um framework de aplicação;
- um produto de IA;
- uma plataforma de automação;
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
│   ├── estado-vigente.md
│   ├── handoff-contextos.md
│   └── uso-de-llm.md
└── templates/
    └── projeto/
        ├── AGENTS.md.template
        └── projeto.code-workspace.template
```

## Responsabilidades

- `AGENTS.md`: orienta a atuação do Codex neste repositório.
- `docs/`: registra a metodologia de desenvolvimento, seus princípios, seu
  método e a governança do conhecimento.
- `templates/`: contém os materiais reutilizáveis para integração de projetos.
- `CHANGELOG.md`: registra mudanças relevantes na base.

## Estado atual

O DevTOLAS é a fonte da verdade da metodologia comum utilizada pelos projetos
consumidores. Cada workspace ativo contém somente a raiz do projeto; quando uma
norma comum for necessária, o `AGENTS.md` local aponta para o documento
específico do DevTOLAS como referência externa.

Integrações com ferramentas, skills e automações pertencem à aplicação
operacional. Elas serão adicionadas apenas quando houver necessidade concreta e
benefício demonstrável, sem se tornarem fundamentos da metodologia.
