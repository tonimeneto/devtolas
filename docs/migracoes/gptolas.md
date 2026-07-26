# Migração do GPTOLAS

**Status:** concluída em 26/07/2026.

## Objetivo

Transferir para o DevTOLAS somente o conhecimento reutilizável e fundamentado do
GPTOLAS, tornando o DevTOLAS a única fonte ativa do método de engenharia.

Esta migração não copia os documentos antigos para o DevTOLAS. Ela registra as
decisões extraídas, sua avaliação e o destino dado a cada uma.

## Fontes avaliadas

- `GPTOLAS_MASTER_REFERENCE.md`, versão 2.0, de 04/07/2026;
- `GPTOLAS_CHAT_PROTOCOL.md`, versão 1.0.0, de 04/07/2026.

Durante a classificação, as fontes permaneceram inalteradas em `Fs\Comum`.

## Critérios

Cada orientação recebe um estado definido em
`docs/evolucao-do-conhecimento.md`:

- `validado`: pode integrar o método comum;
- `provisório`: é útil, mas precisa de confirmação;
- `experimental`: pode ser testado de forma controlada;
- `depreciado`: não deve orientar novos trabalhos;
- `rejeitado`: não pertence ao método comum.

Uma orientação tecnicamente útil, mas dependente do tipo de sistema, deve ser
tratada como padrão contextual e não como princípio universal.

## Classificação inicial

| Conhecimento | Estado | Decisão e destino |
|---|---|---|
| Trabalhar com um único projeto ativo | Validado | Manter como princípio de isolamento de contexto. |
| Não misturar documentação, arquitetura ou regras entre projetos | Validado | Já representado pelos princípios do DevTOLAS. |
| Consultar a documentação oficial do projeto ativo | Validado | Incorporar ao método, respeitando a precedência definida pelo DevTOLAS. |
| Priorizar estabilidade, previsibilidade, simplicidade, reutilização, documentação e evolução incremental | Validado | Já incorporado em `docs/principios.md`. |
| Tratar decisões anteriores como passíveis de revisão | Validado | Já incorporado como revisão contínua. |
| Exigir sempre Programa, Backend e Banco | Rejeitado como regra universal | Pode existir futuramente como padrão contextual para sistemas distribuídos em camadas. |
| Proibir toda regra de negócio no frontend | Rejeitado como regra universal | A distribuição de responsabilidades depende da arquitetura e do risco do projeto. |
| Manter regras críticas e segurança em uma fronteira confiável | Provisório | Reformular como princípio de confiança, sem exigir uma tecnologia ou camada chamada backend. |
| Backend como única fonte da verdade | Rejeitado como regra universal | Pode ser válido para determinadas arquiteturas cliente-servidor. |
| Integridade estrutural garantida pelo banco | Provisório | Aplicável quando existe banco com capacidade para impor essas garantias. |
| Pipeline único | Provisório | Avaliar como padrão de redução de caminhos concorrentes, não como obrigação universal. |
| Ausência de fallback silencioso | Validado | Incorporar como princípio de comportamento explícito e observável. |
| Remoção de legado incompatível | Provisório | Exige avaliação de compatibilidade, risco e estratégia de migração. |
| Preferência por Add-Only | Rejeitado como regra universal | Manter somente em projetos que adotem explicitamente essa estratégia. |
| Todo plano deve declarar Programa, Backend e Banco | Rejeitado como regra universal | O plano deve declarar apenas componentes existentes e afetados. |
| Fluxo de análise, planejamento, implementação, testes, auditoria e documentação | Validado com adaptação | O fluxo vigente está em `docs/metodo-de-desenvolvimento.md` e deve ser proporcional ao risco. |
| Executar um teste por vez | Rejeitado como regra universal | Estratégia de testes depende do tipo de validação e do custo de execução. |
| Responder testes somente com `OK` ou `ERRO` | Rejeitado | Resultados devem conter evidência suficiente para diagnóstico e auditoria. |
| Usar um chat para uma única tarefa | Provisório | Preservar foco e isolamento, sem depender do conceito técnico de chat. |
| Comandos `GPTST INICIAR` e `GPTST ENCERRAR` | Depreciado | Não transportar comandos vinculados à identidade GPTOLAS. |
| Gerar pacote de continuidade | Provisório | Adaptar para um processo simples de encerramento quando houver troca de sessão. |
| O usuário não deve precisar reconstruir sozinho o contexto | Validado | A continuidade deve ser clara, verificável e limitada ao projeto ativo. |
| LLM nunca controla a lógica do sistema | Provisório | Reformular em termos de determinismo, supervisão e limites de confiança quando IA fizer parte do produto. |

## Conhecimento incorporado

Os itens aprovados foram adaptados sem transportar regras arquiteturais
específicas:

1. documentação do projeto como fonte local, em
   `docs/metodo-de-desenvolvimento.md`;
2. fronteiras confiáveis para regras críticas e segurança, em
   `docs/metodo-de-desenvolvimento.md`;
3. ausência de fallback silencioso, em
   `docs/metodo-de-desenvolvimento.md`;
4. continuidade entre sessões e tarefas, em `docs/continuidade.md`.

Itens provisórios ou contextuais permanecem sem promoção automática.

## Desativação do GPTOLAS

Os critérios de saída foram atendidos:

1. itens validados incorporados ao DevTOLAS;
2. referências ao GPTOLAS identificadas nos templates e projetos;
3. consumidores ativos apontando para o DevTOLAS;
4. origem histórica preservada fora das raízes abertas pelo Codex;
5. diretório antigo sem consumidores ativos.

O diretório original foi movido, com autorização, para:

```text
D:\MeusArquivos\30 - Fs\Arquivo\Metodologia\
Transicao-DevTOLAS-2026-07-26\Fontes-Antigas\
Comum\Metodologia\GPTOLAS
```

Esse local não participa dos workspaces ativos e existe somente para
rastreabilidade histórica.
