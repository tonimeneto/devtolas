# Criação de projetos

## Objetivo

Criar um projeto isolado e integrá-lo ao DevTOLAS sem escolher antecipadamente
linguagem, framework, banco, provedor ou arquitetura.

## Informações necessárias

- nome do projeto;
- objetivo inicial;
- restrições, quando existirem;
- caminho e repositório, quando já definidos.

## Verificações iniciais

Antes de criar arquivos:

1. confirmar a raiz organizacional vigente;
2. verificar se já existem pasta, workspace ou repositório com o mesmo nome;
3. resolver os caminhos de projeto, DevTOLAS e workspace;
4. preservar arquivos e alterações existentes;
5. apresentar ambiguidades ou riscos de sobrescrita.

## Estrutura mínima

Criar apenas:

```text
NOME_DO_PROJETO/
├── AGENTS.md
├── README.md
└── docs/
```

Outras pastas devem nascer quando a tecnologia ou a necessidade do projeto as
justificar.

## Instruções locais

Gerar o `AGENTS.md` a partir de
`templates/projeto/AGENTS.md.template`, preenchendo somente informações
conhecidas e mantendo marcadores explícitos para decisões pendentes.

As instruções locais devem:

- apontar para a governança do DevTOLAS;
- definir o projeto e seu escopo;
- listar fontes oficiais;
- registrar arquitetura e tecnologias somente depois de decididas;
- fornecer comandos seguros de validação;
- identificar caminhos sensíveis sem revelar conteúdo.

## Workspace

Gerar o workspace a partir de
`templates/projeto/projeto.code-workspace.template`.

O workspace deve conter somente:

1. o projeto ativo;
2. o DevTOLAS como referência de método.

O DevTOLAS é somente leitura durante tarefas normais do projeto. Melhorias
comuns devem ser tratadas separadamente no repositório DevTOLAS.

## Git

Não inicializar repositório, alterar remotos, criar commits ou publicar sem
autorização compatível.

## Validação

Ao concluir:

1. validar o JSON do workspace;
2. confirmar que todos os caminhos existem;
3. confirmar que o projeto não depende do DevTOLAS em tempo de execução;
4. confirmar que nenhuma tecnologia foi escolhida sem decisão;
5. informar o workspace que deverá ser aberto em uma nova sessão.
