<p align="center">
  <img src="icon.svg" width="160" alt="Website builder — janela de browser com uma página a ser desenhada por um lápis">
</p>

<h1 align="center">Website builder — Claude Skill</h1>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
  <img src="https://img.shields.io/badge/Claude-Skill-D97757" alt="Claude Skill">
</p>

<p align="center">
📚 Faz parte da <b><a href="https://github.com/mozuraa/claude-skills">biblioteca de skills de mozuraa</a></b> · Part of <b><a href="https://github.com/mozuraa/claude-skills">mozuraa's skills library</a></b>
</p>

<p align="center"><b><a href="#português">Português</a> · <a href="#english">English</a></b></p>

---

## Português

Uma [skill](#o-que-é-uma-skill) para o **Claude** que **cria websites completos de raiz, contigo**. Faz as perguntas certas, propõe o plano com a sua opinião honesta e constrói o site página a página. Pelo caminho mostra-te capturas, verifica tudo antes de publicar e ajuda-te a pô-lo online com domínio e email. Traz ainda um **site-base pronto**, com boas práticas de acessibilidade, velocidade, segurança e privacidade já feitas.

### Como trabalha

```
1. Briefing ─► 2. Plano ─► ✋ aprovas ─► 3. Identidade visual ─► 4. Página inicial ─► ✋ aprovas
   ─► 5. Resto do site ─► 6. Verificação ─► ✋ aprovas ─► 7. Lançamento e entrega
```

| Fase | O que acontece |
|---|---|
| 🗣️ **Briefing** | Faz-te até 5 perguntas essenciais (para que é o site, o que deve o visitante fazer, para quem é, que conteúdo já tens, que estilo procuras) e depois as específicas do teu tipo de site. |
| 🗺️ **Plano** | Propõe o mapa do site, a tecnologia e o alojamento (com custos), a direção visual, as funcionalidades e a privacidade, e diz-te a sua opinião sincera. **Só avança com a tua aprovação.** |
| 🎨 **Identidade visual** | Cria um sistema de design a partir da tua marca (cores com contraste verificado, tipografia, espaçamentos), para o site não parecer um modelo genérico. |
| 🏠 **Página inicial** | Constrói primeiro a página inicial completa e mostra-te capturas em telemóvel e computador. **Ajustas antes de ele fazer o resto.** |
| 🧱 **Resto do site** | Faz as outras páginas, a página 404, as páginas legais (privacidade, livro de reclamações...), o SEO, o favicon e a imagem de partilha. |
| ✅ **Verificação** | Testa em 3 tamanhos de ecrã, a consola, os links, o formulário, o Lighthouse (objetivo ≥ 90), as imagens, a acessibilidade, a privacidade e o texto esquecido. **Pede-te autorização para publicar.** |
| 🚀 **Lançamento** | Publica (GitHub Pages, Netlify, Cloudflare, Vercel), liga o domínio, configura o email (SPF/DKIM/DMARC) e o Google Search Console, testa o site real e deixa-te um guia `COMO-EDITAR.md`. |

### Guias incluídos

| Guia | Conteúdo |
|---|---|
| [`briefing.md`](references/briefing.md) | Perguntas e secções obrigatórias para 11 tipos de site: negócio local, restaurante, landing page de app, portfolio, loja, evento, blog, CV, associação, alojamento local, saúde e profissionais liberais |
| [`stack.md`](references/stack.md) | HTML, Astro, Next.js, WordPress, construtores ou Shopify: quando usar cada um. Alojamento, formulários, CMS, estatísticas sem cookies e custos |
| [`design.md`](references/design.md) | Da marca ao estilo, tokens, tipografia fluida, cor e contraste, grelha, componentes, imagens responsivas, movimento, modo escuro e como evitar o aspeto genérico |
| [`paginas.md`](references/paginas.md) | O que cada página deve ter, como escrever para a web, páginas legais na UE e em Portugal (com modelo de política de privacidade) e metadados |
| [`qualidade.md`](references/qualidade.md) | Orçamento de desempenho e a lista de verificação completa antes e depois de publicar |
| [`lancamento.md`](references/lancamento.md) | Publicar passo a passo, domínio e DNS, email, Search Console, verificação final e guia de manutenção |

### Site-base incluído

[`assets/starter/`](assets/starter/) é um site estático pronto a adaptar, testado em telemóvel, computador e modo escuro:

- HTML semântico e **acessível**: link "Saltar para o conteúdo", menu móvel com teclado e Esc, foco visível, etiquetas nos campos.
- CSS com **design tokens**, tipografia fluida, grelhas que se adaptam sem *media queries*, **modo escuro** e respeito por "reduzir movimento".
- **SEO e partilha**: título, descrição, canonical, Open Graph, dados estruturados, `sitemap.xml`, `robots.txt` e manifest.
- **Segurança**: cabeçalhos (CSP, HSTS, `nosniff`, Referrer e Permissions Policy) para Netlify/Cloudflare (`_headers`) e Vercel (`vercel.json`).
- **Privacidade**: zero rastreadores, fontes do sistema (sem Google Fonts) e formulário com proteção anti-spam.
- Página **404** e modelo de **política de privacidade**.
- Cerca de 1 KB de JavaScript, sem dependências.

Os sítios a personalizar estão marcados com `TODO:` e `[entre parênteses retos]`.

### Exemplos de pedidos

- "Quero fazer um site para a minha padaria"
- "Preciso de uma landing page para a minha app"
- "Faz-me um portfolio de fotografia"
- "Quero refazer o site do restaurante do zero"
- "Como é que eu tenho um site para o meu negócio?"

Vê um exemplo de briefing e plano em [`examples/exemplo.md`](examples/exemplo.md).

### Princípios

Telemóvel primeiro · Rápido por defeito · Privado por defeito (sem rastreadores, sem banner) · Acessível desde o início (WCAG 2.2 AA) · Seguro por defeito · Conteúdo real, nunca inventado · A tecnologia mais simples que resolve · Opinião honesta, decisão tua.

### Funciona bem com

- [`website-doctor`](https://github.com/mozuraa/claude-skill-website-doctor): para um exame completo antes de publicar (150+ verificações) e para cuidar do site depois.
- [`code-for-noobs`](https://github.com/mozuraa/claude-skill-code-for-noobs): se quiseres perceber o que está a ser feito.

### Instalação

**Claude Code (para todos os teus projetos)**

```bash
git clone https://github.com/mozuraa/claude-skill-website-builder.git ~/.claude/skills/website-builder
```

**Ou com toda a biblioteca, como plugin** (categoria Criação):

```
/plugin marketplace add mozuraa/claude-skills
/plugin install criacao@mozuraa-skills
```

**App Claude / claude.ai:** carrega em **Code → Download ZIP** e carrega o ZIP nas **Definições**, na secção **Skills** (em *Capacidades*).

Abre uma sessão nova para a skill ser carregada. Para atualizar: `cd ~/.claude/skills/website-builder && git pull`.

### O que é uma skill?

Uma skill é uma pasta com um ficheiro `SKILL.md`: um nome, uma descrição de quando deve ser usada e instruções. O Claude lê só a descrição até ela ser útil; quando o pedido encaixa, carrega as instruções e segue-as.

### Estrutura

```
claude-skill-website-builder/
├── SKILL.md                  # a skill: as 7 fases e os 3 momentos de aprovação
├── references/
│   ├── briefing.md           # perguntas por tipo de site
│   ├── stack.md              # tecnologia, alojamento, serviços, custos
│   ├── design.md             # sistema de design e componentes
│   ├── paginas.md            # conteúdo das páginas e páginas legais
│   ├── qualidade.md          # verificação antes e depois de publicar
│   └── lancamento.md         # publicar, domínio, email, manutenção
├── assets/starter/           # site-base pronto a adaptar
├── examples/exemplo.md
├── icon.svg
├── README.md
├── CHANGELOG.md
└── LICENSE
```

### Contribuir

Falta algum tipo de site, um serviço mudou de preço ou de regras? Abre uma *issue* ou um *pull request*.

### Licença

[MIT](LICENSE). Os modelos de páginas legais são pontos de partida e não substituem aconselhamento jurídico.

---

## English

A [skill](#what-is-a-skill) for **Claude** that **builds complete websites from scratch, with you**. It asks the right questions, proposes a plan with its honest opinion and builds the site page by page. Along the way it shows you screenshots, checks everything before publishing, and helps you put it online with a domain and email. It also ships a **ready-made starter site** with accessibility, speed, security and privacy best practices already in place.

### How it works

| Phase | What happens |
|---|---|
| 🗣️ **Briefing** | Asks up to 5 key questions (what the site is for, what visitors should do, who it's for, what content you have, what style you like), then the ones specific to your type of site. |
| 🗺️ **Plan** | Proposes the sitemap, technology and hosting (with costs), the visual direction, the features and the privacy setup, and gives its honest opinion. **Only moves on with your approval.** |
| 🎨 **Visual identity** | Builds a design system from your brand (contrast-checked colors, typography, spacing) so the site doesn't look like a generic template. |
| 🏠 **Home page** | Builds the full home page first and shows you mobile and desktop screenshots. **You adjust it before the rest is built.** |
| 🧱 **Rest of the site** | Builds the other pages, the 404 page, legal pages (privacy, EU/Portugal requirements), SEO, favicon and share image. |
| ✅ **Verification** | Tests 3 screen sizes, the console, links, the form, Lighthouse (target ≥ 90), images, accessibility, privacy and leftover placeholder text. **Asks before publishing.** |
| 🚀 **Launch** | Publishes (GitHub Pages, Netlify, Cloudflare, Vercel), connects the domain, sets up email (SPF/DKIM/DMARC) and Google Search Console, tests the live site, and leaves you a `COMO-EDITAR.md` maintenance guide. |

### Included

- **6 reference guides** ([`references/`](references/)): briefing questions for 11 site types; choosing technology, hosting, forms, CMS and cookie-free analytics, with costs; a full design guide; page content and EU/Portugal legal pages; the pre- and post-launch checklist; launch, domain, email and maintenance.
- **A starter site** ([`assets/starter/`](assets/starter/)), tested on mobile, desktop and dark mode. It has semantic, accessible HTML, CSS design tokens with dark mode, SEO and sharing metadata, security headers for Netlify, Cloudflare and Vercel, zero trackers, a 404 page, a privacy policy template and about 1 KB of JavaScript.

The guides are in Portuguese, but Claude replies in the language you write in.

### Example prompts

- "I want a website for my bakery"
- "I need a landing page for my app"
- "Make me a photography portfolio"
- "Rebuild my restaurant's site from scratch"

### Works well with

- [`website-doctor`](https://github.com/mozuraa/claude-skill-website-doctor): a full checkup before publishing, and site care afterwards.
- [`code-for-noobs`](https://github.com/mozuraa/claude-skill-code-for-noobs): if you want to understand what's being built.

### Installation

```bash
git clone https://github.com/mozuraa/claude-skill-website-builder.git ~/.claude/skills/website-builder
```

Or with the whole library as a plugin: `/plugin marketplace add mozuraa/claude-skills` then `/plugin install criacao@mozuraa-skills`. For the Claude app / claude.ai, use **Code → Download ZIP** and upload it under **Settings → Skills**.

### What is a skill?

A skill is a folder with a `SKILL.md` file: a name, a description of when it should be used, and instructions. Claude only reads the description until it becomes relevant; when a request matches, it loads the instructions and follows them.

### License

[MIT](LICENSE). The legal page templates are starting points, not legal advice.
