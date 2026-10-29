# Romero Saraiva

**Backend Java / Spring Boot · desenvolvimento com IA · sistemas que tiram trabalho manual de negócios reais**

São Luís, MA · remoto

[![VibeSurf Dev](https://img.shields.io/badge/VibeSurf_Dev-000000?style=flat&logo=vercel&logoColor=white)](https://vibesurfdev.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/romero-saraiva)
[![E-mail](https://img.shields.io/badge/E--mail-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:SEU_EMAIL_AQUI)

---

### `> whoami`

Construo sistemas que tiram trabalho manual das costas de quem toca um negócio, e uso **IA como parte central do meu processo de desenvolvimento**: um ambiente de Claude Code que montei ao longo do tempo, com skills de segurança, processo e front-end e regras próprias de proteção de dados.

Meu principal projeto é o **sistema de gestão da clínica da Dra. Kerly Helena**, em Java 21 + Spring Boot 4. Ele está **em produção desde outubro de 2026**, com agenda, financeiro e automações de WhatsApp que a equipe usa todo dia. Construí e mantenho o sistema, e ele foi do primeiro commit à produção em 22 dias.

Antes do Java, entreguei sites e dashboards para clientes reais pela minha agência, a [VibeSurf Dev](https://vibesurfdev.com).

---

### `> ls producao/`

#### Sistema da Clínica Dra. Kerly Helena

`em produção desde 10/2026` · `203 classes` · `2.167 testes` · `51 migrations` · `9 jobs agendados`

Sistema de gestão para uma clínica de medicina integrativa em São Luís. Três perfis (médica, assistente e administrador), cada pessoa com o próprio acesso.

**Dores que o sistema resolveu**

| Antes | Depois |
|---|---|
| As datas de consulta eram anotadas **no papel** | Agenda digital com a grade do mês e um painel do dia. A médica marca só os dias (ou turnos) em que **não** atende, e o resto fica livre |
| Lembrar a paciente não bastava: a médica não tinha como saber **quem ia de fato** | Na véspera e 2h antes, a paciente recebe uma **enquete** ("Confirmo" / "Preciso remarcar"). A resposta vira aviso para a equipe e aparece no painel do dia: confirmadas, aguardando, sem resposta, pediu remarcação |
| As **avaliações no Google** são essenciais para a clínica, mas o link sempre ficava para depois | Depois de cada consulta, o sistema envia sozinho a mensagem de agradecimento com o link de avaliação |
| A médica respondia o tempo todo a mesma pergunta: **onde fica a clínica** e **quando é a minha consulta**. Em 17 dias, 13 pacientes mandaram 28 mensagens assim para o número de avisos | Quando a paciente escreve, o sistema identifica o assunto e responde, ou manda um **menu em enquete** para ela escolher. Escolheu "localização", recebe o pino da clínica no mapa; escolheu "minha consulta", recebe a data |
| Risco de duas pacientes no mesmo horário | O **próprio banco** recusa horário sobreposto, mesmo com duas pessoas marcando ao mesmo tempo |
| A receita só entrava no financeiro se alguém lembrasse de clicar, e o valor era digitado à mão | A receita é lançada sozinha quando a consulta termina, com o valor do catálogo de serviços congelado na consulta |
| Senha compartilhada, e cancelar ou mudar valor não deixava rastro | Login por código no e-mail, acesso individual e página de atividade ("quem fez o quê") |

**Automações no WhatsApp** (Evolution API)
- **Paciente:** confirmação 5 min depois de marcar, lembrete na véspera (seguido do pino da clínica), lembrete 2h antes e pós-consulta com link de avaliação no Google. Nada sai entre 22h e 7h.
- **Equipe:** 13 tipos de aviso, ligados ou desligados por pessoa, mais um resumo da agenda às 7h.
- **Também:** despesas fixas lançadas todo mês, painel financeiro anual e um módulo de aluguéis com cobrança mensal, multa e juros e recibo em PDF enviado pelo WhatsApp.

<details>
<summary><b>Decisões técnicas</b></summary>

- **Double booking barrado no Postgres, não no Java:** coluna `tstzrange` com `EXCLUDE USING gist`. Um `if (existeConflito())` em Java sofre condição de corrida.
- **Outbox no banco:** marcar consulta só grava a mensagem numa fila, e um job envia ao WhatsApp. Se a Evolution API estiver lenta, a consulta não trava nem se perde.
- **Uma transação por item nos jobs** (`TransactionTemplate`): `@Transactional` em chamada interna não passa pelo proxy do Spring. Isso já causou reenvio de mensagem a cada minuto em produção, até eu corrigir.
- **Idempotência com índice único parcial + `ON CONFLICT DO NOTHING`:** no Postgres, capturar a violação não basta, porque a transação inteira já fica abortada.
- **Webhook fail-closed:** token comparado em tempo constante, corpo limitado a 1 MB, filtro por instância e segredos higienizados antes de gravar o evento.
- **Login sem senha:** código de 5 dígitos guardado só como hash BCrypt, limite de tentativas por IP + e-mail e tempo de resposta igual para e-mail inexistente.
- **Agenda esparsa:** só os dias bloqueados viram linha no banco; o resto é livre por padrão.
- **Respostas automáticas sem LLM:** classificador por palavras com tolerância a erro de digitação (Damerau-Levenshtein), restrita aos assuntos em que ela não gera ambiguidade ("pegar" não pode virar "pagar"). O texto da paciente não sai do servidor.
- **JVM enxuta** para rodar numa VPS de 4 GB junto com o Postgres e a Evolution API.
- **Testes contra Postgres real**, sem H2 (o H2 não tem `tstzrange` nem `EXCLUDE`), incluindo testes de concorrência com threads.

</details>

**O que a produção me ensinou**
- Uma consulta foi marcada para a pessoa errada e cancelada 15 segundos depois, mas a confirmação já tinha saído. Agora a confirmação espera 5 minutos, e cancelar nesse prazo impede o envio.
- O número de avisos levou um bloqueio de 1 dia do WhatsApp, e decidi parar com o envio em massa. Sistema bom também é saber o que desligar.
- A VPS ficou 4 horas fora do ar depois de uma manutenção do provedor. Corrigi a causa e coloquei backup automático para o Google Drive no mesmo dia.

**Resultados**
<!-- TODO: preencher com os números das queries de produção (consultas/mês, % de confirmação pela paciente, dúvidas respondidas) -->

`Java 21` · `Spring Boot 4` · `Spring Security` · `Spring Data JPA` · `Thymeleaf` · `PostgreSQL 17` · `Flyway` · `Docker Compose` · `Caddy` · `Evolution API` · `VPS Linux`

> Código privado (envolve dados de pacientes). Mostro a arquitetura e o código numa conversa.

#### Clientes VibeSurf Dev
- **Dra. Kerly Helena** · site institucional com domínio próprio (além do sistema acima)
- **Motel Paraíso** · dashboard conectado ao banco
- **Dr. Roberto Teixeira** · site de apresentação
- **Ilha Forte Transportes** · site institucional
- **Daniel Hakan** · site pessoal
- **VibeSurf Dev** · marca e site próprios

---

### `> cat como-eu-trabalho-com-ia.md`

O **Claude Code** é minha ferramenta principal de desenvolvimento. Não fico só pedindo código: montei e mantenho um ambiente para a IA trabalhar do jeito certo em cada projeto.

- **Segurança:** skills de auditoria (`vibe-security`, `owasp-security`, `security-best-practices`) e, por cima delas, **regras minhas** no `CLAUDE.md`: controle de acesso no servidor e anti-IDOR, segredo só em variável de ambiente, nunca logar senha, token ou dado pessoal. Nenhuma dessas skills trata LGPD nem dados de saúde, então essa camada eu escrevi no próprio projeto da clínica: não logar telefone, expurgo de dados antigos e a IA proibida de ler o `.env`.
- **Processo:** `superpowers` (TDD, debugging sistemático, planos, code review) e diretrizes contra os erros comuns de LLM escrevendo código.
- **Front-end:** skills de design (`design-taste-frontend`, `high-end-visual-design`, `impeccable`) e uma regra minha de como combiná-las: uma de descoberta, duas de execução, no máximo um estilo e uma de revisão.
- **Contexto de projeto versionado:** `CLAUDE.md` com as armadilhas já encontradas no sistema e specs por funcionalidade em `docs/specs/`, para a IA não repetir erro e cada decisão ficar rastreável.
- **Vários agentes em paralelo** para tarefas grandes. Exemplo: cinco agentes levantaram a documentação deste sistema lendo o código, e eu conferi as afirmações que mais pesavam.
- **Ferramenta própria:** o [ClaudeCodeHUD](https://github.com/armitagethird/ClaudeCodeHUD), um HUD em Rust que uso todo dia como status line do Claude Code.
- **Já integrei IA em produto:** o **Pronto Vet**, um programa que consome uma API de IA, feito com o Claude Code.
- **Saber quando não usar IA também conta:** no sistema da clínica, as respostas automáticas às pacientes não usam LLM, para o texto delas não sair do servidor.

Não sou especialista em machine learning. Sou um dev de back-end que usa IA todos os dias e já colocou isso para rodar em projeto real.

---

### `> stack --list`

**Backend**
![Java](https://img.shields.io/badge/Java_21-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat&logo=springsecurity&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=flat&logo=hibernate&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat&logo=thymeleaf&logoColor=white)

**Dados**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Flyway](https://img.shields.io/badge/Flyway-CC0200?style=flat&logo=flyway&logoColor=white)

**IA**
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)

**Infra e ferramentas**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat&logo=caddy&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=flat&logo=apachemaven&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ_IDEA-000000?style=flat&logo=intellijidea&logoColor=white)

**Front**
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat&logo=reactrouter&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Astro](https://img.shields.io/badge/Astro-BC52EE?style=flat&logo=astro&logoColor=white)

---

### `> ls java/`

| Projeto | O que mostra |
|---|---|
| [backend-agendamentos-java-springboot](https://github.com/armitagethird/backend-agendamentos-java-springboot) | API REST de agendamentos com bloqueio de horário sobreposto, ciclo de status (AGENDADO → CONCLUÍDO / CANCELADO), PostgreSQL 18 via Docker Compose e migrations Flyway |
| [backend-geladeira-java-springboot](https://github.com/armitagethird/backend-geladeira-java-springboot) | CRUD bem feito: soma a quantidade de itens repetidos, mantém a validade mais próxima e garante a regra com `CHECK` no banco |

---

### `> ls rust/`

Ferramentas que fiz para o meu próprio dia a dia:

| Projeto | O que é |
|---|---|
| [ClaudeCodeHUD](https://github.com/armitagethird/ClaudeCodeHUD) | HUD para o Claude Code CLI |
| [NoProcrastination](https://github.com/armitagethird/NoProcrastination) | App para fazer o que precisa ser feito |
| [acentorust](https://github.com/armitagethird/acentorust) | Clone minimalista do Acento Rápido do PowerToys |

---

### `> ./agora.sh`

- [x] Java + Spring Boot + JPA + PostgreSQL + Flyway
- [x] Sistema em produção com cliente ativo (Docker Compose, Caddy, VPS)
- [x] Spring Security: perfis de acesso, login por código, CSRF, limite de tentativas
- [x] Testes com JUnit 5 e MockMvc contra Postgres real
- [ ] CI/CD com GitHub Actions
- [ ] Orquestração de LLM em Java (Spring AI, RAG, agents)
- [ ] ServiceNow: retomando os estudos (Now Pro / CSA)
