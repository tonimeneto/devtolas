# Mapa-referência — Ecossistema DEV

> Referência rápida para decidir **onde colocar e onde procurar instruções do Codex**.

## Mapa

| O que é | Local estratégico |
|---|---|
| Preferências universais de interação com o Codex | `C:\Users\anton\.codex\AGENTS.md` |
| Configuração técnica do Codex | `C:\Users\anton\.codex\config.toml` |
| Governança administrativa de `D:\MeusArquivos` | `D:\MeusArquivos\AGENTS.md` |
| Método e regras comuns de desenvolvimento | `D:\MeusArquivos\Fs\Projetos\DevTolas\docs\` |
| Regras para trabalhar no próprio DevTOLAS | `D:\MeusArquivos\Fs\Projetos\DevTolas\AGENTS.md` |
| Regras específicas de um projeto | `D:\MeusArquivos\Fs\Projetos\<Projeto>\AGENTS.md` |
| Conhecimento específico do produto | `D:\MeusArquivos\Fs\Projetos\<Projeto>\docs\` |
| Fonte canônica das skills | `D:\MeusArquivos\Governanca\Codex\skills\<skill>\` |
| Instalação das skills para o Codex | `C:\Users\anton\.agents\skills\<skill>` |
| Procedimento de uma skill | `<skill>\SKILL.md` |
| Automação mecânica de uma skill | `<skill>\scripts\` |
| Histórico, itens antigos e rollback | `D:\MeusArquivos\Governanca\Arquivo\Reserva\` |

## Regra de decisão

```text
Como o Codex deve trabalhar comigo sempre?
→ C:\Users\anton\.codex\AGENTS.md

É configuração do Codex?
→ C:\Users\anton\.codex\config.toml

É administração de D:\MeusArquivos?
→ D:\MeusArquivos\AGENTS.md

Vale para desenvolvimento de qualquer projeto?
→ DevTOLAS\docs

Vale somente para um projeto?
→ Projeto\AGENTS.md

Explica negócio, arquitetura ou funcionamento do produto?
→ Projeto\docs

É um procedimento reutilizável?
→ Governanca\Codex\skills\<skill>\SKILL.md

É execução determinística desse procedimento?
→ Governanca\Codex\skills\<skill>\scripts

Não faz mais parte da estrutura ativa?
→ Governanca\Arquivo\Reserva
```

## Fluxo normal

```text
Codex
  ↓
preferências pessoais
  ↓
AGENTS.md do projeto
  ↓
docs locais, se necessários
  ↓
DevTOLAS, somente se a regra comum for necessária
  ↓
skill, somente se o procedimento for necessário
```

**Princípio:** uma regra deve ter **um local canônico**. Não duplicar regras comuns nos projetos, não colocar regras de produto no DevTOLAS e não deixar cópias antigas em locais ativos.
