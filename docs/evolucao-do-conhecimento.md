# Evolução do conhecimento

O DevTOLAS deve preservar conhecimento útil sem transformar opiniões em regras
permanentes.

Propostas podem surgir da experiência em projetos, de auditorias, incidentes,
mudanças externas, pesquisa técnica ou riscos identificados. A origem de uma
ideia não basta para torná-la orientação comum: sua incorporação deve possuir
justificativa e evidência proporcionais ao alcance e ao risco.

## Estados

- `hipótese`: ideia ainda não avaliada na prática;
- `experimental`: orientação em avaliação controlada;
- `provisório`: conhecimento útil, mas ainda sujeito a confirmação;
- `validado`: prática sustentada por uso ou evidência suficiente;
- `depreciado`: orientação ainda registrada, mas não recomendada;
- `rejeitado`: proposta avaliada e considerada inadequada.

## Critérios para incorporação

Antes de incorporar um aprendizado à base comum, confirmar:

1. ele é independente de regras de negócio;
2. ele pode beneficiar mais de um projeto;
3. sua justificativa está registrada;
4. seu estado está explícito;
5. ele não cria complexidade desnecessária;
6. ele não expõe dados, código ou decisões específicas do projeto de origem.

Uma hipótese pode ser registrada antes da validação prática, desde que seu estado
seja explícito e ela não seja apresentada como regra consolidada. Quanto mais
universal for a orientação proposta, maior deve ser a evidência de que ela é
reutilizável em contextos diferentes.

## Processo mínimo

1. registrar a proposta e sua origem;
2. classificar o estado;
3. avaliar aplicabilidade e riscos;
4. incorporar, manter em avaliação ou rejeitar;
5. registrar mudanças relevantes no `CHANGELOG.md`.

## Revisão

Conhecimento validado também pode ser revisto. Quando uma orientação mudar,
registrar o motivo e preservar o histórico necessário para compreender a
decisão.
