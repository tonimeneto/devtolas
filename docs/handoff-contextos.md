# Handoff entre Contextos e Projetos

## 1. Objetivo

O Handoff é o mecanismo oficial de transferência explícita de contexto entre conversas, projetos, áreas de governança ou novos ambientes de trabalho do Ecossistema DEV.

Seu objetivo é preservar decisões, contexto e continuidade quando uma informação relevante precisa atravessar uma fronteira de contexto.

O Handoff não substitui a documentação do projeto.

Ele atua como uma ponte controlada entre dois contextos.

---

## 2. Princípio

A memória de uma ferramenta de IA pode auxiliar na continuidade, mas não deve ser considerada mecanismo determinístico de transferência de contexto.

Portanto:

**Memória da IA = conveniência.**

**Handoff = transferência explícita de contexto.**

Informações importantes não devem depender exclusivamente da capacidade de uma ferramenta recuperar espontaneamente conversas anteriores.

---

## 3. Quando utilizar

Um Handoff deve ser considerado quando uma informação relevante precisar sair do contexto onde foi produzida e continuar válida em outro contexto.

Exemplos:

- uma ideia nasce dentro de um projeto e passa a ter natureza transversal;
- uma discussão de Governança origina um novo projeto;
- um projeto novo precisa receber decisões tomadas antes de sua criação;
- uma conversa precisa continuar em outro Projeto do ChatGPT;
- uma investigação realizada em um contexto precisa ser entregue para execução em outro;
- um assunto inicialmente pertencente a um projeto passa a possuir responsabilidade própria;
- decisões importantes precisam sobreviver à troca de ferramenta, sessão ou ambiente;
- a recuperação automática de contexto pela ferramenta não é suficientemente confiável.

---

## 4. Quando não utilizar

Não criar Handoff apenas por rotina.

Um Handoff normalmente não é necessário quando:

- a conversa continua no mesmo contexto;
- a informação já está adequadamente registrada na documentação vigente;
- nenhuma fronteira entre projetos ou responsabilidades foi atravessada;
- o conteúdo é temporário e não possui valor de continuidade;
- a transferência pode ser feita por referência direta a uma fonte canônica já existente.

O objetivo não é aumentar documentação.

O objetivo é evitar perda ou distorção de contexto relevante.

---

## 5. Momento de criação

O Handoff deve preferencialmente ser produzido no contexto de origem.

Isso ocorre porque o contexto de origem possui maior probabilidade de conter:

- motivação;
- problema inicial;
- decisões;
- alternativas consideradas;
- limites;
- dúvidas ainda abertas;
- sequência da discussão;
- significado das decisões tomadas.

Sempre que possível:

**quem possui o contexto produz o Handoff.**

---

## 6. Tipos de Handoff

### 6.1 Handoff para Governança

Utilizado quando uma questão surgida em um projeto precisa ser analisada em nível transversal.

Exemplo:

Projeto A
→ surge necessidade transversal
→ Handoff Governança
→ Governança

Governança pode então decidir se aquilo deve permanecer como:

- responsabilidade do projeto original;
- conhecimento compartilhado;
- regra metodológica;
- skill;
- ferramenta comum;
- serviço compartilhado;
- novo projeto;
- outra estrutura apropriada.

### 6.2 Handoff para novo projeto

Utilizado quando a decisão de criar um projeto independente já foi tomada.

Exemplo:

Projeto de origem / Governança
→ decisão de criar Projeto B
→ Handoff Projeto B
→ criação do Projeto B
→ novo contexto de trabalho

O Handoff passa a fornecer o contexto inicial necessário para que o novo projeto não precise reconstruir sua origem por inferência.

### 6.3 Handoff entre projetos existentes

Pode ser utilizado quando um projeto precisa entregar informação relevante para outro sem transportar indevidamente seu domínio.

Exemplo:

Projeto A
→ produz contrato / decisão / necessidade
→ Handoff
→ Projeto B

O Handoff deve transportar somente aquilo que o projeto de destino realmente precisa conhecer.

Não deve copiar indiscriminadamente todo o contexto do projeto de origem.

---

## 7. Conteúdo mínimo

Um Handoff deve conter somente o contexto necessário para continuidade segura.

Quando aplicável, deve registrar:

1. **Origem**
   - onde a discussão começou;
   - qual projeto ou contexto a originou.

2. **Problema ou motivação**
   - o que levou à discussão.

3. **Objetivo**
   - o que se pretende alcançar.

4. **Decisões já tomadas**
   - somente decisões efetivamente estabelecidas.

5. **Motivos relevantes**
   - por que determinadas decisões foram tomadas, quando necessário para compreendê-las.

6. **Limites**
   - o que ficou explicitamente fora do escopo;
   - o que não deve ser assumido.

7. **Estado atual**
   - o que existe;
   - o que ainda não existe;
   - o que já foi validado.

8. **Pendências**
   - questões ainda abertas.

9. **Responsabilidade do contexto de destino**
   - o que se espera que o próximo projeto, área ou conversa faça.

