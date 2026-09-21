# Política de Privacidade, STP Quiz

**Última atualização:** 20 de setembro de 2026
**Responsável pelo tratamento:** Vagner Bom Jesus
**Contacto:** vagneripg@gmail.com

> Este documento é a Política de Privacidade pública da aplicação móvel
> **STP Quiz** (identificador `st.stpquiz.bjtech`). O URL público desta
> página pode ser usado no campo "Política de Privacidade" da Google
> Play Console.
>
> URL público: `https://vagnerbomjesus.github.io/stp.quiz/privacy.html`

---

## 1. Introdução

A presente Política de Privacidade descreve a forma como a aplicação
**STP Quiz** trata informação relacionada com a sua utilização. O objetivo
é dar transparência ao utilizador sobre o que é (ou não é) recolhido, com
que fundamento e durante quanto tempo.

## 2. Princípio da minimização

A STP Quiz foi desenhada de raiz para tratar o mínimo de informação
indispensável ao seu funcionamento. **O progresso dos quizzes e as
preferências ficam apenas no dispositivo.** Desde a versão 1.2.0, um
conjunto pequeno e delimitado de dados (um identificador anónimo, as
respostas do início e, se assim o quiser, o endereço de email da conta
Google) é guardado num servidor próprio, para que possa recuperar o seu
perfil se mudar de telemóvel. Nada mais sai do dispositivo.

## 3. Dados tratados

A aplicação armazena localmente, no próprio dispositivo, os seguintes
dados:

- **Progresso dos quizzes**: melhor resultado por tema e por nível;
- **Estatísticas de jogo**: partidas concluídas, pontos, precisão e
  histórico recente;
- **Preferências**: tema (claro/escuro/sistema), idioma
  (PT/EN/FR/sistema), cores personalizadas (primária/secundária), filtro
  de nível, estado do onboarding e ativação das notificações.

Estes dados são guardados através do mecanismo `SharedPreferences` do
sistema operativo e **nunca são transmitidos para o exterior**. A
aplicação não pede localização, contactos nem ficheiros.

## 3-A. Dados tratados no servidor

Desde a versão 1.2.0 a aplicação comunica com um servidor próprio,
exclusivamente para os seguintes dados:

- **Identificador anónimo**: um código gerado pela própria aplicação na
  primeira utilização. Não é o identificador do aparelho nem está ligado à
  sua identidade; reinstalar a aplicação gera outro;
- **Respostas do início**: o nome que quiser dar (opcional), a razão por
  que quer aprender, quanto diz saber sobre o país e a meta diária;
- **Endereço de email**: apenas se escolher associar uma conta Google, e
  apenas para o reconhecer quando entrar noutro telemóvel. Quem verifica a
  identidade é a Google; a aplicação nunca vê nem guarda a sua
  palavra-passe.

O progresso dos quizzes, o histórico, a sequência de dias e as
estatísticas de jogo **não** são enviados: continuam apenas no
dispositivo. Os dados viajam sempre por ligação encriptada (HTTPS) e ficam
alojados na Vercel, com as funções fixadas na região de Paris, e na
MongoDB Atlas, subcontratantes que os tratam por nossa conta e segundo as
nossas instruções. As estatísticas públicas da aplicação nunca incluem
nomes e só mostram a distribuição das respostas a partir de dez
respondentes.

## 4. Finalidades

Os dados acima são tratados apenas para:

- permitir ao utilizador continuar os quizzes onde os deixou;
- apresentar o progresso global, as estatísticas e a revisão de respostas;
- restaurar as preferências escolhidas pelo utilizador.

## 5. Base legal

O armazenamento local descrito é indispensável ao funcionamento da
aplicação solicitada pelo utilizador (execução do serviço, artigo 6.º,
n.º 1, alínea b), do RGPD) e assenta no **interesse legítimo** de
proporcionar uma experiência funcional e contínua (alínea f)). Como nenhum
dado chega ao responsável pelo tratamento, não é pedido consentimento nem
existe qualquer transmissão. O utilizador pode eliminar todos os dados a
qualquer momento em **Definições > Limpar Cache** ou desinstalando a
aplicação. As notificações só são ativadas mediante permissão expressa
concedida ao sistema operativo, revogável em Definições.

## 6. Conservação dos dados

Os dados guardados no dispositivo são mantidos enquanto a aplicação
estiver instalada, e a eliminação é imediata quando o utilizador toca em
"Limpar Cache" ou desinstala a aplicação. Os dados no servidor (secção
3-A) são conservados enquanto a conta existir, e apagados quando o
utilizador a apagar.

## 6-A. Apagar a conta e os dados

Em **Definições > Apagar conta e dados**, a aplicação elimina do servidor
a conta e as respostas do início, desassocia a conta Google e limpa o
perfil do telemóvel. A eliminação é definitiva e **não existem cópias de
segurança** de onde recuperar os dados.

Se já não tiver a aplicação instalada, pode pedir o mesmo em
`https://vagnerbomjesus.github.io/stp.quiz/delete-account.html` ou por
email para `vagneripg@gmail.com`, a partir do endereço da conta Google que
associou; respondemos no prazo máximo de 30 dias.

