# Release Notes — STP Quiz v1.0.9 (build 10)

Salto cumulativo desde a v1.0.2 — várias funcionalidades novas e
refactor estrutural. Cola um dos blocos abaixo no campo "Novidades
desta versão" da Play Console.

---

## 🇵🇹 Português (pt-PT)

> 472 caracteres

```
Novidades:

• Curiosidade do Dia na Home — uma nova curiosidade sobre STP todos os dias.
• Notificação diária às 9h (configurável em Definições > Notificações).
• Cada categoria tem perguntas distintas por nível (História coberta nos 4).
• Níveis com mecânicas próprias — embaralhar, timer, vidas, dica 50/50.
• Pontuação com multiplicador (×1 a ×4) no ecrã de resultado.
• Melhorias responsivas nos ecrãs Acertou/Errou e Resultado.

Obrigado!
```

---

## 🇬🇧 English (en-US)

> 463 characters

```
What's new:

• Fact of the Day on Home — a new STP fact every day.
• Daily notification at 9 a.m. (toggle under Settings > Notifications).
• Each category now has different questions per level (History covered on all 4).
• Levels with own mechanics — shuffle, timer, lives, 50/50 hint.
• Score with multiplier (×1 to ×4) on the result screen.
• Responsive tweaks on Correct/Wrong and Result screens.

Thanks!
```

---

## 🇫🇷 Français (fr-FR)

> 488 caracteres

```
Nouveautés :

• Curiosité du jour sur l'Accueil — une nouvelle info sur STP chaque jour.
• Notification quotidienne à 9 h (activable dans Paramètres > Notifications).
• Chaque catégorie a des questions distinctes par niveau (Histoire couverte sur les 4).
• Niveaux avec mécaniques propres — mélange, minuteur, vies, indice 50/50.
• Score avec multiplicateur (×1 à ×4) à l'écran de résultat.
• Améliorations responsives.

Merci !
```

---

## Changelog técnico cumulativo (v1.0.2 → v1.0.9)

### v1.0.3 — Modo Aleatório
- Cartão "Quiz Aleatório" na Home (depois substituído).

### v1.0.4 — Mecânicas por nível (Fase 1)
- `LevelConfig` por nível: embaralhar perguntas, embaralhar respostas, multiplicador de pontos (×1 a ×4).
- `ChallengePage` aplica config no `initState`.
- `_PointsCard` no ecrã de Resultado.

### v1.0.5 — Mecânicas por nível (Fase 2)
- Timer (Difícil 20s, Perito 10s) com anel circular.
- Vidas (Difícil 3, Perito 1) com corações.
- Dica 50/50 no nível Fácil (esconde 2 respostas erradas).
- Resultado redirecciona cedo se as vidas acabarem.

### v1.0.6 — Perguntas por nível + Home renovada
- `CategoryQuiz` com `Map<Level, List<QuestionModel>>`.
- 1 card por categoria, chip define a variante de nível.
- Categorias sem conteúdo para o nível aparecem como "Em breve".
- **História** com os 4 níveis cobertos (15 perguntas novas).
- i18n reorganizado: `quiz.<cat>.<nivel>.q<N>.*`.

### v1.0.7 — Curiosidade do Dia
- Cartão "Curiosidade do Dia" substitui o "Quiz Aleatório" na Home.
- 15 curiosidades rotativas com seed = dia do ano.
- Bottom sheet com partilha.
- `flutter_local_notifications` + `timezone` agendam 30 dias.
- `core library desugaring` activado no `build.gradle.kts`.

### v1.0.8 — Master + sub-toggle de notificações
- Estrutura provisória com master + sub-toggle.

### v1.0.9 — Toggle único de notificações
- Volta à simplicidade: **um toggle só** "Notificações da aplicação · Activa ou desactiva".

### Faixa de testers
- Adiciona o teu email + amigos como testers em "Testes internos" antes de instalar.
