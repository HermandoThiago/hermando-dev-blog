# hermando.dev — Blog Pessoal

Blog pessoal de Hermando Thiago sobre programação, análise de dados e tecnologia.

## Sobre

Site estático construído com **Astro**, focado em conteúdo técnico nas áreas de:

- Desenvolvimento backend (TypeScript, Node.js, NestJS, Python)
- Análise de dados e automação
- Arquitetura de software
- Tecnologia em geral

## Stack

| Tecnologia | Versão | Uso |
| :--------- | :----- | :-- |
| Astro | 5.17.1 | Framework principal |
| TypeScript | 5.9.3 | Linguagem |
| Tailwind CSS | 4.2.1 | Estilização |
| MDX | 4.3.13 | Suporte a componentes em posts |

**Outras integrações:** `@astrojs/sitemap`, `@astrojs/rss`, `astro-icon`, `sharp`

## Estrutura do Projeto

```text
hermando-dev-blog/
├── public/
│   └── fonts/              # Fontes (Atkinson Regular/Bold)
├── src/
│   ├── assets/             # Imagens dos posts
│   ├── components/         # Componentes reutilizáveis
│   │   ├── BaseHead.astro  # Meta tags e SEO
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   └── FormattedDate.astro
│   ├── content/
│   │   └── blog/           # Posts em Markdown/MDX
│   ├── icons/              # Ícones SVG (GitHub, LinkedIn, Bash)
│   ├── layouts/
│   │   └── BlogPost.astro  # Layout dos posts
│   ├── pages/
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── blog/
│   │   └── rss.xml.js
│   ├── styles/
│   │   └── global.css
│   ├── content.config.ts   # Schema das coleções
│   └── consts.ts           # Constantes globais
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## Comandos

Todos os comandos devem ser executados na raiz do projeto:

| Comando | Ação |
| :------ | :--- |
| `pnpm install` | Instala as dependências |
| `pnpm dev` | Inicia o servidor local em `localhost:4321` |
| `pnpm build` | Gera o site de produção em `./dist/` |
| `pnpm preview` | Pré-visualiza o build localmente |
| `pnpm astro ...` | Executa comandos da CLI do Astro |

## Criando um novo post

Crie um arquivo `.md` ou `.mdx` em `src/content/blog/` com o seguinte frontmatter:

```markdown
---
title: 'Título do Post'
description: 'Breve descrição do conteúdo'
pubDate: 'Mar 17 2026'
heroImage: '../assets/nome-da-imagem.png'
draft: false
---

Conteúdo do post aqui...
```

**Campos disponíveis:**

| Campo | Tipo | Obrigatório | Descrição |
| :---- | :--- | :---------- | :-------- |
| `title` | string | sim | Título do post |
| `description` | string | sim | Descrição curta (usada no SEO e listagem) |
| `pubDate` | date | sim | Data de publicação |
| `updatedDate` | date | não | Data da última atualização |
| `heroImage` | image | não | Imagem de capa |
| `draft` | boolean | não | `true` oculta o post da listagem |

## Artigos Publicados

| Data | Título | Arquivo |
| :--- | :----- | :------ |
| 16/03/2026 | [Por que o Astro deveria ser seu próximo framework frontend (mas não o primeiro)](src/content/blog/por-que-o-astro-deveria-ser-seu-proximo-framework.md) | `por-que-o-astro-deveria-ser-seu-proximo-framework.md` |
| 22/03/2026 | [O mínimo de comandos linux para todo profissional de tecnologia](src/content/blog/comandos-linux-essenciais-para-devs.md) | `comandos-linux-essenciais-para-devs.md |

## Funcionalidades

- SEO otimizado com canonical URLs, OpenGraph e Twitter Cards
- Feed RSS em `/rss.xml`
- Sitemap automático
- Design responsivo (mobile-first)
- Suporte a português brasileiro (`lang="pt-br"`)
- Otimização de imagens com Sharp
