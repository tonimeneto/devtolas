# Transição concluída

## Resultado

Em 26/07/2026, o DevTOLAS tornou-se a única fonte ativa do método de engenharia
para os workspaces de desenvolvimento existentes.

## Base incorporada

- governança de contexto, segurança e operações;
- método de desenvolvimento;
- evolução do conhecimento;
- continuidade entre sessões;
- criação de projetos;
- template de `AGENTS.md`;
- template de workspace;
- classificação do conhecimento do GPTOLAS;
- classificação dos materiais de `Fs\Comum`.

## Workspaces

Foram migrados:

- Ask2Trade;
- BrainDrive;
- Find2Go;
- Find2GoLocal;
- KaraokeySync;
- Lovegol;
- PDFLivre;
- SmartTrade;
- WheresIt.

Também foi criado `DevTOLAS.code-workspace`.

Cada workspace consumidor contém:

1. o projeto específico;
2. o DevTOLAS como referência de método.

Todos os arquivos foram validados como JSON, todos os caminhos resolvem para
diretórios existentes e nenhum workspace mantém `Fs\Comum` como raiz.

## Instruções dos projetos

Os `AGENTS.md` existentes tiveram somente suas referências metodológicas
adaptadas. Regras e decisões locais foram preservadas. Um `AGENTS.md` inicial
foi criado para Ask2Trade a partir do template oficial, mantendo decisões
desconhecidas como pendentes.

Essas alterações permanecem nos respectivos projetos e não foram commitadas pelo
DevTOLAS, para evitar mistura de históricos Git.

## Fontes anteriores

Foram retirados do contexto ativo:

- políticas comuns para agentes;
- guia de contexto e isolamento;
- templates antigos de projeto e workspace;
- procedimento antigo de criação de projetos;
- diretório GPTOLAS.

Os originais foram preservados em:

```text
D:\MeusArquivos\30 - Fs\Arquivo\Metodologia\
Transicao-DevTOLAS-2026-07-26
```

Essa área também contém cópias dos workspaces e `AGENTS.md` anteriores à
migração.

## Fs\Comum

`Fs\Comum` continua disponível para recursos compartilhados que não representam
o método. Suas áreas antigas de IA, metodologia e templates possuem avisos
indicando o DevTOLAS como fonte oficial.

## Validação final

- dez workspaces válidos;
- zero caminhos ausentes;
- zero workspaces apontando para `Fs\Comum`;
- todos os projetos com `AGENTS.md`;
- zero `AGENTS.md` apontando para as políticas antigas;
- GPTOLAS ausente da área ativa;
- GPTOLAS presente no arquivo histórico;
- código e documentação de negócio dos projetos não consultados nem alterados.
