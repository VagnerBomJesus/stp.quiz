# Landing page · STP Quiz

Página HTML standalone (`index.html`) que apresenta a aplicação **STP Quiz**
ao público, mais as páginas legais `privacy.html`, `terms.html` e
`support.html`. Tema claro, azul `#8257E5`, tipografia Poppins (títulos) e
Open Sans (texto), mockups de telemóvel em CSS com os ecrãs reais da app.

Publicada via GitHub Pages em <https://vagnerbomjesus.github.io/stp.quiz/>
(Settings → Pages → Branch `main` · Folder `/docs`).

## Estrutura do `index.html`

1. **Nav**: logo, âncoras, seletor PT/EN/FR, menu hambúrguer em mobile
2. **Hero**: título, badge Google Play, telemóvel e cartão com números (160 · 8 · 4 · 3)
3. **Porquê a STP Quiz**: 4 pontos numerados (privacidade, grátis, offline, fontes)
4. **Funcionalidades**: painel azul com 3 telemóveis + 4 pontos (Curiosidade do Dia, mecânicas, estatísticas, quiz aleatório)
5. **Temas**: 8 cartões · **Níveis**: 4 cartões com as regras reais (×1…×4, 50/50, 20 s/3 vidas, 10 s/1 vida)
6. **Ecrãs**: fila horizontal de 9 telemóveis sobre faixa azul
7. **Factos e Números**: 6 dos 19 factos
8. **Novidades 1.1.0**: anéis + changelog
9. **FAQ**: acordeão acessível (7 perguntas, alinhadas com a FAQ da app)
10. **Contacto** + autor · **CTA final** · **Footer**

## Idiomas

O HTML está em **português** (fonte de verdade). Os dicionários EN e FR
estão no `<script>` no fim do ficheiro. A língua é escolhida por esta
ordem: `localStorage` (`stpquiz.lang`) → `?lang=xx` → idioma do browser →
`pt`. A escolha é partilhada entre todas as páginas.

## Imagens (`images/`)

| Ficheiro | Origem | Uso |
|---|---|---|
| `screens/01.webp` … `09.webp` | ecrãs recortados do set `android-screenshot-set-black-centered-v3` da app (480 px de largura) | dentro dos mockups CSS |
| `logo.png`, `favicon-64.png`, `apple-touch-icon.png` | `assets/images/logo.png` da app (logo atual "STP?") | nav, favicon |
| `og-image.png` | gerada (1200×630) | partilha em redes sociais |
| `vagnerbomjesus.webp` | avatar do autor | secção Contacto |
| `en_badge_web_generic_google_play.png` | badge oficial Google | CTA |

Peso total das imagens: ~0,4 MB (antes: ~6,7 MB de PNG).

## Fontes e ícones (sem pedidos a terceiros)

Poppins e Open Sans (licença OFL) estão em `fonts/` como `.woff2` (latin +
latin-ext), declaradas com `@font-face` no topo de cada página. Os ícones
Material Symbols Rounded (Apache 2.0) são um sprite SVG inline no
`index.html` (`<symbol id="i-...">`), usados com `<svg class="ic"><use href="#i-nome"/></svg>`.
O site não faz nenhum pedido a domínios externos (verificado: 0 pedidos).

## Ficheiros de descoberta

`robots.txt`, `sitemap.xml` (com `hreflang`), `llms.txt` (resumo para IA),
`humans.txt`, `.well-known/security.txt` (RFC 9116), `site.webmanifest`,
`.nojekyll` e dados estruturados JSON-LD no `index.html`
(`MobileApplication`, `Person`, `WebSite`, `FAQPage`). A revisão de
segurança e RGPD está em `../SECURITY_PRIVACY_REVIEW.md`.

## Personalização rápida

Todos os tokens estão em `:root` no topo de cada ficheiro:

```css
:root {
  --primary: #8257E5;   /* roxo da marca, igual a BrandColors.defaults na app Flutter */
  --ink:     #1E1E1E;
  --text:    #3A3A3A;
  --soft:    #F6F7FB;
}
```

Para atualizar os ecrãs, substituir os `.webp` em `images/screens/`
mantendo a numeração (01 = boas-vindas … 09 = resultado).

## Páginas legais

`privacy.html`, `terms.html` e `support.html` são geradas a partir de um
único modelo (nav completa, cabeçalho com separadores entre as três páginas,
índice lateral com realce ao scroll) e partilham o mecanismo de idioma. A **Política de Privacidade em vigor é a `privacy.html`**;
o `PRIVACY.md` na raiz é a fonte em Markdown e deve ser mantido em sincronia.

## TODO

- [ ] Badge Google Play em PT/FR (por agora usa o badge EN em todas as línguas)
- [ ] Vídeo/GIF de demonstração no hero
