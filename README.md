<div align="center">

<img src="https://media1.tenor.com/m/STlYYOUVenUAAAAd/anime-armitage-iii-dual-matrix.gif" width="260" />

### Romero Saraiva · `ArmitageThird`

**Desenvolvedor Backend Java** — Spring Boot · Spring Data JPA · PostgreSQL · Flyway · Docker

[![VibeSurf Dev](https://img.shields.io/badge/vibesurfdev.com-0a0000?style=flat-square&logo=googlechrome&logoColor=ff4b14&labelColor=1a0500)](https://vibesurfdev.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a0000?style=flat-square&logo=linkedin&logoColor=ff4b14&labelColor=1a0500)](https://www.linkedin.com/in/romero-saraiva-ba315b345/)
[![Email](https://img.shields.io/badge/Email-0a0000?style=flat-square&logo=gmail&logoColor=ff4b14&labelColor=1a0500)](mailto:romerosaraiva4@gmail.com)

</div>

---

## `> whoami`

Backend em **Java + Spring Boot**. Construo APIs REST em arquitetura de camadas, com persistência via **Spring Data JPA** sobre **PostgreSQL** e schema versionado em **Flyway** — migrations em SQL, `ddl-auto=validate`, sem o Hibernate improvisando o banco.

Antes de virar a chave para o Java, entreguei **sites e sistemas para clientes reais** — consultórios médicos, transportadora e rede de hospedagem. O maior deles, o sistema de gestão da **[Garagem PedroRED](https://pedrored.com.br)**, está **em produção hoje**, com cliente pagante e domínio próprio. Isso continua ali embaixo: prazo, escopo e alguém do outro lado dependendo do sistema no ar.

> *"Não estou chegado — estou chegando."*

---

## `> cat pom.xml`

```xml
<project>
  <groupId>dev.vibesurf</groupId>
  <artifactId>romero-saraiva</artifactId>
  <version>2026.1.0</version>

  <properties>
    <java.version>17</java.version>
    <spring-boot.version>4.1.1</spring-boot.version>
  </properties>

  <dependencies>
    <dependency>spring-boot-starter-webmvc</dependency>
    <dependency>spring-boot-starter-data-jpa</dependency>
    <dependency>spring-boot-starter-flyway</dependency>
    <dependency>postgresql</dependency>

    <!-- em construção, chegando nesta ordem:
    <dependency>spring-boot-starter-security</dependency>
    <dependency>spring-boot-starter-test</dependency>
    <dependency>spring-ai</dependency>
    -->
  </dependencies>
</project>
```

---

## `> stack --list`

| | |
|:--|:--|
| **`backend`** | ![Java](https://img.shields.io/badge/Java%2017-0a0000?style=flat-square&logo=openjdk&logoColor=ff4b14&labelColor=1a0500) ![Spring Boot](https://img.shields.io/badge/Spring%20Boot%204-0a0000?style=flat-square&logo=springboot&logoColor=ff4b14&labelColor=1a0500) ![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-0a0000?style=flat-square&logo=spring&logoColor=ff4b14&labelColor=1a0500) ![Hibernate](https://img.shields.io/badge/Hibernate-0a0000?style=flat-square&logo=hibernate&logoColor=ff4b14&labelColor=1a0500) |
| **`dados`** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0a0000?style=flat-square&logo=postgresql&logoColor=ff4b14&labelColor=1a0500) ![Flyway](https://img.shields.io/badge/Flyway-0a0000?style=flat-square&logo=flyway&logoColor=ff4b14&labelColor=1a0500) ![SQL](https://img.shields.io/badge/SQL-0a0000?style=flat-square&logo=postgresql&logoColor=ff4b14&labelColor=1a0500) |
| **`tools`** | ![Maven](https://img.shields.io/badge/Maven-0a0000?style=flat-square&logo=apachemaven&logoColor=ff4b14&labelColor=1a0500) ![Docker](https://img.shields.io/badge/Docker%20Compose-0a0000?style=flat-square&logo=docker&logoColor=ff4b14&labelColor=1a0500) ![Git](https://img.shields.io/badge/Git-0a0000?style=flat-square&logo=git&logoColor=ff4b14&labelColor=1a0500) ![IntelliJ](https://img.shields.io/badge/IntelliJ-0a0000?style=flat-square&logo=intellijidea&logoColor=ff4b14&labelColor=1a0500) |
| **`front`** | ![TypeScript](https://img.shields.io/badge/TypeScript-0a0000?style=flat-square&logo=typescript&logoColor=ff4b14&labelColor=1a0500) ![React Router](https://img.shields.io/badge/React%20Router%207-0a0000?style=flat-square&logo=reactrouter&logoColor=ff4b14&labelColor=1a0500) ![Vite](https://img.shields.io/badge/Vite-0a0000?style=flat-square&logo=vite&logoColor=ff4b14&labelColor=1a0500) ![Astro](https://img.shields.io/badge/Astro-0a0000?style=flat-square&logo=astro&logoColor=ff4b14&labelColor=1a0500) |

---

## `> ls java/` — o que estou construindo

| Projeto | O que é | Destaque técnico |
|:--|:--|:--|
| **[Geladeira API](https://github.com/ArmitageThird/backend-geladeira-java-springboot)** | API REST de controle de alimentos | Regra de negócio no service: cadastrar item já existente **soma a quantidade** e preserva a validade mais próxima de vencer. `CHECK` no banco e `ddl-auto=validate` |
| **[API de Agendamentos](https://github.com/ArmitageThird/backend-agendamentos-java-springboot)** | API REST de agendamentos | **Docker Compose** subindo PostgreSQL 18 · duas migrations Flyway versionadas, incluindo correção de tipo de coluna |
| **[clinica-vet](https://github.com/ArmitageThird/clinica-vet)** | Laboratório de fundamentos Java e SQL | POO, collections, exceções e consultas — o alicerce, exposto de propósito |

---

## `> ls producao/` — entregue e no ar, com cliente do outro lado

> ### 🔧 [Garagem PedroRED](https://pedrored.com.br) — sistema de gestão em produção
>
> Sistema completo de gestão para oficina mecânica, com **loja integrada**, agenda e painel administrativo — rodando hoje para um cliente pagante, em domínio próprio.
>
> **Operação:** deploy em **VPS** com Docker Compose e Caddy · **PostgreSQL** com schema versionado em migrations · backend em Rust/Axum, front em TypeScript.
>
> *Repositório privado por ser sistema de cliente — o produto está no ar no link acima.*

| Cliente | Entrega | Link |
|:--|:--|:--|
| **Dra. Kerly Helena** | site institucional, **domínio próprio** | [drakerlyhelena.com.br](https://drakerlyhelena.com.br/) |
| **Motel Paraíso** | dashboard de operação conectado ao banco | [dashboard-motel-paraiso](https://dashboard-motel-paraiso.vercel.app) |
| **Dr. Roberto Teixeira** — cardiologista | site de apresentação | [ver](https://armitagethird.github.io/case-Roberto-Teixeira-Cardiologista/) |
| **Ilha Forte Transportes** | site institucional | [ver](https://armitagethird.github.io/ilhaforte/) |
| **Daniel Hakan** | site pessoal | [ver](https://armitagethird.github.io/danielhakan-1.1/) |
| **VibeSurf Dev** | marca e site próprios | [vibesurfdev.com](https://vibesurfdev.com) |

---

## `> ./agora.sh`

```
[ construindo ]  APIs REST em Java 17 + Spring Boot 4 sobre PostgreSQL
[ praticando  ]  algoritmos em Java, diariamente
[ próximo     ]  Spring Security (JWT) · JUnit 5 + Mockito · deploy em produção
[ meta        ]  sistema de gestão clínica em produção — desta vez em Java/Spring
```

<details>
<summary><b><code>> roadmap</code></b></summary>
<br/>

- [x] POO, collections e tratamento de exceções
- [x] SQL e modelagem em PostgreSQL
- [x] Spring Boot: REST controllers, injeção por construtor, arquitetura em camadas
- [x] Spring Data JPA: entidades, query methods e `Optional` como contrato
- [x] Flyway: schema versionado, `ddl-auto=validate`
- [x] Docker Compose para o ambiente de banco
- [ ] JPA: relacionamentos (`@OneToMany`, `@ManyToOne`) e estratégias de fetch
- [ ] Bean Validation na borda (`@Valid`) e tratamento global de exceção
- [ ] Testes: JUnit 5 + Mockito com cobertura real de serviço
- [ ] Spring Security: JWT, roles e filtros customizados
- [ ] Deploy de uma API em produção
- [ ] Orquestração de LLM em Java (Spring AI, RAG, agents)

</details>

---

<div align="center">
<img height="160" src="https://github-readme-stats.vercel.app/api?username=ArmitageThird&show_icons=true&rank_icon=github&hide_title=true&bg_color=0a0000&border_color=3d0000&icon_color=ff4b14&text_color=ffaaaa&cache_seconds=86400" />
</div>

---

<details>
<summary><b><code>> history | grep -i "rust"</code></b></summary>
<br/>

Antes do Java eu construí em **Rust** — `Axum`, `Tokio` e `SQLx` sobre PostgreSQL. É a stack do backend do **PedroRED**, que segue em produção, e de ferramentas próprias que continuam aqui no perfil.

Não é a direção da minha carreira: **meu foco é Java/Spring Boot.** Mas foi onde eu aprendi, na prática, o que um sistema precisa para ficar de pé — migrations versionadas, containers, proxy reverso e um cliente ligando quando cai.

*Before Java I built in Rust — Axum, Tokio and SQLx over PostgreSQL. It still powers PedroRED in production, but Java/Spring Boot is the direction.*

![Rust](https://img.shields.io/badge/Rust-0a0000?style=flat-square&logo=rust&logoColor=ff4b14&labelColor=1a0500)
![Axum](https://img.shields.io/badge/Axum-0a0000?style=flat-square&logo=rust&logoColor=ff4b14&labelColor=1a0500)
![Tokio](https://img.shields.io/badge/Tokio-0a0000?style=flat-square&logo=rust&logoColor=ff4b14&labelColor=1a0500)

</details>

<details>
<summary><b><code>> history | grep -i "servicenow"</code></b></summary>
<br/>

Estudei **ServiceNow** a sério antes de virar a chave. Continua no cinto de utilidades; só não é o que eu construo aqui.

![ServiceNow](https://img.shields.io/badge/ServiceNow-0a0000?style=flat-square&logo=servicenow&logoColor=ff4b14&labelColor=1a0500)

</details>

<details>
<summary><b><code>> sobre IA</code></b></summary>
<br/>

Uso IA na toolchain todo dia e leio cada linha antes de subir — mas **ainda não construí orquestração de LLM em Java**. Está no roadmap, com nome e ordem: Spring AI, RAG e agents, depois de Security e testes.

Prefiro dizer isso a listar um badge que eu não aguente defender numa sabatina.

</details>
