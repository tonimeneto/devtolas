# Estado vigente

## Objetivo

Representar, quando necessário, a menor visão operacional capaz de retomar um
trabalho sem depender do histórico da conversa.

Não se cria um arquivo de estado por padrão. O projeto deve adotá-lo quando uma
tarefa longa, múltiplas sessões ou decisões em evolução não puderem ser
reconstruídas com segurança pelo código, Git e documentação permanente.

## Contrato mínimo

O estado vigente deve informar:

- objetivo ativo;
- situação: ativo, bloqueado, concluído ou substituído;
- decisões vigentes e, quando houver, o que substituíram;
- evidências ou fontes para verificar a realidade;
- pendências reais;
- próxima ação, quando necessária;
- data da atualização e responsável pela atualização.

O `AGENTS.md` deve apontar para a fonte de estado adotada pelo projeto. O nome do
arquivo pode seguir a linguagem local; sua função e vigência precisam ser
inequívocas.

## Regras de vigência

- Uma decisão nova substitui a anterior somente quando a substituição estiver
  explícita na fonte canônica.
- Conteúdo substituído deixa de orientar a operação e deve apontar para o vigente
  enquanto permanecer no ESD.
- Histórico necessário pode ser preservado fora do contexto ativo.
- Estado declarado deve ser reconciliado com código, Git, testes, configuração e
  ambientes observáveis antes da retomada.
- Ao concluir o trabalho, encerrar ou retirar o estado temporário; não mantê-lo
  artificialmente ativo.

## Relação com continuidade e handoff

- mesma responsabilidade em outra sessão: continuidade;
- estado atual durável do trabalho: estado vigente;
- transferência entre contextos ou responsabilidades: handoff.

Memória da IA auxilia a recuperação, mas não substitui essas fontes quando a
fidelidade for importante.
