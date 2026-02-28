<div align="center">

<p>
  <img src="https://raw.githubusercontent.com/lucasprmartins/beta/main/apps/web/public/logo-1.svg" alt="Beta" height="70" align="center" />
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/plugins-7c3aed?style=for-the-badge" alt="Plugins" height="28" align="center" />
</p>

[![GitHub](https://img.shields.io/badge/Template-Beta-7c3aed?logo=github)](https://github.com/lucasprmartins/beta)

<sub>Feito para <img src="https://cdn.simpleicons.org/claude/d97757" alt="Claude" height="12" /> Claude Code · adaptável para outros agentes</sub>

</div>

---

## Sobre

Plugins para [Claude Code](https://github.com/anthropics/claude-code) que oferece um pipeline completo de desenvolvimento — da ideação à revisão de código — através de skills orquestradas e subagentes especializados.

## Plugins

### Workflow

Pipeline completo de desenvolvimento com orquestração de subagentes.

| Skill | Descrição |
|-------|-----------|
| `/spec` | Transforma ideias vagas em especificações detalhadas |
| `/roadmap` | Converte especificações em tarefas atômicas e executáveis |
| `/build` | Orquestra subagentes `maker` para execução paralela por fases |
| `/check` | Orquestra subagentes `reviewer` e `fixer` em loop de verificação |

**Subagentes:**

| Agente | Função |
|--------|--------|
| `maker` | Implementa tarefas individuais com commits atômicos |
| `reviewer` | Executa verificações técnicas e revisão de código |
| `fixer` | Aplica correções cirúrgicas nos problemas encontrados |

### Essentials

Utilitários de produtividade para o dia a dia.

| Skill | Descrição |
|-------|-----------|
| `/commit` | Commits atômicos seguindo Conventional Commits |
| `/design` | Criação de interfaces UI/UX profissionais e distintas |
| `/pr` | Pull requests padronizados com checklist de verificação |

**MCP Server:** [Context7](https://mcp.context7.com) — consulta de documentação em tempo real.

## Instalação

Adicione o marketplace e instale os plugins desejados:

```bash
# 1. Registrar o repositório como marketplace
/plugin marketplace add lucasprmartins/beta-plugins

# 2. Instalar plugins
/plugin install workflow@beta-plugins
/plugin install essentials@beta-plugins
```