10. **Fontes relevantes**
    - documentos, arquivos, contratos, repositórios ou outras evidências necessárias para continuidade.

Nem todos os itens precisam existir em todos os Handoffs.

O conteúdo deve ser proporcional ao risco e à complexidade da transferência.

---

## 8. Regra de fidelidade

O Handoff deve separar claramente:

- decisão tomada;
- fato comprovado;
- hipótese;
- proposta;
- pendência;
- inferência.

Não transformar hipótese em decisão.

Não transformar intenção futura em funcionalidade existente.

Não completar lacunas por conta própria.

Não reescrever a história para torná-la mais coerente.

Quando uma informação importante não puder ser confirmada, registrar explicitamente:

**não confirmado**

ou

**a decidir**.

---

## 9. Regra de escopo

O Handoff deve transportar o mínimo contexto suficiente.

Evitar:

- copiar conversas completas;
- transportar histórico irrelevante;
- incluir detalhes de outros projetos sem necessidade;
- reproduzir código, arquitetura ou regras de negócio apenas por semelhança;
- criar dependência desnecessária entre projetos.

O princípio é:

**transferir contexto sem transferir acoplamento.**

---

## 10. Relação com documentação canônica

O Handoff não se torna automaticamente fonte permanente de verdade.

Após a transferência:

- decisões duradouras devem ser incorporadas à documentação apropriada do projeto ou do DevTOLAS;
- regras metodológicas devem ser formalizadas na fonte metodológica correspondente;
- contratos devem ser registrados onde pertencem;
- informações temporárias podem permanecer apenas no Handoff quando não justificarem documentação permanente.

Quando existir conflito entre:

- Handoff antigo;
- documentação vigente;
- código atual;
- contrato atual;
- decisão posterior registrada;

deve prevalecer a fonte vigente e autoritativa correspondente.

O Handoff representa o estado conhecido no momento da transferência.

---

## 11. Relação com memória da IA

A existência de memória entre conversas ou projetos não elimina a necessidade de Handoff.

A memória pode:

- facilitar retomadas;
- recuperar referências;
- reduzir repetição;
- ajudar na continuidade informal.

Mas ela não deve ser utilizada como única evidência de decisões críticas.

A recuperação automática pode ser:

- incompleta;
- resumida;
- seletiva;
- indisponível;
- diferente entre ferramentas ou sessões.

Portanto:

**Memória ajuda.**

**Handoff transfere explicitamente.**

---

## 12. Relação com o DevTOLAS

O Handoff é um mecanismo de governança e continuidade do DevTOLAS.

Ele deve preservar os princípios de:

- isolamento entre projetos;
- autoridade explícita;
- rastreabilidade;
- documentação proporcional ao risco;
- contexto mínimo necessário;
- separação entre conhecimento comum e domínio específico;
- ausência de decisões silenciosas;
- continuidade independente de uma conversa específica.

---

## 13. Fluxo recomendado para ideias transversais

Quando uma ideia surgir dentro de um projeto:

Ideia nasce no Projeto A
→ análise inicial
→ continua pertencendo somente ao Projeto A?

Se SIM:
→ permanece no Projeto A.

Se NÃO:
→ questão transversal
→ já está claro onde ela pertence?

Se NÃO:
→ Handoff Governança
→ Governança classifica a responsabilidade.

Se SIM:
→ Handoff direto para o contexto de destino.

Se Governança decidir criar novo projeto:

Governança
→ decisão de criar projeto
→ Handoff do novo projeto
→ criar-projeto
→ workspace isolado
→ novo Projeto do ChatGPT / nova sessão
→ continuidade dentro do novo contexto.

---

## 14. Handoff não é autorização de execução

Receber um Handoff não significa autorização automática para modificar código, infraestrutura, dados, documentação ou outros projetos.

O Handoff transfere contexto.

A execução continua sujeita às regras normais de:

Diagnosticar
→ Propor
→ Autorizar
→ Executar
→ Validar
→ Registrar

quando essas etapas forem aplicáveis.

---

## 15. Nomeação recomendada

Quando armazenado como arquivo, utilizar nome que identifique claramente origem ou destino.

Exemplos:

- `handoff-radaria.md`
- `handoff-governanca-radaria.md`
- `handoff-pro2go-radaria.md`
- `handoff-markethub-smarttrade.md`

Quando utilizado diretamente em uma conversa, pode ser identificado por comando conceitual:

`Handoff Governança`

ou:

`Handoff <NomeDoProjeto>`

Exemplos:

- `Handoff RadarIA`
- `Handoff MarketHub`
- `Handoff Sia2Fa`

---

## 16. Regra final

Uma conversa pode originar conhecimento.

Uma memória pode ajudar a recuperá-lo.

Mas uma decisão que precisa atravessar uma fronteira deve possuir uma transferência explícita quando sua preservação for importante.

O princípio do Ecossistema DEV é:

> **Contexto importante não deve depender de lembrança implícita quando pode ser transferido de forma explícita, mínima e rastreável.**