<p align="center">
  <img src="icon.svg" width="160" alt="Website doctor — janela de browser com batimento cardíaco e estetoscópio">
</p>

<h1 align="center">Website doctor — Claude Skill</h1>

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

Uma [skill](#o-que-é-uma-skill) para o **Claude** que funciona como **médico do teu site**: examina tudo o que afeta o bom funcionamento, mostra-te um relatório de saúde por prioridades, dá-te a opinião sincera sobre o que fazer primeiro e corrige — só o que autorizares.

### O que examina (12 áreas)

| Área | Exemplos |
|---|---|
| 🧩 **Funcionamento** | erros na consola, links partidos, 404, formulários que não enviam, redirecionamentos |
| 📐 **Layout e alinhamentos** | telemóvel/tablet/desktop, scroll horizontal, elementos sobrepostos, espaçamentos, modo escuro, `100vh` no iPhone |
| 🖼️ **Imagens e media** | peso, WebP/AVIF, tamanho certo, `alt`, deformações, favicon e imagem de partilha, GPS nas fotos |
| ⚡ **Desempenho** | Core Web Vitals (LCP, INP, CLS), JS e fontes pesados, cache, compressão, scripts de terceiros |
| 🔒 **Segurança** | HTTPS, HSTS, CSP e outros cabeçalhos, chaves secretas expostas, `.env`/`.git` públicos, XSS, injeção SQL, cookies, dependências vulneráveis, regras Firebase/Supabase |
| 🍪 **Privacidade e RGPD** | rastreadores antes do consentimento, banner de cookies, política de privacidade, Google Fonts, YouTube, dados pessoais em URLs |
| ♿ **Acessibilidade** | WCAG 2.2 AA: contraste, teclado, foco, etiquetas, cabeçalhos, alvos de toque, zoom |
| 🔎 **SEO e partilha** | títulos, descrições, canonical, sitemap, robots, dados estruturados, Open Graph |
| ✍️ **Conteúdo** | gralhas, *Lorem ipsum* esquecido, contactos e ano desatualizados |
| 🌐 **Compatibilidade** | Safari/iOS, Chrome, Firefox, Android, ligações lentas |
| 📮 **Domínio, alojamento e email** | SSL a expirar, DNS, SPF/DKIM/DMARC, cópias de segurança, monitorização |
| 🧹 **Qualidade do código** | avisos de build, linter, `console.log`, dependências desatualizadas, tratamento de erros |

A lista completa (mais de 150 verificações) está em [`references/checklist.md`](references/checklist.md) e os comandos para cada uma em [`references/como-verificar.md`](references/como-verificar.md).

### Como trabalha

1. **🩺 Consulta:** faz-te algumas perguntas, como o que examinar (URL, código ou os dois), se é um exame completo ou um problema concreto, para que serve o site e se pode corrigir.
2. **🔬 Exame:** verifica com provas. Abre o site em telemóvel e desktop, lê a consola e a rede, mede a velocidade, lê os cabeçalhos e o código. Sem prova, não aponta problemas.
3. **📋 Relatório de saúde:** mostra uma tabela por área (🟢🟡🟠🔴) e os problemas por gravidade. Para cada um diz o que é, onde está, porque importa, como corrigir e o esforço.
4. **💬 Opinião e perguntas:** diz-te francamente o que faria primeiro e o que não vale o esforço, e pergunta-te o que só tu podes decidir. Se sugerires algo, diz-te honestamente se concorda e porquê.
5. **🛠️ Tratamento:** corrige uma coisa de cada vez, verifica cada correção (com capturas antes e depois no layout) e pede confirmação antes de tudo o que é arriscado.
6. **✅ Alta:** resume o que ficou resolvido, o que falta e o que tens de fazer tu.

### Exemplos de pedidos

- "Revê o meu site, https://…"
- "O menu fica desalinhado no telemóvel"
- "O meu site é seguro? Cumpre o RGPD?"
- "Porque é que o site está tão lento?"
- "Melhora tudo o que conseguires no meu site"

Vê um exemplo completo de relatório em [`examples/exemplo.md`](examples/exemplo.md).

### Segurança e ética

A skill só examina sites que são teus ou que estás autorizado a testar, e todas as verificações são passivas: lê código, cabeçalhos e o que o site mostra publicamente. Nunca ataca nem explora falhas. Quando encontra um segredo exposto, não o repete e diz-te como o revogar.

### Funciona com

HTML/CSS/JS, React, Next.js, Vue, Nuxt, Svelte, Astro, Vite, WordPress, PHP, sites estáticos (GitHub Pages, Netlify, Vercel), Firebase e Supabase. Em plataformas fechadas (Shopify, Wix, Squarespace) foca-se em conteúdo, imagens, velocidade, SEO, acessibilidade e cookies.

Funciona melhor no **Claude Code** com acesso ao código e a um browser, mas também funciona só com um URL.

### Instalação

**Claude Code (para todos os teus projetos)**

```bash
git clone https://github.com/mozuraa/claude-skill-website-doctor.git ~/.claude/skills/website-doctor
```

**Claude Code (só num projeto)** — dentro da pasta do projeto:

```bash
git clone https://github.com/mozuraa/claude-skill-website-doctor.git .claude/skills/website-doctor
```

**Ou com toda a biblioteca, como plugin:** ver [mozuraa/claude-skills](https://github.com/mozuraa/claude-skills).

**App Claude / claude.ai:** carrega em **Code → Download ZIP** e carrega o ZIP nas **Definições**, na secção **Skills** (em *Capacidades*).

Abre uma sessão nova para a skill ser carregada. Para atualizar: `cd ~/.claude/skills/website-doctor && git pull`.

### O que é uma skill?

Uma skill é uma pasta com um ficheiro `SKILL.md`: um nome, uma descrição de quando deve ser usada e instruções. O Claude lê só a descrição até ela ser útil; quando o pedido encaixa, carrega as instruções e segue-as.

### Estrutura

```
claude-skill-website-doctor/
├── SKILL.md                   # a skill: consulta → exame → relatório → decisão → tratamento → alta
├── references/
│   ├── checklist.md           # 12 áreas, 150+ verificações
│   └── como-verificar.md      # comandos e ferramentas para cada verificação
├── examples/
│   └── exemplo.md             # exemplo de consulta e relatório
├── icon.svg
├── README.md
├── CHANGELOG.md
└── LICENSE
```

### Contribuir

Falta alguma verificação? Algum comando deixou de funcionar? Abre uma *issue* ou um *pull request*.

### Licença

[MIT](LICENSE)

---

## English

A [skill](#what-is-a-skill) for **Claude** that acts as your **website's doctor**. It examines everything that affects how well the site works, shows a health report by priority, gives its honest opinion on what to do first, and fixes things, but only what you approve.

### What it examines (12 areas)

| Area | Examples |
|---|---|
| 🧩 **Functionality** | console errors, broken links, 404s, forms that don't send, redirects |
| 📐 **Layout & alignment** | mobile/tablet/desktop, horizontal scroll, overlapping elements, spacing, dark mode, `100vh` on iPhone |
| 🖼️ **Images & media** | weight, WebP/AVIF, right size, `alt`, distortion, favicon and share image, GPS in photos |
| ⚡ **Performance** | Core Web Vitals (LCP, INP, CLS), heavy JS and fonts, caching, compression, third-party scripts |
| 🔒 **Security** | HTTPS, HSTS, CSP and other headers, exposed secret keys, public `.env`/`.git`, XSS, SQL injection, cookies, vulnerable dependencies, Firebase/Supabase rules |
| 🍪 **Privacy & GDPR** | trackers before consent, cookie banner, privacy policy, Google Fonts, YouTube, personal data in URLs |
| ♿ **Accessibility** | WCAG 2.2 AA: contrast, keyboard, focus, labels, headings, touch targets, zoom |
| 🔎 **SEO & sharing** | titles, descriptions, canonical, sitemap, robots, structured data, Open Graph |
| ✍️ **Content** | typos, leftover *Lorem ipsum*, outdated contacts and year |
| 🌐 **Compatibility** | Safari/iOS, Chrome, Firefox, Android, slow connections |
| 📮 **Domain, hosting & email** | expiring SSL, DNS, SPF/DKIM/DMARC, backups, monitoring |
| 🧹 **Code quality** | build warnings, linter, `console.log`, outdated dependencies, error handling |

The full list (150+ checks) is in [`references/checklist.md`](references/checklist.md) and the commands for each one in [`references/como-verificar.md`](references/como-verificar.md) (in Portuguese; Claude translates as needed).

### How it works

1. **🩺 Consultation:** asks you a few questions, such as what to examine (URL, code or both), whether you want a full checkup or have a specific problem, what the site is for, and whether it may fix things.
2. **🔬 Examination:** checks with evidence. It opens the site on mobile and desktop, reads the console and network, measures speed, and reads the headers and code. Without evidence, it doesn't report a problem.
3. **📋 Health report:** shows a table by area (🟢🟡🟠🔴) and the issues by severity. For each one it says what it is, where it is, why it matters, how to fix it and how much effort it takes.
4. **💬 Opinion & questions:** tells you frankly what it would do first and what isn't worth the effort, and asks you about the decisions only you can make. If you suggest something, it tells you honestly whether it agrees and why.
5. **🛠️ Treatment:** fixes one thing at a time, verifies each fix (with before/after screenshots for layout), and asks before anything risky.
6. **✅ Discharge:** summarizes what was fixed, what's left and what you need to do yourself.

### Example prompts

- "Review my site, https://…"
- "The menu is misaligned on mobile"
- "Is my site secure? Is it GDPR compliant?"
- "Why is my site so slow?"
- "Improve everything you can on my site"

See a full example report in [`examples/exemplo.md`](examples/exemplo.md) (in Portuguese).

### Safety & ethics

The skill only examines sites you own or are authorized to test, and every check is passive: it reads code, headers and what the site shows publicly. It never attacks or exploits anything. When it finds an exposed secret, it doesn't repeat it and tells you how to revoke it.

### Works with

HTML/CSS/JS, React, Next.js, Vue, Nuxt, Svelte, Astro, Vite, WordPress, PHP, static sites (GitHub Pages, Netlify, Vercel), Firebase and Supabase. On closed platforms (Shopify, Wix, Squarespace) it focuses on content, images, speed, SEO, accessibility and cookies.

It works best in **Claude Code** with access to the code and a browser, but also works with just a URL.

### Installation

**Claude Code (all projects)**

```bash
git clone https://github.com/mozuraa/claude-skill-website-doctor.git ~/.claude/skills/website-doctor
```

**Claude Code (one project only)**, from the project folder:

```bash
git clone https://github.com/mozuraa/claude-skill-website-doctor.git .claude/skills/website-doctor
```

**Or with the whole library, as a plugin:** see [mozuraa/claude-skills](https://github.com/mozuraa/claude-skills).

**Claude app / claude.ai:** click **Code → Download ZIP** and upload the ZIP in **Settings**, under **Skills** (in *Capabilities*).

Start a new session so the skill is loaded. To update: `cd ~/.claude/skills/website-doctor && git pull`.

### What is a skill?

A skill is a folder with a `SKILL.md` file: a name, a description of when it should be used, and instructions. Claude only reads the description until it becomes relevant; when a request matches, it loads the instructions and follows them.

### License

[MIT](LICENSE)
