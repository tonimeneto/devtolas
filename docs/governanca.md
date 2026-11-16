# Governança do DevTOLAS

## Objetivo

Definir os limites comuns para uso do DevTOLAS pelo Codex e para execução segura
do trabalho de engenharia.

Esta governança orienta o método comum. Cada projeto consumidor deve possuir
instruções locais que definam seu domínio, sua arquitetura, suas fontes oficiais
e seus comandos de validação.

## Contexto ativo

Antes de agir, identificar:

1. projeto ou área ativa;
2. pasta autorizada;
3. objetivo da tarefa;
4. fontes oficiais disponíveis;
5. alterações locais existentes;
6. operações permitidas.

Quando essas informações não forem suficientes, permanecer em leitura e limitar
a investigação ao necessário para esclarecer o escopo.

Uma sessão de desenvolvimento deve operar em um único projeto ativo. A troca de
projeto encerra o contexto anterior e exige um novo contexto.

## Precedência técnica, autoridade e autorização

O DevTOLAS é a autoridade metodológica do Ecossistema DEV. Essa autoridade não
significa que sua documentação seja herdada ou carregada automaticamente pelo
Codex apenas porque o DevTOLAS existe no ecossistema ou em uma raiz do
workspace.

O Codex determina a precedência técnica de suas instruções. No uso local, ele
combina a orientação global com os `AGENTS.md` encontrados da raiz do projeto
até o diretório atual; instruções mais próximas do diretório de trabalho são
mais específicas. A tarefa atual expressa a intenção e a autorização do usuário
dentro dos limites superiores de segurança e da plataforma.

O Ecossistema DEV não redefine essa precedência. Ele define a matéria de cada
fonte e como recuperar evidência. O carregamento operacional é progressivo:

```text
global pessoal do Codex
    → `AGENTS.md` do contexto ou projeto ativo
    → documentação local necessária à tarefa
    → DevTOLAS, quando houver norma metodológica aplicável
    → skill acionada
    → script necessário
```

O `AGENTS.md` de um projeto deve funcionar como roteador de contexto, não como
repositório de todo o conhecimento. O Codex não deve consultar toda a
documentação disponível por padrão.

Cada fonte responde somente por sua matéria:

- a tarefa atual define objetivo, resultado e autoridade concedida;
- o `AGENTS.md` ativo controla comportamento recorrente no seu escopo;
- o DevTOLAS é canônico para o método comum;
- a documentação do projeto é canônica para decisões e conhecimento do produto;
- o estado vigente situa o trabalho atual;
- código, testes, configuração e ambientes fornecem evidência observável;
- skills conduzem procedimentos e scripts garantem operações determinísticas.

Uma tarefa pode substituir legitimamente uma decisão ou orientação que esteja
dentro da autoridade do usuário, desde que a mudança seja explícita, atualize a
fonte canônica e registre o que foi substituído. Segurança, privacidade,
políticas da plataforma e limites de autoridade não podem ser reduzidos por
inferência.

Resultado necessário não equivale a autoridade genérica para qualquer ação. Se
o resultado depender de operação destrutiva, externa, em produção ou fora do
escopo concedido, apresentar o impedimento ou obter autorização compatível.

Conflitos entre documentação e comportamento observado devem ser comunicados e
resolvidos de forma explícita. Não corrigir silenciosamente uma fonte com base
em outra.

## Isolamento entre projetos

- Consultar somente o projeto ativo e referências comuns autorizadas.
- Não pesquisar outros projetos para encontrar exemplos sem autorização.
- Não transferir código, arquitetura, regras, prompts ou decisões entre projetos
  por semelhança.
- Não presumir que uma tecnologia adotada em um projeto seja padrão universal.
- Manter regras de negócio e documentação específica no projeto de origem.
- Identificar claramente qualquer aprendizado proposto para a base comum.

O workspace reduz exposição acidental, mas não constitui uma barreira absoluta
de segurança.

## Conhecimento comum e específico

Pode ser candidato ao DevTOLAS:

- método de análise, planejamento e validação;
- práticas gerais de segurança, testes e documentação;
- templates neutros;
- padrões arquiteturais com contexto e limites explícitos;
- aprendizados reutilizáveis sem dependência de domínio.

Deve permanecer no projeto:

- requisitos e regras de negócio;
- arquitetura e tecnologias escolhidas;
- código, banco, infraestrutura e configurações;
- identidade visual;
- dados operacionais;
- credenciais e identificadores;
- decisões que dependam do contexto local.

