# Continuidade entre sessões

## Objetivo

Permitir a retomada de uma tarefa sem depender da memória de uma conversa e sem
transportar contexto desnecessário.

A continuidade pertence ao projeto ativo. O DevTOLAS define o método, mas não
armazena pacotes de continuidade de projetos consumidores.

## Quando registrar

Registrar continuidade quando:

- uma tarefa precisar continuar em outra sessão;
- houver trabalho implementado ainda não concluído;
- existirem decisões ou riscos que não possam ser reconstruídos com segurança
  apenas pelo repositório;
- o usuário solicitar um resumo para retomada.

Não criar pacotes por rotina quando a tarefa estiver concluída e o estado puder
ser compreendido diretamente pelo Git e pela documentação.

## Conteúdo mínimo

O registro deve conter:

1. projeto e caminho;
2. objetivo da tarefa;
3. estado atual;
4. alterações realizadas;
5. validações executadas e resultados;
6. decisões tomadas;
7. riscos ou impedimentos;
8. próxima ação concreta.

Não incluir:

- segredos;
- conteúdo integral de arquivos;
- histórico irrelevante da conversa;
- informações de outro projeto;
- decisões ainda não tomadas apresentadas como definitivas.

## Fonte de verdade

O pacote de continuidade é um apoio temporário. Antes de continuar:

1. confirmar o projeto ativo;
2. ler suas instruções;
3. verificar Git e arquivos atuais;
4. comparar o estado observado com o resumo;
5. tratar divergências explicitamente.

O repositório e a documentação vigente prevalecem sobre um resumo desatualizado.

## Encerramento

Ao finalizar uma tarefa, informar:

- resultado;
- arquivos alterados;
- validações realizadas;
- documentação atualizada ou avaliada;
- pendências reais;
- aprendizado reutilizável identificado, se houver.

Comandos vinculados ao GPTOLAS, como `GPTST INICIAR` e `GPTST ENCERRAR`, não
fazem parte do DevTOLAS.
