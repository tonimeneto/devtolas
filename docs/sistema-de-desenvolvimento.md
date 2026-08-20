# Metodologia de desenvolvimento DevTOLAS

## Objetivo

O DevTOLAS é a metodologia comum utilizada para conduzir projetos de software
com assistência de IA de forma consistente, documentada e evolutiva.

Ele organiza como o trabalho é analisado, planejado, implementado, validado,
documentado e aprimorado. Não executa o papel do sistema desenvolvido e não
substitui suas decisões específicas.

## Fonte da verdade

O DevTOLAS é a fonte oficial do método de engenharia.

Projetos consumidores podem adaptar a aplicação do método ao próprio contexto,
mas não devem manter cópias independentes das orientações comuns. Melhorias
reutilizáveis devem retornar ao DevTOLAS para beneficiar os projetos atuais e
futuros.

## Independência de ferramenta

Os conceitos, os princípios e o fluxo da metodologia não dependem de uma
ferramenta específica. Codex, outros assistentes, skills e automações são formas
possíveis de executá-la.

Na versão atual, o Codex no VS Code é a principal aplicação operacional. As
instruções específicas dessa aplicação devem permanecer separadas do núcleo
conceitual sempre que a distinção for relevante.

## Camadas

### 1. Método comum

Pertence ao DevTOLAS:

- princípios de engenharia;
- fluxo de desenvolvimento;
- padrões de análise, implementação, testes, revisão e auditoria;
- governança da documentação e do conhecimento;
- templates e mecanismos operacionais reutilizáveis, quando justificados;
- critérios para evolução do próprio método.

### 2. Aplicação local

Pertence ao projeto consumidor:

- objetivo e domínio;
- requisitos e regras de negócio;
- arquitetura e tecnologias escolhidas;
- código, testes e infraestrutura;
- decisões e documentação específicas;
- adaptações justificadas do método ao contexto local.

## Relação com o GPTOLAS

O GPTOLAS é uma origem histórica de aprendizados, não uma metodologia paralela.

Suas orientações devem ser avaliadas antes de entrar no DevTOLAS. Cada item pode
ser incorporado, adaptado, mantido como específico, depreciado ou rejeitado. A
adoção não ocorre apenas porque a orientação já foi utilizada anteriormente.

## Relação com a estrutura comum existente

A estrutura compartilhada em `Fs\Comum` antecede o DevTOLAS e continua
armazenando recursos compartilhados que não representam o método de engenharia.

As políticas, os templates e a metodologia anteriores foram avaliados e
migrados. O DevTOLAS é a única fonte metodológica ativa. O histórico foi
preservado fora das raízes abertas normalmente nos workspaces.

## Fluxo de evolução

```text
Experiência em projeto ou evidência relevante
          ↓
Identificação de aprendizado reutilizável
          ↓
Avaliação e classificação
          ↓
Incorporação ao DevTOLAS
          ↓
Aplicação nos projetos consumidores
```

Conhecimento específico permanece no projeto de origem. Ideias ainda sem
evidência suficiente podem ser registradas como hipóteses, mas não devem ser
promovidas automaticamente a orientações comuns.

## Autoridade e carregamento no projeto consumidor

Ao desenvolver um sistema, o DevTOLAS permanece como autoridade do método
comum. Isso não determina a ordem técnica de carregamento do Codex nem implica
herança automática da documentação metodológica.

O Codex carrega primeiro seu global pessoal e o `AGENTS.md` do projeto ativo.
Depois de entender a tarefa, consulta a documentação local necessária e o
DevTOLAS somente quando houver norma metodológica aplicável. Skills e scripts
são carregados ou executados apenas quando acionados pela necessidade da tarefa.

Entre as fontes efetivamente aplicáveis, respeitar:

1. segurança e autorização;
2. método comum do DevTOLAS;
3. instruções e decisões do projeto ativo;
4. documentação e código da tarefa atual.

Uma decisão local pode adaptar o método quando o contexto justificar, mas não
deve alterar silenciosamente a fonte comum.

## Normas transversais

- [governanca.md](governanca.md) define autoridade, isolamento e carregamento
  progressivo de contexto;
- [documentacao.md](documentacao.md) define classificação e organização
  documental;
- [uso-de-llm.md](uso-de-llm.md) define o uso eficiente e seguro de LLM em
  qualquer componente do Ecossistema DEV.

## Limites da versão inicial

Nesta fase, o DevTOLAS é uma metodologia documentada, aplicada operacionalmente
principalmente pelo Codex no VS Code. Ainda não é:

- um framework de aplicação;
- uma biblioteca compartilhada em tempo de execução;
- um conjunto de agentes especializados;
- uma plataforma de automação;
- um substituto para julgamento técnico.

Essas capacidades somente serão consideradas quando problemas reais demonstrarem
sua necessidade.
