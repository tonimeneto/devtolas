# Uso de LLM

## Objetivo

Definir a política transversal para uso de modelos de linguagem em qualquer
componente do Ecossistema DEV. A norma é arquitetural e independente de
fornecedor, modelo, API, ferramenta ou tipo de agente.

## Princípios obrigatórios

Informações determinísticas, estáveis e reutilizáveis não devem ser reenviadas
desnecessariamente à LLM. Cada chamada deve receber somente o menor contexto
suficiente para executar corretamente a tarefa.

Uma LLM não deve executar trabalho que possa ser resolvido adequadamente, com
maior previsibilidade e eficiência, por processamento determinístico.

A primeira decisão não é como reduzir tokens, mas se a LLM é necessária para a
operação:

```text
Existe necessidade real de interpretação,
geração ou raciocínio probabilístico?
        │
        ├── NÃO → processamento determinístico
        │
        └── SIM
              ↓
        definir o menor contexto suficiente
              ↓
        recuperar somente esse contexto
              ↓
        chamar a LLM
```

## Contexto mínimo suficiente

Uma chamada deve receber as instruções, os dados, o estado e o conhecimento
necessários à decisão atual. Não deve receber automaticamente:

- documentação ou histórico completos;
- arquivos e dados não relacionados;
- dados estáveis já processados;
- resultados determinísticos reproduzíveis;
- conhecimento que não influencia a tarefa atual.

Menor contexto suficiente não significa menor contexto possível. Correção,
segurança e clareza têm prioridade sobre economia de contexto.

## Carregamento progressivo

Aplicar o contrato de contexto definido em [governanca.md](governanca.md):

```text
identificar a necessidade
        ↓
localizar a fonte autorizada
        ↓
recuperar a parte relevante
        ↓
fornecer à LLM
```

Não carregar tudo para pedir à LLM que descubra o que era relevante. O
carregamento progressivo se aplica a documentação, RAG, memória, histórico de
conversa, ferramentas, agentes e pipelines.

## Processamento determinístico

Quando não houver benefício real no uso de LLM, preferir código ou scripts para
operações como:

- validações estruturais e de JSON;
- cálculos determinísticos;
- parsing e transformações previsíveis;
- filtragem, ordenação e busca exata;
- substituição de placeholders;
- manipulação mecânica de arquivos.

O critério é a natureza da operação, não uma tecnologia específica.

## RAG e recuperação

RAG não significa enviar todo o conhecimento disponível. A recuperação deve
selecionar conteúdo conforme:

- escopo e relevância para a tarefa;
- granularidade e quantidade adequadas;
- atualidade;
- autoridade da fonte.

Evitar duplicar no prompt informação já representada de forma suficiente em
outro trecho recuperado.

## Memória, histórico e estado persistido

Conhecimento persistido não é sinônimo de contexto enviado à chamada atual. A
existência de informação em banco, arquivo, cache, memória, índice ou estado da
aplicação não exige seu envio em toda chamada. Selecionar somente o que
influencia a tarefa atual.

## Cache e reutilização

Quando um resultado determinístico, estável ou suficientemente reutilizável
puder ser persistido, cacheado, indexado, pré-processado ou calculado uma vez,
preferir sua reutilização adequada a pedir repetidamente à LLM que o reconstrua.
O mecanismo depende da arquitetura local.

## Ferramentas e agentes

Ferramentas usadas por uma LLM devem produzir, preferencialmente, saída
estruturada, mínima e filtrada antes de entrar no contexto. Não devolver
conteúdo excessivo sem uso previsto.

Em arquiteturas multiagente, não transmitir automaticamente todo o contexto de
um agente para outro. Cada agente deve receber somente o necessário à sua
responsabilidade.

## Prompts

Prompts devem conter instruções suficientes e inequívocas, evitando repetição,
documentação integral desnecessária, exemplos redundantes e conhecimento
estável que possa ser recuperado sob demanda. Clareza não deve ser sacrificada
apenas para reduzir tokens.

## Exceções justificadas

Contexto adicional pode ser necessário para segurança, correção,
desambiguação, consistência, auditoria, requisitos legais ou decisões que
dependam efetivamente de histórico maior. A ampliação deve responder a uma
necessidade funcional, não à conveniência de enviar tudo.
