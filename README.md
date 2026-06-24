# Blog HendelCode

Blog técnico sobre **programação**, **vibe coding** com IA, **análise de dados** e **aprendizado**.

- **Gerador**: [Hugo](https://gohugo.io/) (extended)
- **Tema**: [Hextra](https://github.com/imfing/hextra) — o mesmo do [akitaonrails.com](https://akitaonrails.com/)
- **Hospedagem**: [GitHub Pages](https://pages.github.com/) (gratuita)
- **CI/CD**: GitHub Actions (build + deploy automáticos no push para `main`)

## Rodar localmente

Pré-requisitos:

- Hugo extended >= 0.146.0 ([instalação](https://gohugo.io/installation/))
- Git (com submódulos)

Clone com o tema:

```bash
git clone --recurse-submodules https://github.com/hendelsantos/blog_hendelcode_Hugo.git
cd blog_hendelcode_Hugo
```

Servidor de desenvolvimento:

```bash
hugo server -D
```

Abra http://localhost:1313/blog_hendelcode_Hugo/

Build de produção:

```bash
hugo --gc --minify
```

O conteúdo fica em `content/` em Markdown. Cada seção tem seu próprio diretório:

```
content/
├── blog/           # Posts gerais
├── stacks/         # Stacks e ferramentas
├── vibe-coding/    # Vibe coding com IA
├── dados/          # Análise de dados
├── aprendizado/    # Anotações de estudo
├── sobre.md        # Página sobre
└── arquivo/        # Arquivo por data
```

## Deploy

O deploy é automático via `.github/workflows/hugo.yml` a cada push em `main`.
No repositório do GitHub, em **Settings → Pages → Build and deployment → Source**, selecione **GitHub Actions**.

## Estrutura

```
.
├── .github/workflows/hugo.yml   # CI/CD
├── archetypes/                  # Templates de novo post
├── assets/                      # CSS/JS customizados
├── content/                     # Posts em Markdown
├── layouts/                     # Overrides do tema (opcional)
├── static/images/               # Logos e imagens
├── themes/hextra/               # Tema (git submodule)
└── hugo.toml                    # Configuração do site
```

## Criar um novo post

```bash
hugo new content blog/meu-post.md
```

Edite o front matter (`title`, `date`, `tags`, `draft = false`) e escreva em Markdown.

---

Inspiração: [AkitaOnRails](https://akitaonrails.com/).
