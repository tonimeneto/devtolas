# AGENTS.md — DevTOLAS

## Escopo

Este arquivo controla o trabalho no repositório DevTOLAS. O repositório contém
o método comum de engenharia do Ecossistema DEV; não contém arquitetura, regras
de negócio nem estado operacional dos projetos consumidores.

Trabalhe na raiz `D:\MeusArquivos\Fs\Projetos\DevTolas` e preserve alterações
preexistentes que não pertençam à tarefa.

## Roteamento

Consulte somente a norma necessária:

- autoridade, autorização, isolamento, segurança e Git: `docs/governanca.md`;
- classificação e localização de informação: `docs/documentacao.md`;
- fluxo de engenharia e fechamento de mudanças: `docs/metodo-de-desenvolvimento.md`;
- estado operacional: `docs/estado-vigente.md`;
- uso de LLM e seleção de contexto: `docs/uso-de-llm.md`;
- continuidade entre sessões: `docs/continuidade.md`;
- transferência entre contextos: `docs/handoff-contextos.md`;
- evolução de normas comuns: `docs/evolucao-do-conhecimento.md`;
- criação de projetos: `docs/criacao-de-projetos.md`.

Em criação, manutenção, diagnóstico, correção, refatoração, testes e auditorias
técnicas pertinentes de interfaces conversacionais com LLM, é obrigatória a
consulta a `docs/uso-de-llm.md`, fonte normativa única dessa arquitetura. Sua
aplicação aos projetos consumidores respeita o escopo autorizado de cada tarefa.

A precedência técnica das instruções é determinada pelo Codex. A autoridade de
cada fonte e os limites da tarefa pertencem a `docs/governanca.md`.

## Regras específicas deste repositório

- Mantenha o método independente de ferramenta e tecnologia quando a matéria
  for realmente transversal.
- Incorpore conhecimento de outro projeto somente quando a tarefa autorizar e
  a avaliação de `docs/evolucao-do-conhecimento.md` demonstrar reutilização.
- Preserve o histórico necessário das decisões metodológicas sem mantê-lo como
  orientação vigente.
- Trate melhorias comuns neste repositório, separadamente das tarefas normais
  dos projetos consumidores.

## Validação

Após mudanças, valide links, consistência entre as normas afetadas e o estado do
Git. Quando a alteração substituir uma responsabilidade existente, aplique o
fechamento definido em `docs/metodo-de-desenvolvimento.md`.
