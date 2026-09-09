# Revisão de segurança e privacidade (RGPD) - STP Quiz

**Âmbito:** site `vagnerbomjesus.github.io/stp.quiz` (este repositório) e aplicação Android STP Quiz (`st.stpquiz.bjtech`, repositório `quizstp`, versão local 1.1.0+15).
**Data:** 9 de setembro de 2026. **Autor da revisão:** análise técnica automatizada com base no código; não constitui parecer jurídico.

## 1. Resumo

A STP Quiz está numa posição muito favorável face ao RGPD porque **não trata dados pessoais fora do dispositivo do utilizador**: não há contas, servidores próprios, analytics, publicidade ou SDKs de terceiros. O ponto fraco que existia estava do lado do **site**, que carregava fontes e ícones a partir do Google Fonts (transmissão do endereço IP do visitante para a Google a cada visita, sem consentimento). Essa dependência foi removida nesta revisão, e a base legal invocada na política (antes "consentimento implícito") foi corrigida. O que resta são pequenas melhorias de documentação e duas verificações na configuração do GitHub Pages.

| Área | Estado | Observação |
|---|---|---|
| App: dados pessoais transmitidos | Conforme | Nenhum. Tudo em `SharedPreferences` local. |
| App: permissões | Conforme | `POST_NOTIFICATIONS`, `RECEIVE_BOOT_COMPLETED`, `VIBRATE`. Todas justificadas pela Curiosidade do Dia; sem alarmes exatos (`inexactAllowWhileIdle`). |
| App: terceiros | Atenção (documentado) | Google Play In-App Review e folha de partilha do sistema, ambos iniciados pelo utilizador. Agora descritos na política. |
| App: menores | Conforme | Sem recolha de dados, sem perfis; PEGI 3. Não é necessário consentimento parental (art. 8.º RGPD não se aplica sem tratamento). |
| App: Declaração de segurança de dados (Play Console) | Conforme | "Sem dados recolhidos, sem partilha" coincide com o código. |
| Site: cookies | Conforme | Zero cookies. `localStorage` só para a língua (estritamente necessário, isento de consentimento ao abrigo do art. 5.º, n.º 3 da Diretiva ePrivacy). |
| Site: pedidos a terceiros | Corrigido | Google Fonts e Material Symbols substituídos por ficheiros locais (`docs/fonts/`) e SVG inline. Zero pedidos externos confirmados em teste. |
| Site: alojamento | Atenção (documentado) | GitHub Pages (GitHub, Inc., EUA) pode registar IPs. Coberto pelo Data Privacy Framework UE-EUA e pelas cláusulas da GitHub; a política passou a informar o visitante. |
| Site: HTTPS | Verificar | Ativar "Enforce HTTPS" em Settings > Pages (GitHub Pages redireciona HTTP para HTTPS quando ativo). |
| Política: base legal | Corrigido | "Consentimento implícito" substituído por execução do serviço (art. 6.º, n.º 1, b)) e interesse legítimo (f)). Ver secção 4. |
| Política: direitos, prazos, contacto | Conforme | Secções 13 a 16 da `privacy.html`. |
| Segurança: divulgação responsável | Adicionado | `/.well-known/security.txt` (RFC 9116). |
| Segurança: segredos no repositório | Conforme | Nenhum segredo neste repositório; o repositório da app removeu o keystore do histórico em 2026-09-03 (`SECURITY_NOTE_KEYSTORE_2026-09-03.md`). |

## 2. Fluxos de dados verificados no código da app

Dependências relevantes em `pubspec.yaml`: `shared_preferences`, `share_plus`, `in_app_review`, `flutter_local_notifications`, `timezone`, `package_info_plus`. Não existem `http`, `dio`, `firebase_*`, `google_mobile_ads` ou SDKs de analytics.

- **Progresso e estatísticas** (`SharedPreferences`): melhor resultado por tema e nível, partidas, pontos, precisão, histórico recente. Ficam no sandbox da app; apagáveis em Definições > Limpar Cache ou por desinstalação.
- **Preferências**: tema, idioma, cores, filtro de nível, onboarding, toggle de notificações.
- **Notificações locais**: 15 curiosidades incorporadas, agendadas no dispositivo com `flutter_local_notifications`; sem servidor push, sem tokens de dispositivo.
- **In-App Review**: a API da Google Play decide se mostra o diálogo; a Google trata esses dados como operadora da loja, ao abrigo da sua própria política. A app não recebe nem guarda nada.
- **Partilha**: o texto é entregue ao seletor do sistema; o destinatário é escolhido pelo utilizador.
- **Links externos** (fontes das perguntas: UNESCO, FAO, BCSTP, etc.): abertos no browser do sistema; o site de destino vê o pedido, a app não.

