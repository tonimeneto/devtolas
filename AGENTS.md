# AGENTS.md — DevTOLAS

## Propósito

O DevTOLAS é uma base de engenharia de software reutilizável, documentada e
evolutiva. Ele fornece método de trabalho para outros projetos, mas não substitui
a documentação, a arquitetura nem as regras de negócio de cada projeto.

## Princípios de atuação

Ao trabalhar neste repositório:

- priorize simplicidade, clareza e manutenção;
- evolua a base de forma incremental;
- evite estruturas ou automações sem necessidade comprovada;
- diferencie conhecimento comum de decisões específicas de projetos;
- não transfira regras de negócio entre projetos;
- preserve o histórico das decisões relevantes;
- trate práticas existentes como passíveis de revisão;
- consulte a documentação deste repositório antes de propor mudanças.

## Fluxo de trabalho

Sempre que aplicável:

1. analisar;
2. planejar;
3. implementar;
4. testar;
5. auditar;
6. documentar;
7. avaliar se houve aprendizado reutilizável.

Execute apenas as etapas proporcionais ao tamanho e ao risco da tarefa.

## Limites

- Não transformar o DevTOLAS em um framework sem necessidade.
- Não adicionar dependência de tecnologia específica como padrão universal.
- Não incorporar conteúdo de outro projeto sem autorização e validação de que
  ele é realmente reutilizável.
- Não alterar a área comum compartilhada durante tarefas deste projeto.
- Não executar operações Git externas, como `pull`, `push` ou alteração de
  remotos, sem autorização compatível com a tarefa.

## Fontes de orientação

Respeite, nesta ordem:

1. segurança e autorização do usuário;
2. políticas comuns aplicáveis ao workspace;
3. este arquivo;
4. `docs/governanca.md`;
5. demais documentos em `docs/`;
6. tarefa atual.

## Evolução

Uma melhoria somente deve virar orientação comum quando:

- puder ser aplicada sem depender do domínio de um projeto;
- possuir justificativa clara;
- tiver seu estado registrado conforme `docs/evolucao-do-conhecimento.md`;
- não contradizer uma orientação superior.
