# Criação de projetos

## Objetivo

Criar um projeto isolado e integrá-lo ao DevTOLAS sem escolher antecipadamente
linguagem, framework, banco, provedor ou arquitetura.

## Informações necessárias

- nome do projeto;
- alias do projeto, informado pelo usuário;
- objetivo inicial;
- restrições, quando existirem;
- caminho e repositório, quando já definidos.

## Verificações iniciais

Antes de criar arquivos:

1. confirmar a raiz organizacional vigente;
2. resolver os caminhos de projeto, DevTOLAS e workspace;
3. validar o alias sem diferenciar maiúsculas e minúsculas no registro
   `D:\MeusArquivos\Governanca\aliases.md`;
4. verificar se já existem pasta, workspace ou repositório com o mesmo nome;
5. preservar arquivos e alterações existentes;
6. apresentar ambiguidades ou riscos de sobrescrita.

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
- funcionar como roteador para a documentação necessária, sem reproduzi-la
  integralmente;
- definir o projeto e seu escopo;
- listar fontes oficiais;
- registrar arquitetura e tecnologias somente depois de decididas;
- fornecer comandos seguros de validação;
- identificar caminhos sensíveis sem revelar conteúdo.

Se o produto incluir interface conversacional com LLM, o roteamento para
[uso-de-llm.md](uso-de-llm.md) é obrigatório, conforme o template. Consultar a
norma na definição da arquitetura e dos critérios de aceitação, sem reproduzi-la
no projeto. Produtos sem essa necessidade não devem receber conversação por
exigência metodológica.

Quando a criação ocorrer em ferramenta que não acesse as referências locais,
fornecer efetivamente o conteúdo canônico vigente de `uso-de-llm.md`, por anexo
ou outro meio suportado, e confirmar sua leitura no planejamento. Informar
apenas o caminho não fornece o conteúdo. O material enviado é referência
datada à fonte, sem constituir cópia normativa independente. No fluxo Lovable,
a skill `criar-projeto-lovable` orienta esse fornecimento condicional.

## Workspace

Gerar o workspace a partir de
`templates/projeto/projeto.code-workspace.template`.

O workspace deve conter exatamente uma raiz: o projeto ativo.

O DevTOLAS permanece fora das raízes do workspace. Quando houver norma comum
aplicável, o `AGENTS.md` do projeto aponta diretamente para o documento
necessário.

O DevTOLAS é somente leitura durante tarefas normais do projeto. Melhorias
comuns devem ser tratadas separadamente no repositório DevTOLAS.

Exclusivamente no fluxo oficial da skill `criar-projeto`, após criar e validar
o projeto, registrar em `D:\MeusArquivos\Governanca\aliases.md` o alias informado, o nome canônico,
o tipo `Projeto` e o caminho real criado. Não duplicar um registro da mesma
entidade e interromper antes da criação se o alias pertencer a outra entidade.

A criação de documentação deve seguir [documentacao.md](documentacao.md), sem
gerar diretórios ou arquivos vazios apenas para completar uma taxonomia.

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
6. confirmar que o alias está registrado uma única vez no registro canônico.
7. se houver interface conversacional com LLM, confirmar o roteamento para a
   norma e, em ferramentas sem acesso local, o fornecimento efetivo do conteúdo
   vigente e sua consideração nos critérios de aceitação.
