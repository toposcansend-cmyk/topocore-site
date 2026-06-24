# Topocore — Handoff (versão pública-segura)

> **Para quem chega agora (inclusive Claude no celular):** este documento é o
> ponto de partida para continuar o trabalho do site da Topocore. É uma versão
> **pública-segura** — sem segredos, credenciais ou dados pessoais. Está dentro
> do próprio repositório, então você o recebe automaticamente ao clonar.
>
> **Antes de editar qualquer coisa:** clone o repo, leia o `index.html` e as 4
> landings, e diga em voz alta o que entendeu do posicionamento abaixo. Só
> então mexa em algo.

---

## 1. O que é a Topocore (posicionamento DEFINITIVO)

**Empresa de software sob medida, com método de engenharia.** Faz parte do
**Grupo Toposcan**.

Frase-âncora: *"A Toposcan transforma a realidade em dados. A Topocore
transforma seus dados em gestão."*

Regras de copy que **não se negociam**:

- **Software sob medida é a manchete.** PIX, WhatsApp, CRM, NF-e são
  **módulos / prova de capacidade**, **nunca** a manchete. Eles ilustram que o
  método funciona — não são o produto.
- **Tom premium e analítico**, não apelativo. Nada de "explosão de vendas",
  emoji gritando, urgência falsa.
- **CTA = diagnóstico** (conversa de diagnóstico), não "compre agora".
- **n=1 honesto:** a base já roda no próprio Grupo Toposcan. Diga isso com
  honestidade — é uma prova real, não um case inflado. Não invente clientes,
  números ou depoimentos.
- **Sem preço** no site. Preço é conversa, não vitrine.

Se uma edição empurra PIX/cobrança para o topo como se fosse o produto, ou
adota tom de "guru de vendas", está **errada** — reverta.

## 2. Onde mora e como publica

- **Repositório:** `toposcansend-cmyk/topocore-site` (público).
- **Domínio de produção:** `topocore.com.br` (hospedado no HostGator). **É lá
  que se verifica** o resultado final.
- **Deploy:** automático. Todo push na branch **`main`** dispara o workflow
  `.github/workflows/deploy-hostgator.yml`, que envia os arquivos por FTP para
  o HostGator. As credenciais de FTP ficam em **GitHub Actions Secrets** (não
  estão no repo, e não devem estar).
- **Cache:** o `.htaccess` força o HTML a sempre revalidar, então o deploy
  aparece na hora (sem precisar de hard-refresh).
- **Stack:** páginas estáticas, **sem build**. HTML com CSS e JS inline. Fontes
  via Google Fonts (Jost + Poppins + Rubik). Logos e imagens em `marca/`.

⚠️ **Cuidado no workflow:** `dangerous-clean-slate` fica **desligado** de
propósito — ligá-lo apagaria arquivos que existem só no servidor (`.htaccess`
real, `cgi-bin`, etc.). Não ligue.

## 3. Mapa dos arquivos

| Arquivo | Papel |
|---|---|
| `index.html` | Home institucional. H1: *"Sua empresa tem um jeito próprio de operar. Seu software também deveria ter."* É o arquivo principal e o maior. |
| `cobranca-automatica-whatsapp-pix.html` | Landing de captação por dor (cobrança automática WhatsApp + PIX). |
| `construtora.html` | Landing por segmento — construtora. |
| `engenharia.html` | Landing por segmento — empresa de engenharia. |
| `topografia.html` | Landing por segmento — empresa de topografia. |
| `obrigado.html` | Página de pós-conversão (após enviar contato). |
| `privacidade.html` / `termos.html` | Jurídico (LGPD / termos de uso). |
| `marca/` | Logos (`topocore-logo*.svg`), `favicon.svg`, `og-cover.png`. |
| `sitemap.xml` / `robots.txt` / `.htaccess` | SEO + servidor. |

As 4 landings (cobrança, construtora, engenharia, topografia) seguem a mesma
estrutura/estilo da home; ao editar uma, confira se as outras precisam do mesmo
ajuste para manter consistência.

## 4. Identidade visual

- Azul primário `#1E5BFF` (variações `--azul-claro #5B85FF`), verde de acento
  `#16C784`, sobre fundo escuro (`--bg #0D0D0D`).
- Tipografia: Jost (títulos), Poppins (destaques), Rubik (corpo).
- Alinhada à marca-mãe **Toposcan** (`toposcan.com.br`).

Os tokens de cor estão como CSS custom properties no `:root` de cada HTML —
mude lá, não hardcode hex no meio do conteúdo.

## 5. Fluxo de trabalho recomendado

1. Clonar: `gh repo clone toposcansend-cmyk/topocore-site` (ou `git clone`).
2. Ler `index.html` + as 4 landings antes de propor qualquer mudança.
3. Editar em **branch**, abrir **PR** (de preferência draft), revisar o diff.
4. Só faça merge na `main` quando tiver certeza — **merge na `main` publica em
   produção** automaticamente.
5. Depois do deploy, verifique em `https://topocore.com.br` (não só no preview
   local), porque o que vale é o que está no ar.

## 6. Honestidade sobre o que transfere — e o que NÃO

✅ **Transfere bem (está no git ou aqui neste doc):**
- O site inteiro (é um repositório git).
- A estratégia e as decisões de posicionamento (este handoff).
- A continuação de copy, SEO e novas páginas.

⚠️ **NÃO transfere automaticamente** (depende da máquina/ambiente original):
- Verificação visual no navegador (o browser controlado por ferramenta usado
  para inspecionar o layout e operar Google Ads / GA4).
- Backend do CRM, integrações locais e o bot de WhatsApp.

Ou seja: **site e estratégia, você continua perfeitamente daqui.** Para
verificação visual real no navegador ou para o backend do CRM, o ambiente é
mais limitado — assuma isso com honestidade em vez de fingir que rodou.

---

*Versão pública-segura. Não inclua aqui credenciais, números de WhatsApp,
CNPJ/razão social, nomes de repositórios privados ou detalhes de
infraestrutura. Isso é de propósito: este arquivo viaja com o repositório
público.*
