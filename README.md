# Topocore — Site institucional

Site (landing page) da **Topocore**, empresa de software do **Grupo Toposcan**.
*O núcleo do seu negócio — da proposta ao PIX, num só sistema.*

## Stack
Página estática, **arquivo único** (`index.html`), sem build. CSS e JS inline. Fontes via Google Fonts (Jost + Rubik). Logos em `marca/`.

## Rodar localmente
Abra `index.html` no navegador. Só isso.

## Publicar
- **GitHub Pages:** Settings → Pages → Branch `main` / pasta `/ (root)`. O `index.html` na raiz é servido automaticamente.
- **HostGator (produção):** subir o `index.html` (e a pasta `marca/`) para a pasta `public_html` via cPanel/FTP. Domínio: `topocore.com.br`.
- **Domínio customizado no Pages (opcional):** criar um arquivo `CNAME` na raiz com `topocore.com.br` e apontar o DNS.

## Antes de publicar — preencher placeholders
No `index.html`, substituir:
- `55SEUNUMEROAQUI` → número de WhatsApp com DDI+DDD (ex.: `5511999998888`).
- No rodapé (campos com fundo cinza): **WhatsApp**, **e-mail**, **razão social**, **CNPJ**, **cidade/UF**.

## Identidade
Azul `#006CFF` sobre fundo escuro, fontes Jost + Rubik — alinhado à marca-mãe [Toposcan](https://toposcan.com.br).

© 2026 Topocore · Grupo Toposcan.
