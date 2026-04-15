# Site Dr. Henrique Alvarenga — versão Quarto

Nova versão do site pessoal, construída com [Quarto](https://quarto.org).
Substitui o antigo site em Jekyll.

## Estrutura

```
Nova_Pagina/
├── _quarto.yml          ← configuração do site (navbar, rodapé, tema)
├── custom.scss          ← cores, fontes, estilos personalizados
├── index.qmd            ← Página inicial
├── sobre.qmd            ← Formação Acadêmica
├── publicacoes.qmd      ← Publicações, livros, artigos, palestras
├── contato.qmd          ← Contato e endereço
├── images/              ← Fotos (retrato, consultório, jubileu...)
└── docs/                ← Saída renderizada (gerada pelo Quarto; o GitHub Pages serve essa pasta)
```

## Como editar

1. Abra qualquer arquivo `.qmd` no **Positron** (ou RStudio / VSCode).
2. Edite o texto em Markdown — igual ao que você já faz nos seus outros projetos Quarto.
3. Salve.

## Como renderizar (preview local)

No Positron (ou no Terminal, dentro desta pasta):

```bash
quarto preview        # abre o site com auto-reload
quarto render         # gera os arquivos finais em docs/
```

## Como publicar no GitHub Pages

### Primeiro deploy — passos únicos

1. Copie o conteúdo desta pasta `Nova_Pagina` para a raiz do seu repositório `henriquealvarenga/henriquealvarenga.github.io` (ou para uma branch nova, por segurança).
2. **Desative o workflow antigo do Jekyll**: no GitHub, vá em `Settings → Pages` e em **Source** selecione **Deploy from a branch** → **main** → pasta **/docs**.
3. Apague (ou desabilite) o arquivo `.github/workflows/jekyll.yml` — não é mais necessário, pois Quarto gera HTML estático pronto.
4. Crie um arquivo vazio chamado `.nojekyll` dentro de `docs/` para impedir que o GitHub Pages tente processar com Jekyll:
   ```bash
   touch docs/.nojekyll
   ```

### Fluxo de atualização (dia-a-dia)

```bash
# 1. editar os .qmd que quiser
# 2. renderizar
quarto render
# 3. commit + push
git add .
git commit -m "Atualiza página"
git push
```

Em ~1 minuto o site está no ar em <https://henriquealvarenga.github.io>.

## Por que Quarto é melhor que Jekyll no seu caso

- **Você já usa Quarto** em todos os outros projetos — um fluxo único.
- **Render local**: você vê exatamente como vai ficar antes de publicar.
- **Sem GitHub Actions** — deploy direto da pasta `docs/`, menos coisa para quebrar.
- Suporte nativo a **código R/Python**, **gráficos**, **citações**, **matemática** — útil se no futuro quiser publicar posts técnicos, materiais didáticos, etc.
- **Temas bonitos prontos** + SCSS customizável (veja `custom.scss`).
- **Markdown padrão** — arquivos legíveis e fáceis de editar direto no GitHub também, se precisar.

## Paleta e tipografia atuais

- Cor primária: **#1f3a5f** (azul profundo)
- Cor secundária: **#b08968** (terra/areia)
- Fontes: **Inter** (texto) + **Playfair Display** (títulos)

Para ajustar, edite `custom.scss`.
