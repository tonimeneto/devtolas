# Organização documental

## Objetivo

Definir como classificar e localizar instruções, conhecimento, procedimentos e
operações no Ecossistema DEV, mantendo uma fonte normativa para cada regra.

Antes de criar um novo `.md`, skill, script ou instrução, classificar primeiro
a natureza da informação e somente então escolher seu local físico. O destino
não deve ser determinado apenas pela ferramenta em uso, pelo workspace aberto,
por conveniência temporária ou pelo projeto em que a necessidade apareceu.

## Taxonomia oficial

```text
Preferência pessoal ou comportamento universal do Codex
    → `C:\Users\anton\.codex\AGENTS.md`

Administração de `D:\MeusArquivos`
    → `D:\MeusArquivos\AGENTS.md`

Método comum de engenharia
    → `DevTOLAS\docs`

Comportamento do Codex específico de um projeto
    → `Projeto\AGENTS.md`

Conhecimento permanente do produto
    → `Projeto\docs`

Agentes de IA que fazem parte do produto
    → `Projeto\docs\agentes`

Procedimento operacional reutilizável
    → `Skill\SKILL.md`

Operação mecânica ou determinística
    → `Skill\scripts`
```

## Comum e específico

Usar a seguinte classificação inicial:

```text
Vale para vários projetos
    → avaliar incorporação ao DevTOLAS

Vale somente para um projeto
    → projeto

Descreve como o Codex deve trabalhar com o usuário
    → global pessoal

Descreve uma operação reutilizável
    → skill

É execução mecânica
    → script
```

O uso por dois ou mais projetos não promove automaticamente uma regra ao
DevTOLAS. Ela deve representar método realmente compartilhado, independente do
domínio local, e seguir a avaliação descrita em
[evolucao-do-conhecimento.md](evolucao-do-conhecimento.md).

## `AGENTS.md` como roteador

`AGENTS.md` não é depósito de todo o conhecimento disponível. Sua função
principal é fornecer instruções aplicáveis ao contexto e indicar quando e onde
buscar conhecimento adicional.

```text
Tarefa comum
    → `AGENTS.md` → código ou docs necessários

Tarefa de negócio
    → `AGENTS.md` → docs de negócio

Tarefa envolvendo LLM
    → `AGENTS.md` → norma DevTOLAS de LLM → docs locais de IA, se necessários
```

Não transformar `AGENTS.md` em manual completo do projeto.

## Agente de desenvolvimento e agentes do produto

`Projeto\AGENTS.md` contém instruções para o agente de desenvolvimento trabalhar
naquele projeto. `Projeto\docs\agentes\...` especifica agentes de IA
implementados pelo produto. Essas categorias não devem ser misturadas.

## Estrutura orientada por necessidade

A taxonomia define destinos possíveis, não uma lista obrigatória de arquivos ou
diretórios. Não criar automaticamente artefatos como `negocio.md`,
`arquitetura.md`, `dados.md`, `ia.md`, `agentes\` ou `decisoes\` sem conteúdo
real que os justifique. Documentação existe para registrar conhecimento, não
para preencher uma árvore.

## Fonte normativa única

Quando uma norma completa existir no DevTOLAS, projetos devem referenciá-la;
templates devem apontar para ela quando forem atualizados; e skills podem
consultá-la quando necessário. Não copiar integralmente a norma para múltiplos
lugares:

```text
uma regra → uma fonte normativa → referências onde necessário
```

## Estado e vigência

Documentos de decisão e estado devem distinguir conteúdo vigente, substituído e
histórico. Projetos que precisem de estado operacional persistido seguem o
contrato mínimo de [estado-vigente.md](estado-vigente.md); não se cria um arquivo
de estado apenas para completar uma estrutura.