Conclusão: para efeitos do RGPD, o responsável (autor) não recebe dados pessoais. O tratamento existente é realizado pelo próprio titular no seu dispositivo, o que cai fora do âmbito material do Regulamento (art. 2.º) na perspetiva do responsável. Ainda assim é boa prática manter a política, como está feito.

## 3. Verificações no site

Testes executados em 2026-09-09 sobre a versão publicada nesta revisão (Chromium headless, desktop 1440 px e mobile 390 px):

- Pedidos de rede para domínios externos ao carregar `index.html`, `privacy.html`, `terms.html`, `support.html`: **0**.
- Cookies definidos: **0**. `localStorage`: chave `stpquiz.lang` apenas.
- Scripts de terceiros: **0**. Todo o JavaScript é inline e sem dependências.
- Formulários: **0**. O contacto é por `mailto:`.
- Cabeçalhos de segurança: GitHub Pages não permite configurar `Content-Security-Policy`, `X-Frame-Options` ou HSTS por site. Mitigação possível: `<meta http-equiv="Content-Security-Policy">` (ver recomendações).

## 4. Pontos de atenção e recomendações

1. **Base legal na política (secção 7).** O texto anterior invocava "consentimento implícito", que não é uma base válida no RGPD (o consentimento tem de ser explícito e inequívoco, art. 4.º, n.º 11, e art. 7.º). **Corrigido nesta revisão** em `privacy.html` (PT/EN/FR) e em `PRIVACY.md`: execução do serviço (art. 6.º, n.º 1, alínea b)) e interesse legítimo (alínea f)), com a nota de que nenhum dado chega ao responsável. A mesma frase deve ser refletida no texto da política mostrado dentro da app, se existir.
2. **Ativar "Enforce HTTPS"** no GitHub Pages, se ainda não estiver.
3. **CSP por meta tag** (opcional, baixo risco): `default-src 'self'; img-src 'self' data:; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline'; connect-src 'none'; frame-ancestors 'none'`. Como o CSS e JS são inline, exige `'unsafe-inline'` ou migração para ficheiros externos com hashes.
4. **Registo de tratamento (art. 30.º)**: não obrigatório (menos de 250 trabalhadores, tratamento ocasional, sem categorias especiais). Não é necessário DPO nem AIPD.
5. **Dados de contacto de suporte**: os emails recebidos em `vagneripg@gmail.com` são dados pessoais tratados pela Google (Gmail) em nome do autor. A `support.html` já indica confidencialidade e não partilha; sugere-se acrescentar o prazo de conservação dos emails (por exemplo, "até 12 meses após a resolução do pedido").
6. **Transferências internacionais**: a política afirma que não ocorrem. É verdade para a app; para o site, o alojamento na GitHub (EUA) foi acrescentado na secção "Este website". Manter coerência se o alojamento mudar.
7. **Versões**: a página inicial descreve a 1.1.0. Se a versão em produção continuar a ser a 1.0.11, considerar rotular a secção "Novidades" como "Em breve" até à publicação, para não induzir em erro.
8. **security.txt**: o campo `Expires` está definido para 2027-09-30; renovar anualmente.

## 5. Ficheiros de descoberta criados

| Ficheiro | Finalidade |
|---|---|
| `docs/robots.txt` | Permite indexação; aponta para o sitemap. |
| `docs/sitemap.xml` | 4 páginas + `llms.txt`, com `hreflang` pt/en/fr. |
| `docs/llms.txt` | Resumo factual do produto para assistentes de IA (formato llmstxt.org). |
| `docs/.well-known/security.txt` | Contacto para reportar vulnerabilidades (RFC 9116). |
| `docs/humans.txt` | Créditos e tecnologia. |
| `docs/site.webmanifest` | Nome, ícones, cor de tema e ligação à app na Play Store. |
| `docs/.nojekyll` | Garante que o GitHub Pages serve `.well-known/` e ficheiros com ponto inicial. |
| JSON-LD em `index.html` | `MobileApplication`, `Person`, `WebSite` e `FAQPage` (schema.org). |

Recomendação: submeter o `sitemap.xml` no Google Search Console e no Bing Webmaster Tools depois de publicar, e validar o JSON-LD em https://validator.schema.org/.
