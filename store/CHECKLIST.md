# Checklist — Publicação STP Quiz na Google Play (teste interno)

Lista do que precisa de existir antes de abrirmos o Play Console.

---

## 1. Build assinado da app

> **O que tu fazes na tua máquina**

- [ ] **Gerar keystore** (uma vez, guardar password e .jks em sítio seguro)

  ```powershell
  cd C:\Users\vagne\Documents\Github\stpquiz\quizstp\android
  keytool -genkey -v -keystore stpquiz-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias stpquiz
  ```

- [ ] **Criar** `quizstp\android\key.properties`:

  ```properties
  storePassword=...
  keyPassword=...
  keyAlias=stpquiz
  storeFile=stpquiz-release-key.jks
  ```

- [ ] **Construir AAB**:

  ```powershell
  cd C:\Users\vagne\Documents\Github\stpquiz\quizstp
  flutter clean
  flutter pub get
  flutter build appbundle --release
  ```

- [ ] Ficheiro final em:
  `C:\Users\vagne\Documents\Github\stpquiz\quizstp\build\app\outputs\bundle\release\app-release.aab`

---

## 2. Assets gráficos exigidos pela Play Store

> A loja recusa o envio se algum destes faltar

| Asset                  | Dimensões      | Formato      | Estado |
| ---------------------- | -------------- | ------------ | ------ |
| Ícone da app           | 512 × 512      | PNG, 32-bit  | ⚠️ a partir de `assets/images/logo.png` |
| Feature graphic        | 1024 × 500     | PNG/JPG      | ❌ falta criar |
| Screenshots telefone   | mín. 2, máx. 8 · 1080 × 1920 (ou similar 9:16) | PNG/JPG | ❌ falta capturar |
| Screenshots tablet 7"  | opcional       | PNG/JPG      | — |
| Screenshots tablet 10" | opcional       | PNG/JPG      | — |

**Como capturar screenshots para a loja**:

```powershell
# Lançar emulador Pixel 6 / 7 (ou usar device físico)
flutter run --release
# Dentro da app, em cada ecrã, fazer:
# Android Studio → View → Tool Windows → Logcat → câmara (Screenshot)
```

Ecrãs sugeridos a capturar (8 no total):
1. Splash com logo
2. Home (modo escuro com header gradiente)
3. Lista de quizzes filtrada por nível
4. Pergunta a meio de um quiz
5. Ecrã de feedback "Acertou!"
6. Ecrã de resultado com troféu
7. Página "Factos e Números"
8. Definições + Cores Personalizadas aberto

---

## 3. Política de Privacidade pública

- [x] **PRIVACY.md** criado na raiz do repositório
- [ ] **Repositório no GitHub público** (se for privado, o URL devolve 404)
- [ ] URL final: `https://github.com/VagnerBomJesus/stpquiz/blob/main/PRIVACY.md`

---

## 4. Descrições da loja

- [x] `store/listing_pt.md` — Português (idioma padrão)
- [x] `store/listing_en.md` — Inglês
- [x] `store/listing_fr.md` — Francês

---

## 5. Formulários internos da Play Console

> Tens de preencher **todos** antes da Play Store deixar publicar

| Secção                                | O que responder                                |
| ------------------------------------- | ---------------------------------------------- |
| Acesso à aplicação                    | Toda a funcionalidade é gratuita e sem login   |
| Anúncios                              | Não contém anúncios                            |
| Classificação de conteúdo             | Preencher questionário (educacional, sem violência/sexo/álcool/drogas/apostas) → IARC categoria provável **3+** ou **Todos** |
| Público-alvo e conteúdo               | Idade 13+ (escolha conservadora)               |
| Aplicação de notícias                 | Não                                            |
| Política de privacidade               | URL público do PRIVACY.md no GitHub            |
| Segurança dos dados                   | Não recolhe dados pessoais; tudo em local      |
| Compromissos governamentais           | Não aplicável                                  |
| País/região                           | Disponibilizar em todos os países              |

---

## 6. Teste interno (canal "Internal testing")

- [ ] **Lista de testers** — emails Google (até 100)
  - vagneripg@gmail.com (próprio)
  - amigos / família que ajudem a validar
- [ ] **Notas da versão**:
  ```
  v1.0.0 — primeira versão para testes internos.
  - Quiz educativo sobre São Tomé e Príncipe
  - 6 categorias com 4 níveis de dificuldade
  - Idiomas: PT, EN, FR (segue sistema)
  - Tema claro/escuro/sistema e cores personalizadas
  - Página de Factos e Números, FAQ e Sobre
  ```

---

## 7. Após publicação

- [ ] Receber **opt-in URL** da Play Console
- [ ] Enviar aos testers (eles aceitam → app aparece na Play Store deles)
- [ ] Recolher feedback
- [ ] Próximas versões: subir `version` em `pubspec.yaml` (ex.: `1.0.1+2`) →
      novo `flutter build appbundle` → upload na mesma faixa de testes

---

## Faltas críticas neste momento

🟥 **AAB ainda não construído** — precisas correr os comandos do ponto 1
🟥 **Feature graphic 1024×500** — falta criar
🟥 **Screenshots** — faltam capturar
🟨 **Repo GitHub público** — confirma que `VagnerBomJesus/stpquiz` está público

Quando tiveres o AAB e os screenshots, **diz-me** e eu abro a Play Console
contigo para fazer upload e preencher os formulários.
