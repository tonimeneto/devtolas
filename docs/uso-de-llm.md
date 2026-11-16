# Uso de LLM

## Objetivo

Definir a política transversal para uso de modelos de linguagem em qualquer
componente do Ecossistema DEV. A norma é arquitetural e independente de
fornecedor, modelo, API, ferramenta ou tipo de agente.

## Aplicabilidade e vigência

Esta é a fonte normativa única para uso de LLM no DevTOLAS. Os requisitos de
interfaces conversacionais são obrigatórios para todos os projetos consumidores
que utilizem LLM como interface conversacional, independentemente de linguagem,
framework, fornecedor, modelo ou ferramenta de desenvolvimento.

Aplicam-se a projetos novos e existentes, criação de funcionalidades, manutenção,
diagnóstico, correção de defeitos, refatorações, testes de conformidade e
auditorias técnicas, respeitando o escopo autorizado de cada atividade. Nos
projetos existentes corretamente vinculados ao DevTOLAS, devem ser consultados e
aplicados nas próximas intervenções pertinentes; sua vigência não autoriza
alterações automáticas ou em massa.

Não se exige adicionar conversação a aplicativos que não necessitem dela.
Uma auditoria exclusivamente administrativa de workspace não certifica a
conformidade conversacional do código. A conformidade de cada produto depende
das evidências definidas nesta norma.

## Princípios obrigatórios

Informações determinísticas, estáveis e reutilizáveis não devem ser reenviadas
desnecessariamente à LLM. Cada chamada deve receber somente o menor contexto
suficiente para executar corretamente a tarefa.

Uma LLM não deve executar trabalho que possa ser resolvido adequadamente, com
maior previsibilidade e eficiência, por processamento determinístico.

Em uma interface conversacional, a interpretação semântica é responsabilidade
da LLM. A preferência por processamento determinístico não autoriza substituir
essa interpretação por reconhecimento rígido de frases ou palavras-chave.

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

## Arquitetura de interfaces conversacionais

### Responsabilidade da LLM

A LLM deve interpretar linguagem natural e intenções, referências implícitas,
relações com mensagens anteriores, perguntas complementares e correções do
usuário. Deve reconhecer mudanças e retomadas de assunto, conduzir a conversa
dentro do domínio do aplicativo, identificar ambiguidades que exigem
esclarecimento e propor o uso das ferramentas autorizadas.

A LLM não pode ser reduzida a um mecanismo que apenas reformula respostas
previamente escolhidas pelo código. O usuário deve poder conversar naturalmente,
sem memorizar comandos ou expressões especiais.

### Responsabilidade do código determinístico

O código permanece responsável por autenticação, autorização, permissões,
validação de parâmetros, regras de negócio, cálculos exatos, contratos e
protocolos, execução segura de ferramentas, persistência e integridade,
idempotência, segurança operacional e verificação dos resultados. Essas rotinas
não devem substituir a interpretação semântica da conversa.

### Mecanismos proibidos de compreensão

É proibido utilizar como mecanismo principal de compreensão conversacional:

- listas crescentes de palavras-chave ou frases específicas cadastradas;
- expressões regulares para simular compreensão;
- condicionais que reconheçam perguntas por sua redação;
- respostas fixas disfarçadas de inteligência artificial;
- exceções implementadas exclusivamente para corrigir uma frase que falhou;
- roteamentos semânticos rígidos que impeçam a LLM de interpretar a intenção real.

Uma chamada à API de uma LLM não comprova conformidade se o código já decidiu
semanticamente o significado da mensagem e usa o modelo apenas para redigir.
Continuam permitidos mecanismos determinísticos adequados para segurança,
protocolos, comandos explicitamente estruturados, validações e operações
verificáveis, sem exigir esses comandos como condição para conversar.

### Domínio e segurança

A LLM deve operar exclusivamente dentro do domínio e das capacidades autorizadas
do aplicativo. Não pode inventar regras, informações documentais, autorizações,
resultados de ferramentas, operações concluídas, disponibilidade de recursos
ou dados inexistentes.

O código deve validar as operações propostas pelo modelo antes de executá-las.
A resposta ao usuário deve refletir o resultado efetivamente observado; falhas,
ambiguidades e indisponibilidades devem ser comunicadas adequadamente.

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

Em interfaces conversacionais, o aplicativo deve preservar e recuperar o
histórico, o estado e os resultados relevantes para a continuidade, garantindo
que o contexto necessário seja efetivamente disponibilizado ao modelo. Ter
informações gravadas no banco não comprova que a LLM as recebeu.

