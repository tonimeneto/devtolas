# Método de desenvolvimento

O DevTOLAS adota um fluxo de referência, ajustado à dimensão e ao risco de cada
tarefa.

## 1. Analisar

Compreender objetivo, contexto, restrições, estado atual e critérios de sucesso.
Consultar as fontes oficiais do projeto antes de tomar decisões. Quando
documentação e comportamento observado divergirem, registrar o conflito em vez
de escolher silenciosamente uma das fontes.

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

## 5. Auditar

Revisar segurança, regressões, consistência, duplicação e aderência ao objetivo.

## 6. Documentar

Atualizar somente a documentação impactada pela mudança.

## 7. Avaliar o aprendizado

Verificar se surgiu conhecimento realmente reutilizável. Aprendizados
específicos permanecem no projeto de origem; aprendizados comuns podem ser
propostos ao DevTOLAS.

Quando a tarefa continuar em outra sessão, registrar somente o contexto
necessário conforme `docs/continuidade.md`.

## Aplicação proporcional

O fluxo não exige cerimônia desnecessária. Tarefas pequenas podem combinar
etapas, desde que a análise e a validação não sejam omitidas quando forem
relevantes.
