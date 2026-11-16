# Método de desenvolvimento

O DevTOLAS adota um fluxo de referência, ajustado à dimensão e ao risco de cada
tarefa.

## 1. Analisar

Compreender objetivo, contexto, restrições, estado atual e critérios de sucesso.
Consultar as fontes oficiais do projeto antes de tomar decisões. Quando
documentação e comportamento observado divergirem, registrar o conflito em vez
de escolher silenciosamente uma das fontes.

Quando a tarefa envolver LLM, aplicar a decisão de necessidade e o contexto
mínimo suficiente definidos em [uso-de-llm.md](uso-de-llm.md).

Se houver interface conversacional com LLM, é obrigatória a consulta aos
requisitos arquiteturais dessa mesma norma em criação, manutenção, diagnóstico,
correção, refatoração, testes e auditorias técnicas pertinentes, em projetos
novos e existentes. A consulta não amplia a autorização da tarefa.

## 2. Planejar

Definir a menor mudança capaz de atingir o objetivo e identificar como ela será
validada.

## 3. Implementar

Executar a mudança preservando o escopo, a simplicidade e as convenções do
projeto ativo.

Regras críticas, autorização, integridade e segurança devem permanecer em
fronteiras compatíveis com o nível de confiança exigido pelo sistema. A
arquitetura do projeto define quais componentes formam essas fronteiras.

Falhas e caminhos alternativos relevantes devem ser explícitos e observáveis.
Não introduzir fallback silencioso que esconda erro, perda de integridade ou
comportamento diferente do esperado.

## 4. Testar

Verificar o comportamento afetado com testes proporcionais ao risco da mudança.

Para interfaces conversacionais com LLM, aplicar os
[testes de aceitação conversacional](uso-de-llm.md#testes-de-aceitação-conversacional)
e, em correções, as regressões inéditas exigidas pela norma.

## 5. Auditar

Revisar segurança, regressões, consistência, duplicação e aderência ao objetivo.

Em auditorias técnicas de interfaces conversacionais com LLM, avaliar as
[evidências de conformidade](uso-de-llm.md#evidências-de-conformidade) dentro do
escopo contratado. Auditoria administrativa de workspace não certifica o
comportamento conversacional do código.

## 6. Documentar

Atualizar somente a documentação impactada pela mudança.
Classificar novos artefatos conforme [documentacao.md](documentacao.md).

## 7. Avaliar o aprendizado

Verificar se surgiu conhecimento realmente reutilizável. Aprendizados
específicos permanecem no projeto de origem; aprendizados comuns podem ser
propostos ao DevTOLAS.

Quando a tarefa continuar em outra sessão, registrar somente o contexto
necessário conforme `docs/continuidade.md`.

## Fechamento preventivo de mudança

Quando uma mudança alterar responsabilidade existente, verificar de forma
proporcional:

1. implementação canônica anterior e consumidores identificados;
2. estratégia explícita: modificar, substituir ou coexistir;
3. caminho resultante validado;
4. caminho anterior integrado ou retirado, ou coexistência justificada;
5. referências, testes, configuração e documentação reconciliados.

Esse fechamento previne caminhos concorrentes. Tarefas que apenas acrescentam
conteúdo independente não exigem a cerimônia completa.

## Aplicação proporcional

O fluxo não exige cerimônia desnecessária. Tarefas pequenas podem combinar
etapas, desde que a análise e a validação não sejam omitidas quando forem
relevantes.
