# Migração de Fs\Comum

## Objetivo

Avaliar os materiais compartilhados existentes em `Fs\Comum` e definir o
tratamento de cada um, mantendo o DevTOLAS como única fonte ativa do método de
engenharia.

Este documento não autoriza copiar, mover, renomear ou excluir arquivos. A área
`Fs\Comum` permanece somente leitura durante a classificação.

## Escopo avaliado

Foram considerados:

- políticas comuns para agentes;
- guia de contexto e isolamento;
- templates de projeto e workspace;
- procedimento de criação de projetos;
- metodologia GPTOLAS;
- relatórios recentes de governança relacionados a projetos, agentes e
  workspaces;
- configurações de ambiente com possível conhecimento reutilizável.

Não foram usados como fonte de método:

- código ou documentação interna de projetos;
- arquivos sensíveis;
- backups;
- mídia;
- instaladores;
- cursos e documentação tecnológica antiga;
- prompts ou bases de conhecimento específicos de sistemas.

## Classificação

| Material atual | Tratamento | Destino ou decisão |
|---|---|---|
| `IA\POLITICA-COMUM-AGENTES.md` | Incorporar com adaptação | Governança de segurança, autorização, isolamento, Git e proteção de segredos no DevTOLAS. |
| `IA\GUIA-DE-CONTEXTO-E-ISOLAMENTO.md` | Incorporar com adaptação | Método de início, condução e encerramento de sessões no contexto de um único projeto. |
| `Templates\MODELO-AGENTS-PROJETO.md` | Migrar e evoluir | Criar template oficial de instruções locais em `templates\projeto`. |
| `Templates\MODELO-PROJETO.code-workspace` | Migrar e evoluir | Criar template oficial de workspace com projeto e DevTOLAS. |
| `Templates\Projetos\iniciar-novo-projeto.md` | Migrar e evoluir | Transformar em procedimento oficial de criação de projetos do DevTOLAS. |
| `Metodologia\GPTOLAS` | Migrar seletivamente | Seguir a classificação registrada em `docs/migracoes/gptolas.md`; depois arquivar fora do contexto ativo. |
| Relatórios de execução em `Fs\Governanca` | Extrair padrões | Incorporar o processo de diagnosticar, propor, autorizar, executar, validar e registrar. Não copiar relatórios históricos. |
| Histórico de workspaces | Manter fora | Preservar como governança histórica; não pertence ao método ativo. |
| Configuração e base de conhecimento do SIES | Manter específica | Não transportar conteúdo. Considerar futuramente apenas um template neutro de base de conhecimento local. |
| Materiais de arquitetura, dados, infraestrutura e tecnologias | Avaliar sob demanda | Não promover pastas ou tecnologias inteiras a padrões universais. |
| Mídia e prompts específicos de ferramentas | Manter fora | Não fazem parte do núcleo atual do sistema de desenvolvimento. |
| Cursos, MOCs e documentação tecnológica antiga | Tratar como acervo | Consultar somente quando uma necessidade tecnológica específica justificar. |

## Conhecimento reutilizável identificado

### Isolamento

- trabalhar com um único projeto ativo;
- expor ao agente somente o projeto e referências comuns autorizadas;
- impedir transferência automática de código, regras e decisões entre projetos;
- manter documentação específica dentro do projeto de origem.

### Segurança

- não abrir ou reproduzir segredos sem necessidade e autorização;
- ocultar `.env`, artefatos e dependências das pesquisas usuais;
- tratar ocultação no workspace como redução de exposição, não como barreira de
  segurança;
- sanitizar remotos e metadados antes de relatá-los.

### Operações controladas

- separar diagnóstico, proposta e execução;
- exigir autorização proporcional ao impacto;
- validar alvos antes de mover, substituir ou excluir;
- trabalhar em lotes pequenos;
- registrar o que foi alterado, preservado, validado e não executado.

### Git

- confirmar repositório, branch, remoto sanitizado e alterações locais antes de
  editar;
- não presumir que uma pasta de projeto é um repositório;
- não alterar configurações globais para contornar limitações locais;
- executar operações remotas somente dentro do escopo autorizado.

### Workspaces

- combinar o projeto específico com uma referência comum somente leitura;
- excluir de pesquisas `.git`, dependências, builds e arquivos de ambiente;
- validar o JSON e a resolução dos caminhos;
- não usar o workspace como substituto de políticas de acesso.

### Rastreabilidade

O fluxo reutilizável observado nos relatórios de governança é:

```text
diagnosticar
    ↓
propor
    ↓
autorizar
    ↓
executar
    ↓
validar
    ↓
registrar
```

Esse fluxo complementa o método de desenvolvimento e deve ser aplicado a
operações organizacionais ou destrutivas de acordo com o risco.

## Inconsistências a resolver

Os templates e relatórios históricos usam mais de uma forma de caminho, entre
elas:

- `D:\MeusArquivos\Fs`;
- `D:\MeusArquivos\30 - Fs`.

Materiais migrados devem usar a estrutura vigente ou parâmetros que evitem
acoplamento desnecessário a um caminho absoluto.

O modelo atual de workspace referencia `Fs\Comum`. O modelo futuro deverá
referenciar o projeto ativo e o DevTOLAS, mas essa troca somente ocorrerá depois
da criação e validação do novo template.

## Ordem de incorporação

1. governança de contexto, segurança e operações;
2. template de `AGENTS.md` para projetos;
3. template de workspace;
4. procedimento de criação de projetos;
5. continuidade entre sessões;
6. integração piloto com um projeto autorizado.

Cada item será tratado em uma mudança pequena e revisável.

## Critérios para encerrar a transição

`Fs\Comum` deixará de ser fonte do método quando:

1. políticas e procedimentos aprovados existirem no DevTOLAS;
2. templates oficiais forem fornecidos pelo DevTOLAS;
3. workspaces consumidores apontarem para a nova fonte;
4. não existirem referências ativas ao GPTOLAS;
5. materiais históricos estiverem fora das raízes consultadas normalmente;
6. uma integração piloto tiver sido validada.

Conteúdos compartilhados que não representem método de engenharia podem
permanecer fora do DevTOLAS, com responsabilidade explicitamente separada.
