# Release Notes, STP Quiz v1.1.0 (build 15)

Cópia das notas oficiais em `quizstp/docs/product/RELEASE_NOTES_1.1.0.md`.
Cola um dos blocos no campo "Novidades desta versão" da Play Console
(limite: 500 caracteres, os blocos curtos abaixo respeitam-no).

---

## 🇵🇹 Português (pt-PT), versão curta

```
Novidades:

• 160 perguntas (antes 55): 20 por tema, nos 4 níveis, com explicação e fonte.
• Alternativas embaralhadas em todos os níveis.
• Nova página de revisão de respostas.
• Curiosidade do Dia às 9h locais.
• Quiz aleatório com as mecânicas do nível escolhido.
• Confirmação ao sair de um quiz.
• Interface a toda a largura no Android 15 e download mais pequeno.

Obrigado!
```

## 🇬🇧 English (en-US), short

```
What's new:

• 160 questions (up from 55): 20 per topic across all 4 levels, with explanation and source.
• Shuffled answer choices at every level.
• Redesigned answer review page.
• Fact of the Day at 9 a.m. local time.
• Random quizzes now use the mechanics of the level you pick.
• Confirmation when leaving a quiz.
• Edge-to-edge layout on Android 15 and a smaller download.

Thanks!
```

## 🇫🇷 Français (fr-FR), court

```
Nouveautés :

• 160 questions (contre 55): 20 par thème sur les 4 niveaux, avec explication et source.
• Réponses mélangées à tous les niveaux.
• Nouvelle page de révision des réponses.
• Info du Jour à 9 h locales.
• Quiz aléatoire avec les mécaniques du niveau choisi.
• Confirmation avant de quitter un quiz.
• Affichage bord à bord sur Android 15 et téléchargement allégé.

Merci !
```

---

## Notas completas (origem: repositório da app)

# STP Quiz 1.1.0, versão estável

Build 15. Sucede a `1.0.11+12` em Produção e à candidata `1.1.0-beta.1+13`,
cujas notas ficam em `RELEASE_NOTES_1.1.0_BETA1.md`.

## Português

- Catálogo ampliado de 55 para 160 perguntas.
- Quatro níveis e 20 perguntas disponíveis em cada categoria.
- Alternativas embaralhadas em todos os níveis.
- 105 novas perguntas com explicações, PT/EN/FR e fontes específicas.
- Nova página de revisão alinhada ao design de Estatísticas e Definições.
- A Curiosidade do Dia passa a chegar às 9h **locais**. Antes era calculada em
  UTC, pelo que chegava às 10h em Portugal no verão e às 11h em França.
- O quiz aleatório passa a usar as mecânicas do nível escolhido. Quem escolhia
  Perito jogava com regras de Médio, sem cronómetro, sem vidas e a ×2.
- Sair de um quiz pelo X passa a pedir confirmação, em vez de descartar a
  partida em silêncio.
- Interface a toda a largura no Android 15, sem APIs descontinuadas.
- A versão indicada nas Definições e no Sobre passa a incluir o número da
  build e a vir do pacote instalado.
- Download menor: menos 1,7 MB de material da loja que ia dentro da app e
  menos 2,6 MB por optimização do código.

## English

- Quiz catalogue expanded from 55 to 160 questions.
- Four levels and 20 questions available in every category.
- Answer choices shuffled at every level.
- 105 new questions with explanations, PT/EN/FR and specific sources.
- Redesigned answer review page consistent with Stats and Settings.
- The Daily Fact now arrives at 9am **local** time. It was computed in UTC, so
  it reached Portugal at 10am in summer and France at 11am.
- Random quizzes now use the mechanics of the level you pick. Choosing Expert
  previously played by Medium rules, no timer, no lives, ×2 instead of ×4.
- Leaving a quiz through the X now asks for confirmation instead of silently
  discarding the run.
- Edge-to-edge layout on Android 15, with no deprecated APIs.
- The version shown in Settings and About now includes the build number and
  comes from the installed package.
- Smaller download: 1.7 MB of store artwork removed from the app, plus 2.6 MB
  from code optimisation.

## Français

- Catalogue élargi de 55 à 160 questions.
- Quatre niveaux et 20 questions disponibles dans chaque catégorie.
- Réponses mélangées à tous les niveaux.
- 105 nouvelles questions avec explications, PT/EN/FR et sources spécifiques.
- Nouvelle page de révision alignée sur Statistiques et Paramètres.
- L'Info du Jour arrive désormais à 9h **locales**. Elle était calculée en UTC
  et arrivait donc à 10h au Portugal en été et à 11h en France.
- Le quiz aléatoire applique enfin les mécaniques du niveau choisi. Choisir
  Expert donnait les règles de Moyen, sans chrono, sans vies et à ×2.
- Quitter un quiz par le X demande maintenant confirmation au lieu
  d'abandonner la partie en silence.
- Affichage bord à bord sur Android 15, sans API obsolètes.
- La version affichée dans Paramètres et À propos inclut désormais le numéro
  de build et provient du paquet installé.
- Téléchargement allégé : 1,7 Mo de visuels de la boutique retirés de
  l'application et 2,6 Mo d'optimisation du code.

## Estado

Build assinada e verificada localmente: análise estática limpa, 51 testes a
passar e bundle de release construído.

Os gates de conteúdo e de teste em dispositivo continuam por fechar, ver
`RELEASE_CHECKLIST_1.1.0_BUILD15.md`. A decisão de promover a Produção é do
fundador, conforme `docs/agents/OPERATING_SYSTEM.md`.
