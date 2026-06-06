# Release Notes — STP Quiz v1.0.1 (build 2)

Versão a publicar na Google Play Console com as melhorias da segunda
sprint. Cola estes textos nos campos **"Novidades desta versão"** de
cada idioma.

> **Limite Play Store:** 500 caracteres por idioma. Os textos abaixo
> estão dentro do limite.

---

## 🇵🇹 Português (pt-PT)

> 467 caracteres

```
Novidades nesta versão:

• Partilha nativa — recomenda a STP Quiz no WhatsApp, Gmail, Messenger e mais.
• Cores personalizadas — define a tua cor primária e secundária.
• Idioma do sistema por defeito (PT/EN/FR).
• Página "Sobre" redesenhada com o teu autor.
• Troféu de conquista restaurado no ecrã de resultados.
• Telas "Acertou!" e "Errou" responsivas em ecrãs pequenos.
• Cartão de partilha destacado em Definições > Sobre.

Obrigado por experimentares!
```

---

## 🇬🇧 English (en-US)

> 461 characters

```
What's new in this version:

• Native sharing — recommend STP Quiz via WhatsApp, Gmail, Messenger and more.
• Custom colors — set your own primary and secondary colour.
• Follows the system language by default (PT/EN/FR).
• Redesigned "About" page with the author.
• Achievement trophy back on the result screen.
• "Correct!" / "Wrong" screens fully responsive on small devices.
• Share card highlighted in Settings > About.

Thanks for trying it!
```

---

## 🇫🇷 Français (fr-FR)

> 487 caracteres

```
Nouveautés de cette version :

• Partage natif — recommandez STP Quiz via WhatsApp, Gmail, Messenger, etc.
• Couleurs personnalisées — définissez votre couleur primaire et secondaire.
• Suit la langue du système par défaut (PT/EN/FR).
• Page « À propos » repensée avec l'auteur.
• Trophée de réussite restauré sur l'écran des résultats.
• Écrans « Bonne réponse ! » et « Raté » responsives sur petits appareils.
• Carte de partage mise en avant dans Paramètres > À propos.

Merci d'essayer !
```

---

## Lista interna do que mudou (changelog completo)

Para referência futura — **não publicar**, é só para o autor.

### Novas funcionalidades
- 📤 **Partilha nativa** com `share_plus`: abre o share sheet do sistema (WhatsApp, Gmail, Messenger, SMS, etc.) com mensagem traduzida e URL da Play Store.
- 🎨 **Cores personalizadas**: secção em Definições onde o utilizador define a sua cor primária e secundária via paleta de 12 cores ou entrada HEX manual. Pré-visualização do cabeçalho em tempo real.
- 🌍 **Idioma do sistema por defeito**: `LocaleService.load()` devolve `null` quando nada está guardado e o `MaterialApp` segue o idioma do dispositivo (PT/EN/FR).
- ℹ️ **Página "Sobre" redesenhada**: hero com logo + 9 secções (o que é, funcionalidades, propósito, personalização, privacidade, tecnologia, contribuir, autor com avatar do Vagner, agradecimentos) + cartão "Partilhar a aplicação" em destaque.
- 🏆 **Troféu** restaurado no ecrã de resultados (`assets/images/trophy.png`).

### Melhorias de UX
- ✅ Ecrãs "Acertou!" / "Errou" agora ajustam-se a qualquer tamanho (scroll + escala fluida via `LayoutBuilder`); botão sempre ancorado no fundo.
- ✅ Ecrã de resultado responsivo com mesmo padrão.
- ✅ Cartão das categorias com mais respiração, ícone destacado e tipografia maior.
- ✅ Níveis em chips com largura adaptativa para o idioma (sem quebra de linha).
- ✅ Footer das Definições deixou de ser fixo (faz scroll com a lista).
- ✅ Página de Factos & Números agora acessível pela página "Sobre".
- ✅ Versão removida da lista de tiles em Definições (vive no cartão hero da página Sobre).

### Infra / código
- 📦 Nova dependência `share_plus: ^10.1.2`.
- 🏗 Novo `lib/core/app_links.dart` com URL da Play Store, repo, política e email.
- 🏗 Novo `lib/core/brand_colors.dart` com `BrandColors` + `BrandScope` (InheritedWidget) + `brandColorsNotifier`.
- 🏗 Novo serviço `BrandColorsService` para persistência.
- 🏗 Refactor de todas as referências a `AppColors.purple/lightBlue` para `context.brand.primary/secondary`.
- 🏗 i18n alargada (~30 chaves novas em PT/EN/FR para about, custom colors, share).

### Documentação
- 📄 `PRIVACY.md` público para URL da Play Console.
- 📄 `store/listing_{pt,en,fr}.md` com descrições da loja.
- 📄 `store/CHECKLIST.md` com passos de publicação.
- 📄 `docs/index.html` com landing page (GitHub Pages).
- 📄 README atualizado.