## 7. Não partilha com terceiros

A STP Quiz **não vende, não aluga e não disponibiliza informação a
terceiros**, incluindo parceiros publicitários, ferramentas de análise
ou plataformas de marketing. A aplicação **não inclui redes de
publicidade nem rastreadores comportamentais**.

## 8. Notificações e permissões do dispositivo

A funcionalidade **Curiosidade do Dia** pode enviar uma notificação local
diária às 9h (hora local). As notificações são geradas e agendadas no
próprio dispositivo, com conteúdo incorporado na aplicação, não existe
qualquer servidor de notificações. Para tal, no Android 13 ou superior a
aplicação solicita a permissão `POST_NOTIFICATIONS` e utiliza
`RECEIVE_BOOT_COMPLETED` apenas para reagendar a notificação após um
reinício. Podem ser desativadas em **Definições > Notificações**.

Fora isso, a aplicação **não solicita permissões sensíveis** (câmara,
microfone, localização, contactos, calendário, ficheiros do utilizador,
etc.). A utilização da app não requer ligação à internet.

## 8-A. Serviços de terceiros

A aplicação não integra SDKs de publicidade, analytics ou redes sociais.
Existem três interações com serviços do sistema ou da Google, todas
iniciadas pelo utilizador:

- o pedido opcional de avaliação através da API **Google Play In-App
  Review**;
- a partilha de curiosidades ou resultados através da **folha de partilha
  do sistema operativo**, em que o conteúdo é entregue à aplicação que o
  utilizador escolher;
- o **Sign in with Google**, se escolher associar uma conta: nesse caso é
  a Google que verifica a identidade e devolve à aplicação apenas a
  confirmação de onde se extrai o email (secção 3-A).

As interações com serviços da Google estão sujeitas à [Política de
Privacidade da Google](https://policies.google.com/privacy).

## 8-B. Este website

O site `vagnerbomjesus.github.io/stp.quiz` é uma página estática alojada no
GitHub Pages. Não utiliza cookies, analytics, publicidade ou formulários.
As fontes e os ícones são servidos a partir do próprio site, sem pedidos a
terceiros. A única informação guardada no browser é a língua escolhida
(PT/EN/FR), em `localStorage`, estritamente necessária para manter a
preferência entre páginas. O alojamento é prestado pela GitHub, Inc., que
pode registar dados técnicos de acesso (como o endereço IP) para segurança
e operação do serviço, nos termos da sua declaração de privacidade. A STP
Quiz não tem acesso a esses registos.

## 9. Segurança

Os dados encontram-se protegidos pelos mecanismos de **armazenamento
isolado do sistema operativo** (sandbox da aplicação). Recomenda-se ao
utilizador a adoção de práticas adequadas de segurança no dispositivo,
como o uso de bloqueio por código ou biométrico.

## 10. Transferências internacionais

Os dados guardados no dispositivo não são transferidos para lado nenhum.
Os dados descritos na secção 3-A são tratados por subcontratantes: a API
corre na Vercel, com as funções fixadas na região de Paris (União
Europeia), e a base de dados está alojada na MongoDB Atlas. Quando o
tratamento por estes fornecedores envolver países terceiros, é feito ao
abrigo dos mecanismos previstos no capítulo V do RGPD, nomeadamente as
cláusulas contratuais-tipo que constam dos respetivos contratos.

## 11. Direitos do titular

Em conformidade com a **Lei n.º 3/2016, de 18 de fevereiro** (República
Democrática de São Tomé e Príncipe) e o **Regulamento (UE) 2016/679
(RGPD)**, o utilizador tem direito a:

- informação sobre os dados tratados;
- acesso e cópia dos dados;
- rectificação de informação inexacta;
- apagamento ("direito ao esquecimento");
- limitação ou oposição ao tratamento;
- portabilidade;
- retirar o consentimento, sem efeito retroactivo;
- apresentar reclamação à autoridade de controlo competente.

Para exercer estes direitos: **"Limpar Cache"** nas Definições apaga o
progresso guardado no dispositivo; **"Apagar conta e dados"** elimina a
conta e as respostas do servidor (secção 6-A). Para qualquer outro
pedido, incluindo acesso e portabilidade, contacte `vagneripg@gmail.com`.

## 12. Menores

A aplicação destina-se a um **público geral**. Caso seja utilizada por
menores, recomenda-se a supervisão do encarregado de educação. Como não
são recolhidos dados pessoais identificáveis, não é solicitado
consentimento parental específico.

## 13. Alterações à Política

Esta Política pode ser actualizada para reflectir alterações legais ou
funcionais. A versão em vigor é a apresentada nesta página, identificada
pela data de "última actualização" no topo.

## 14. Contacto

Para qualquer questão relacionada com privacidade ou protecção de dados:

**Email:** vagneripg@gmail.com
**Repositório:** https://github.com/VagnerBomJesus/stp.quiz
