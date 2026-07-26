# Sistema de desenvolvimento DevTOLAS

## Objetivo

O DevTOLAS é o sistema comum de desenvolvimento utilizado para conduzir projetos
de software com um método consistente, documentado e evolutivo.

Ele é o cérebro de engenharia: organiza como o trabalho é analisado, planejado,
implementado, validado, documentado e aprimorado. Ele não executa o papel do
sistema desenvolvido e não substitui suas decisões específicas.

## Fonte da verdade

O DevTOLAS é a fonte oficial do método de engenharia.

Projetos consumidores podem adaptar a aplicação do método ao próprio contexto,
mas não devem manter cópias independentes das orientações comuns. Melhorias
reutilizáveis devem retornar ao DevTOLAS para beneficiar os projetos atuais e
futuros.

## Camadas

### 1. Método comum

Pertence ao DevTOLAS:

- princípios de engenharia;
- fluxo de desenvolvimento;
- padrões de análise, implementação, testes, revisão e auditoria;
- governança da documentação e do conhecimento;
- templates e skills reutilizáveis;
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
Experiência em um projeto
          ↓
Identificação de aprendizado reutilizável
          ↓
Avaliação e classificação
          ↓
Incorporação ao DevTOLAS
          ↓
Aplicação nos projetos consumidores
```

Conhecimento específico permanece no projeto de origem.

## Precedência no projeto consumidor

Ao desenvolver um sistema, aplicar:

1. segurança e autorização;
2. método comum do DevTOLAS;
3. instruções e decisões do projeto ativo;
4. documentação e código da tarefa atual.

Uma decisão local pode adaptar o método quando o contexto justificar, mas não
deve alterar silenciosamente a fonte comum.

## Limites da versão inicial

Nesta fase, o DevTOLAS é uma base documental e operacional para o Codex no
VS Code. Ainda não é:

- um framework de aplicação;
- uma biblioteca compartilhada em tempo de execução;
- um conjunto de agentes especializados;
- uma plataforma de automação;
- um substituto para julgamento técnico.

Essas capacidades somente serão consideradas quando problemas reais demonstrarem
sua necessidade.
