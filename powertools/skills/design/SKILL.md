---
name: design
description: Use quando o usuário solicitar criação de componentes web, páginas, landing pages, dashboards, layouts HTML/CSS, componentes React/Vue, pôsteres ou estilização de interfaces. Acionado por pedidos como "cria uma página", "faz um componente", "estiliza isso", "faz um layout".
model: opus
---

# UI/UX Design Distinto

## Overview

Técnica para criar interfaces de nível profissional com identidade visual própria. O princípio central: cada design deve ter um **ponto de vista estético claro e intencional** — nunca convergir para padrões genéricos de IA.

## Quando Usar

- O usuário solicita criação de componentes, páginas, aplicativos ou interfaces web
- O usuário pede para estilizar, embelezar ou redesenhar uma interface existente

**Quando NÃO usar:** alterações puramente funcionais sem impacto visual

## Contexto

Antes de codificar, execute o Design Thinking:

1. **Propósito**: Qual problema esta interface resolve? Quem a utiliza?
2. **Tom estético**: Escolha uma direção **ousada e específica** — não "bonito" ou "moderno". Exemplos: brutalmente minimalista, caos maximalista, retrô-futurista, orgânico/natural, luxuoso/refinado, lúdico/brinquedo, editorial/revista, brutalista/cru, art déco/geométrico, suave/pastel, industrial/utilitário.
3. **Diferenciação**: Defina a única coisa que alguém vai lembrar deste design.

## Padrão Central

### Tipografia

Escolha fontes **distintas e com personalidade** via Google Fonts ou CDN. Combine uma fonte de display ousada com uma fonte de corpo refinada.

**LISTA NEGRA — NUNCA use estas fontes:**
- Inter, Roboto, Arial, Helvetica, Open Sans, Lato, Montserrat
- Segoe UI, system-ui, -apple-system, sans-serif (fontes do sistema)
- Space Grotesk (convergência comum de IA)

A lista abaixo é apenas inspiração — **NÃO trate como fontes padrão**. Escolha combinações diferentes a cada design. Nunca repita o mesmo par de fontes em designs consecutivos:

Serifadas: Playfair Display, Instrument Serif, DM Serif Display, Fraunces, Gambetta, Cormorant, Libre Baskerville, Crimson Pro, Lora, Bodoni Moda.

Sans-serif: Syne, Cabinet Grotesk, Clash Display, Satoshi, General Sans, Outfit, Plus Jakarta Sans, Bricolage Grotesque, Bebas Neue, Archivo Black, Lexend, Manrope, Urbanist, Onest, Geist.

Monospace/Display: JetBrains Mono, Space Mono, Chakra Petch, Orbitron.

### Cor e Paleta

Paleta **coesa e intencional** com cores dominantes e acentos nítidos. Use variáveis CSS no `:root`.

**LISTA NEGRA:**
- Gradientes roxos (`#6366f1`, `#8b5cf6`) em fundos escuros — clichê nº 1 de IA
- Indigo/violet como acento padrão
- Paletas uniformemente distribuídas sem hierarquia

### Layout e Composição

Quebre a previsibilidade. Explore: assimetria, sobreposição, fluxo diagonal, quebra de grade, espaço negativo generoso OU densidade controlada, grids não-convencionais.

### Movimento e Animação

Priorize CSS puro para HTML. Motion para React. Foque em **momentos de alto impacto**: revelações escalonadas (`animation-delay`), hover surpreendentes, scroll encantadores.

### Fundos e Texturas

Crie **atmosfera e profundidade** — nunca cores sólidas chapadas. Aplique: malhas de gradiente, texturas de ruído/grão, padrões geométricos, transparências em camadas, sombras dramáticas, sobreposições de grão.

## Regras de Divergência

Cada design gerado DEVE ser esteticamente **diferente do anterior**. Se o último design foi escuro e minimalista, o próximo deve ser claro e expressivo, ou retrô, ou brutalista.

**Checklist de divergência obrigatório — varie TODOS estes eixos:**

1. **Tema de luminosidade**: Alternar entre claro, escuro e colorido. Não faça tema escuro em sequência.
2. **Par de fontes**: Usar combinação diferente do último design. Se usou Syne+Fraunces, agora use Clash Display+Crimson Pro.
3. **Paleta de temperatura**: Alternar quentes (âmbar, coral, terracota) e frios (sage, teal, lavanda).
4. **Direção estética**: Nunca repetir o mesmo tom (se fez art déco, faça brutalista ou editorial).
5. **Composição**: Se o anterior foi simétrico, use assimetria. Se foi espaçado, use densidade.

## Adequação de Complexidade

- **Maximalista**: Animações complexas, múltiplas camadas, efeitos visuais ricos
- **Minimalista**: Contenção extrema, precisão milimétrica, detalhes sutis

## Regras do Projeto

- Respeite temas CSS existentes no projeto — não altere sem solicitação
- Mantenha coerência com outros componentes existentes

## Referência Rápida

| Aspecto | Genérico (EVITAR) | Distinto (BUSCAR) |
|---------|-------------------|-------------------|
| Fontes | Inter, Roboto, system-ui | Par único por design — nunca repetir |
| Cor de acento | `#6366f1` indigo/roxo | Paleta contextual e intencional |
| Fundo | `#0f1117` sólido | Gradientes, texturas, grão, camadas |
| Layout | Hero centralizado → grid 3 cols | Assimetria, sobreposição, quebra de grade |
| Animação | Nenhuma ou hover básico | Revelações escalonadas, scroll, micro-interações |
| Personalidade | Template intercambiável | Ponto de vista estético memorável |

## Erros Comuns

| Erro | Correção |
|------|----------|
| Usar fontes do sistema ou genéricas | Sempre importar fontes distintas via Google Fonts/CDN |
| Acento roxo/indigo por padrão | Escolher paleta contextual que reflita o propósito |
| Mesmo tema escuro em tudo | Variar entre claro, escuro, colorido, misto |
| Layout de template SaaS | Questionar cada decisão de layout — "isso é previsível?" |
| Fundos de cor sólida | Adicionar profundidade com gradientes, texturas, sobreposições |
| Zero animações | Incluir pelo menos revelações de entrada e hover states |
| Design sem identidade | Antes de codificar, definir o tom estético e o diferencial |
| Copiar o design anterior | Verificar e divergir do último design gerado |
| Usar emoji como ícones | Criar SVGs inline ou usar uma biblioteca de ícones |
| Repetir o mesmo par de fontes | Consultar checklist de divergência — cada design exige combinação nova |
| Tema escuro em todos os designs | Forçar alternância: se o anterior era escuro, o próximo deve ser claro ou colorido |