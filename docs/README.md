# Landing page · STP Quiz

Página HTML standalone que apresenta a aplicação **STP Quiz** ao
público — design inspirado em [Subo](https://www.getsubo.app/) e usando
o sistema de cores e tipografia da própria app (Poppins, gradient
azul→roxo, accent verde `#04D361`).

## Activar GitHub Pages

1. No repositório `VagnerBomJesus/stp.quiz` → **Settings → Pages**.
2. **Source:** `Deploy from a branch`.
3. **Branch:** `main` · **Folder:** `/docs` · **Save**.
4. Após ~1 min a página fica online em:
   `https://vagnerbomjesus.github.io/stp.quiz/`

## Personalização rápida

Tudo está num único `index.html` com CSS e JS inline. Os tokens do
design system estão no topo, em `:root`:

```css
:root {
  --brand-primary:    #8257E5;
  --brand-secondary:  #57B6E5;
  --brand-green:      #04D361;
  --bg:               #0F0F18;
  --surface:          #1B1B28;
  /* ... */
}
```

## Imagens

Carregadas via `raw.githubusercontent.com` a partir de `quizstp/assets/images/`:

- `logo.png` — ícone no nav, hero e favicon
- `vagnerbomjesus.png` — avatar na secção do autor

Se mudares o nome do repo, actualiza os URLs em `index.html` (procura por
`VagnerBomJesus/stp.quiz`).

## Estrutura da página

1. **Nav** — logo + funcionalidades + autor + FAQ + GitHub
2. **Hero** — logo, headline com gradient, CTA para Google Play
3. **3 pillars** — Privacidade · Gratuita · Offline
4. **Categorias** (6 temas) + chips de níveis
5. **Personalização** — phone mockup com cartão de progresso + paleta
6. **Factos & Números** — 6 dados destacados
7. **Autor** — Vagner Bom Jesus
8. **FAQ** — accordion com 6 perguntas
9. **CTA final**
10. **Footer** — Privacidade · GitHub · Contacto

## TODO futuro

- [ ] Substituir o phone mockup CSS por screenshots reais da app
- [ ] Versão EN/FR (criar `/en/index.html` e `/fr/index.html`)
- [ ] Substituir "Em breve na Google Play" pelo URL real assim que a app for publicada
- [ ] Criar `og:image` dedicada (1200×630) em vez de usar o logo