## Classificação do contexto

A taxonomia, o destino conceitual de cada tipo de informação e a regra de fonte
normativa única pertencem exclusivamente a
[documentacao.md](documentacao.md). Esta governança apenas exige que a
classificação seja aplicada antes de criar ou mover artefatos.

Workspaces de projetos usam uma única raiz, a do projeto ativo, conforme
[criacao-de-projetos.md](criacao-de-projetos.md). Componentes que utilizam
modelos de linguagem seguem [uso-de-llm.md](uso-de-llm.md).

## Segurança e privacidade

- Nunca exibir senhas, tokens, chaves, certificados ou conteúdo equivalente.
- Não abrir arquivos de ambiente sem necessidade e autorização compatíveis.
- Não incluir segredos em prompts, relatórios, documentação, commits ou logs.
- Tratar dados pessoais, médicos, financeiros, jurídicos e empresariais como
  sensíveis.
- Ler conteúdo sensível somente quando indispensável e sem reproduzi-lo
  desnecessariamente.
- Sanitizar remotos Git, caminhos, variáveis e metadados antes de compartilhar
  resultados.

Ocultar arquivos no VS Code ou excluí-los de pesquisas reduz exposição
acidental, mas não substitui controle de acesso.

## Operações proporcionais ao risco

Operações de leitura e diagnóstico podem avançar quando estiverem dentro do
escopo autorizado.

Mudanças normais de implementação podem ser executadas quando forem necessárias
para atingir o objetivo solicitado e estiverem limitadas ao projeto ativo.

Operações externas, destrutivas ou que ampliem materialmente o escopo exigem
autorização compatível. Entre elas:

- mover ou excluir dados relevantes;
- sobrescrever conteúdo existente;
- alterar configurações globais;
- modificar áreas compartilhadas;
- publicar ou enviar dados;
- alterar remotos ou executar operações Git não abrangidas pela tarefa.

## Fluxo para operações controladas

Quando uma operação puder afetar estrutura, histórico ou dados:

```text
diagnosticar
    ↓
propor
    ↓
autorizar
    ↓
executar
    ↓
validar
    ↓
registrar
```

### Diagnosticar

Resolver os alvos, o estado atual, dependências e riscos sem modificar conteúdo.

### Propor

Descrever a menor mudança capaz de atingir o objetivo, incluindo preservações e
validação.

### Autorizar

Obter autorização quando a ação for destrutiva, externa, compartilhada ou
materialmente mais ampla que a solicitação.

### Executar

Trabalhar em lotes pequenos, com alvos explícitos, preservando conteúdo não
relacionado.

### Validar

Confirmar o resultado, a integridade das referências e a ausência de efeitos
indevidos.

### Registrar

Informar o que mudou, o que foi preservado, quais verificações foram executadas
e o que permaneceu pendente.

## Git

Antes de alterar um projeto Git, confirmar:

- raiz do repositório;
- branch atual;
- remoto sanitizado;
- alterações locais;
- instruções específicas do projeto.

Preservar alterações existentes e não incluir arquivos alheios ao escopo em
commits.

Commits, pushes, merges, criação de PRs, troca de branch, inicialização de
repositório e alteração de remotos dependem de autorização compatível com a
tarefa.

Não alterar configuração global do Git para contornar um problema local quando
uma solução restrita ao comando ou ao repositório for suficiente.

## Área compartilhada

O DevTOLAS é a fonte do método de engenharia. Projetos consumidores devem
consultá-lo como referência e não modificá-lo durante tarefas normais do
projeto.

Uma melhoria comum deve ser proposta e tratada no próprio repositório DevTOLAS,
com justificativa e estado conforme `docs/evolucao-do-conhecimento.md`.
Registros administrativos, como aliases do ecossistema, pertencem à Governança
e não criam exceção de escrita neste repositório.

## Critérios de conclusão

Antes de encerrar uma mudança, confirmar conforme o risco:

- escopo atendido;
- validações relevantes executadas;
- documentação avaliada;
- alterações não relacionadas preservadas;
- ausência de segredos na saída e no Git;
- isolamento entre projetos mantido;
- estado final e pendências comunicados.

Quando a mudança substituir responsabilidade existente, confirmar também que a
implementação anterior e seus consumidores foram identificados e que código,
testes, referências e documentação foram reconciliados. Coexistência deve ser
intencional e justificada.