Podem ser usados histórico recente, resumos estruturados, recuperação seletiva,
memória persistente proporcional, estado operacional de solicitações e
referências a resultados anteriores. Não é obrigatório enviar todo o histórico;
a seleção e a compactação devem preservar fatos, referências, correções,
entidades e pendências relevantes.

Respeitar isolamento entre usuários e sessões, permissões, privacidade, retenção
e limites financeiros. Não se impõe memória permanente indiscriminada.

## Cache e reutilização

Quando um resultado determinístico, estável ou suficientemente reutilizável
puder ser persistido, cacheado, indexado, pré-processado ou calculado uma vez,
preferir sua reutilização adequada a pedir repetidamente à LLM que o reconstrua.
O mecanismo depende da arquitetura local.

## Ferramentas e agentes

Ferramentas usadas por uma LLM devem produzir, preferencialmente, saída
estruturada, mínima e filtrada antes de entrar no contexto. Não devolver
conteúdo excessivo sem uso previsto.

As ferramentas devem fornecer resultados verificáveis. Sua execução e a
comunicação dos resultados seguem as responsabilidades definidas em
[Arquitetura de interfaces conversacionais](#arquitetura-de-interfaces-conversacionais).

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

## Correção de defeitos conversacionais

Toda falha de compreensão conversacional deve ser investigada pela causa raiz.
A investigação deve considerar:

- arquitetura da orquestração e roteamento de intenções;
- histórico efetivamente enviado ao modelo e estado da conversa;
- persistência e recuperação de memória;
- instruções do modelo e contratos de ferramentas;
- integração com a API;
- seleção e compactação de contexto;
- validações determinísticas que possam interferir na interpretação.

É proibido declarar uma falha resolvida apenas porque a frase original passou a
funcionar, ou implementar novos condicionais ou listas de expressões apenas para
fazer um teste específico passar. A correção deve demonstrar generalização para
outras formulações da mesma intenção e diferenciação entre intenções distintas.

Cada correção deve incluir regressões com formulações inéditas, não utilizadas
como base da implementação do ajuste. Quando a causa raiz não puder ser
comprovada, registrar a limitação e as hipóteses pendentes, sem declarar solução
definitiva.

## Testes de aceitação conversacional

São obrigatórios, quando aplicáveis ao produto, testes de:

1. conversas completas, da solicitação inicial até a conclusão;
2. paráfrases inéditas;
3. variação na ordem das informações;
4. referências implícitas, como "aquele", "o segundo" e "o anterior";
5. correção de informações anteriormente fornecidas;
6. mudança de assunto e retomada posterior;
7. ambiguidades que exigem esclarecimento;
8. conversas longas com recuperação ou compactação de contexto;
9. isolamento entre usuários e sessões;
10. tentativas de operações não autorizadas;
11. falhas de ferramentas e indisponibilidade do modelo;
12. correspondência entre resultados reais e respostas comunicadas.

Os testes de compreensão devem exercitar a integração efetiva com a LLM.
Mocks são permitidos para ferramentas, persistência, segurança e regras
determinísticas, mas não comprovam compreensão semântica. Não exigir redação
literal idêntica; avaliar significado, continuidade, segurança e efeitos
observáveis.

Os limiares de qualidade e o número de repetições devem ser proporcionais ao
domínio e ao risco de cada projeto. Falhas críticas de autorização, isolamento
ou afirmações falsas de sucesso impedem a aprovação.

## Evidências de conformidade

A conformidade exige evidências documentais, arquiteturais e comportamentais.
Não são suficientes, isoladamente: uma API OpenAI ou de outro fornecedor,
prompts, uma referência no `AGENTS.md`, testes unitários com respostas simuladas
ou uma demonstração bem-sucedida com uma única frase.

Quando aplicável, as evidências devem permitir verificar:

- entrada do usuário e contexto relevante efetivamente disponibilizado;
- modelo e configuração utilizados;
- interpretação e proposta observáveis, sem acesso a raciocínio interno privado;
- ferramentas acionadas e validações realizadas;
- resultados efetivos e resposta final;
- casos aprovados, reprovados ou bloqueados.

Não registrar segredos, dados pessoais desnecessários ou raciocínio interno
privado do modelo. As evidências devem respeitar as regras de segurança e
privacidade de [governanca.md](governanca.md).

## Princípio de integração

A IA compreende e conduz a conversa. O código valida e executa operações seguras.
A memória preserva a continuidade. As ferramentas fornecem evidências. O usuário
conversa naturalmente, sem precisar aprender comandos.
