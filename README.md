<div align="center">

<!-- ═══════════════════════ HEADER ═══════════════════════ -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,40:1a0500,70:2b0a00,100:0a0000&height=210&section=header&text=ArmitageThird&fontSize=54&fontColor=ff4b14&fontAlignY=36&desc=Romero%20Saraiva%20%C2%B7%20Rust%20Developer%20%5Bin%20progress%5D&descSize=17&descAlignY=58&descColor=ff2222&animation=fadeIn" />

<!-- ═══════════════════════ GIF ARMITAGE III ═══════════════════════ -->
<img src="https://media1.tenor.com/m/STlYYOUVenUAAAAd/anime-armitage-iii-dual-matrix.gif" width="340" />

<br/>

<!-- ═══════════════════════ TYPING ═══════════════════════ -->
<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&weight=700&size=24&duration=3200&pause=900&color=FF4B14&center=true&vCenter=true&width=700&lines=_+Rust+Developer+%5Bloading...%5D%3B;%3E+cargo+build+--release;%24+Axum+%7C+Tokio+%7C+SQLx+%7C+Postgres;%2F%2F+oxidizing+the+web%2C+one+crate+at+a+time" alt="Typing SVG" />
</a>

<br/><br/>

<!-- ═══════════════════════ LINKS ═══════════════════════ -->
[![VibeSurf Dev](https://img.shields.io/badge/vibesurfdev.com-0a0000?style=for-the-badge&logo=rust&logoColor=ff4b14&labelColor=1a0500)](https://vibesurfdev.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a0000?style=for-the-badge&logo=linkedin&logoColor=ff2222&labelColor=1a0500)](https://www.linkedin.com/in/romero-saraiva-ba315b345/)
[![Email](https://img.shields.io/badge/Email-0a0000?style=for-the-badge&logo=gmail&logoColor=ff2222&labelColor=1a0500)](mailto:romerosaraiva4@gmail.com)

<img src="https://komarev.com/ghpvc/?username=ArmitageThird&style=for-the-badge&color=ff2222&label=VISITORS" />

</div>

---

## `> whoami`

```
╔══════════════════════════════════════════════════════════════╗
║  user    : Romero Saraiva                                    ║
║  handle  : ArmitageThird        // Armitage III (1995)       ║
║  role    : Rust Developer       [ in progress ]              ║
║  stack   : Rust · Axum · Tokio · SQLx · Postgres             ║
║  crew    : VibeSurf Dev         // vibesurfdev.com           ║
║  status  : compiling...         [■■■■■□□□□□]                 ║
╚══════════════════════════════════════════════════════════════╝
```

Estou adotando **Rust** como minha linguagem principal — backend, sistemas e tudo que exigir performance com segurança de memória. Na prática, isso significa `Axum` + `Tokio` + `SQLx` do lado do servidor e `React Router 7` + `Vite` do lado do cliente.

Construo projetos em Rust junto da **[VibeSurf Dev](https://vibesurfdev.com)**.

O nome não é acaso: ferro que oxida vira **rust**. Meta enferrujada, propósito afiado.

> *"Não estou chegado — estou chegando."*

```
        _~^~^~_
    \) /  o o  \ (/
      '_   ¬   _'
      / '-----' \
```

---

## `> cat Cargo.toml`

```toml
[package]
name        = "romero-saraiva"
version     = "2026.1.0"
edition     = "2024"
authors     = ["ArmitageThird <romerosaraiva4@gmail.com>"]
description = "Virando Rust developer. Backend, sistemas e web."
keywords    = ["rust", "axum", "tokio", "sqlx", "backend"]
repository  = "https://github.com/ArmitageThird"

[dependencies]
rust  = { version = "stable", features = ["ownership", "lifetimes", "zero-cost"] }
tokio = { version = "1", features = ["full"] }
axum  = "0.8"
sqlx  = { version = "0.8", features = ["postgres", "runtime-tokio"] }

[dev-dependencies]
react-router = "7"
vite         = "*"
cafe         = { version = "∞", optional = false }

[profile.release]
opt-level = 3
lto       = true
panic     = "abort"   # sem desistir no meio do caminho
```

---

## `> cargo tree --workspace`

<div align="center">

**`[ core ]`**

![Rust](https://img.shields.io/badge/Rust-0a0000?style=for-the-badge&logo=rust&logoColor=ff4b14&labelColor=1a0500)

**`[ backend ]`**

![Tokio](https://img.shields.io/badge/Tokio-0a0000?style=for-the-badge&logo=rust&logoColor=ff4b14&labelColor=1a0500)
![Axum](https://img.shields.io/badge/Axum-0a0000?style=for-the-badge&logo=rust&logoColor=ff4b14&labelColor=1a0500)
![SQLx](https://img.shields.io/badge/SQLx-0a0000?style=for-the-badge&logo=rust&logoColor=ff4b14&labelColor=1a0500)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0a0000?style=for-the-badge&logo=postgresql&logoColor=ff4b14&labelColor=1a0500)

**`[ frontend ]`**

![React Router 7](https://img.shields.io/badge/React%20Router%207-0a0000?style=for-the-badge&logo=reactrouter&logoColor=ff2222&labelColor=1a0500)
![Vite](https://img.shields.io/badge/Vite-0a0000?style=for-the-badge&logo=vite&logoColor=ff2222&labelColor=1a0500)
![TypeScript](https://img.shields.io/badge/TypeScript-0a0000?style=for-the-badge&logo=typescript&logoColor=ff2222&labelColor=1a0500)
![JavaScript](https://img.shields.io/badge/JavaScript-0a0000?style=for-the-badge&logo=javascript&logoColor=ff2222&labelColor=1a0500)
![HTML5](https://img.shields.io/badge/HTML5-0a0000?style=for-the-badge&logo=html5&logoColor=ff2222&labelColor=1a0500)
![CSS3](https://img.shields.io/badge/CSS3-0a0000?style=for-the-badge&logo=css3&logoColor=ff2222&labelColor=1a0500)

**`[ tooling ]`**

![Git](https://img.shields.io/badge/Git-0a0000?style=for-the-badge&logo=git&logoColor=ff2222&labelColor=1a0500)
![GitHub](https://img.shields.io/badge/GitHub-0a0000?style=for-the-badge&logo=github&logoColor=ff2222&labelColor=1a0500)
![VS Code](https://img.shields.io/badge/VS%20Code-0a0000?style=for-the-badge&logo=visualstudiocode&logoColor=ff2222&labelColor=1a0500)

**`[ exploring ]`**

![AI & LLMs](https://img.shields.io/badge/AI%20%26%20LLMs-0a0000?style=for-the-badge&logo=openai&logoColor=ff2222&labelColor=1a0500)

</div>

---

## `> ./now.sh`

```
[ building ]  projetos em Rust na VibeSurf Dev
[ learning ]  async Rust — Tokio, futures e o borrow checker me humilhando
[ next     ]  meu primeiro crate publicado no crates.io
```

### `rustup roadmap`

- [x] Ownership, borrowing & lifetimes
- [x] Traits, generics e tratamento de erro (`Result`, `?`, `thiserror`)
- [ ] Async deep dive — `Future`, `Pin`, runtime do Tokio
- [ ] API em produção: Axum + SQLx + Postgres
- [ ] Publicar meu primeiro crate no crates.io
- [ ] Primeira contribuição em projeto Rust open source

---

## `> gh stats --user ArmitageThird`

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=ArmitageThird&show_icons=true&include_all_commits=true&custom_title=Combat%20Log&bg_color=0a0000&border_color=3d0000&icon_color=ff4b14&title_color=ff4b14&text_color=ffaaaa&hide_border=false&rank_icon=github" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ArmitageThird&layout=compact&langs_count=8&custom_title=Languages&bg_color=0a0000&border_color=3d0000&title_color=ff4b14&text_color=ffaaaa&hide_border=false" />

<br/><br/>

<img src="https://streak-stats.demolab.com?user=ArmitageThird&background=0a0000&border=3d0000&ring=ff4b14&fire=ff2222&currStreakLabel=ff4b14&currStreakNum=ffaaaa&sideLabels=ff4b14&sideNums=ffaaaa&dates=ff6666&stroke=3d0000" />

<br/><br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=ArmitageThird&custom_title=Contribution%20Graph&bg_color=0a0000&color=ff4b14&line=ff2222&point=ffaaaa&area=true&area_color=3d0000&title_color=ff4b14&hide_border=false&border_color=3d0000" />

<br/><br/>

<img src="https://github-profile-trophy.vercel.app/?username=ArmitageThird&theme=darkhub&no-frame=true&no-bg=true&column=7&margin-w=6&margin-h=6" />

</div>

<!--
  🐍 SNAKE DE CONTRIBUIÇÕES (opcional)
  Descomente a linha abaixo DEPOIS de criar o workflow .github/workflows/snake.yml (action: Platane/snk)
  <div align="center">
    <img src="https://raw.githubusercontent.com/ArmitageThird/ArmitageThird/output/snake.svg" />
  </div>
-->

---

## `> cat philosophy.txt`

> *"No matter how far technology evolves, someone still has to build it — line by line."*
>
> ― inspirado em **Armitage III** (1995)

```rust
// fearless concurrency · zero-cost abstractions · no garbage collector
fn main() -> Result<(), Box<dyn Error>> {
    let mut romero = Developer::new("ArmitageThird");

    while romero.is_alive() {
        romero.learn(Rust)?;
        romero.build()?;
        romero.ship()?;
    }

    Ok(())
}
```

---

<details>
<summary><b><code>> history | grep -i "servicenow"</code></b></summary>

<br/>

Antes de virar a chave pro Rust, estudei **ServiceNow** a sério — e não abandonei a plataforma.
Continua no cinto de utilidades; só não é o que eu construo aqui no GitHub.

![ServiceNow](https://img.shields.io/badge/ServiceNow-0a0000?style=for-the-badge&logo=servicenow&logoColor=ff2222&labelColor=1a0500)

</details>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0000,50:2b0a00,100:000000&height=130&section=footer&animation=fadeIn" />

<sub><code>$ echo "compilado à mão por ArmitageThird · 2026"</code></sub>

</div>
