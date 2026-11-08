# 🌑 From the Abyss — Jogo de Plataforma 2D (Unity / C#)

![Menu Principal](Screenshot%20Menu.jpg)

> **Status:** Concluído (Projeto de TCC) | **Engine:** Unity 2022.3.62f2 LTS | **Portal Web Oficial:** [Site-From-The-Abyss](https://github.com/EduardoBruscagim/Site-From-The-Abyss) ([from-the-abyss.vercel.app](https://from-the-abyss.vercel.app/))

---

## 📜 Sobre o Projeto

**From the Abyss** é um jogo indie de plataforma 2D de precisão desenvolvido na **Unity Engine (C#)** como Trabalho de Conclusão de Curso (TCC). O projeto explora física 2D customizada, gravidade adaptativa, detecção de colisão por *Raycasting* e gerenciamento de estados de cena.

---

## ⚙️ Arquitetura de Scripts C# (`From the Abyss/Assets/`)

| Script | Caminho | Responsabilidade Técnica |
|---|---|---|
| [`Personagem.cs`](From%20the%20Abyss/Assets/Capitulo%201/Scripts/Personagem.cs) | `Assets/Capitulo 1/Scripts/` | Controlador principal de física (`Rigidbody2D`), pulo com gravidade variável (`HandleBetterJump`), pulo duplo e *Dash* direcional com verificação de colisão via `Physics2D.Raycast`. |
| [`ColisaoEspinho.cs`](From%20the%20Abyss/Assets/Capitulo%201/Scripts/ColisaoEspinho.cs) | `Assets/Capitulo 1/Scripts/` | Sistema de dano, *Screen Flash* por corrotina (`FlashScreen`), congelamento físico em morte e suporte a dois modos (`ReiniciarCena` ou `Respawn` em *Checkpoint*). |
| [`CameraFollow.cs`](From%20the%20Abyss/Assets/Capitulo%201/Scripts/CameraFollow.cs) | `Assets/Capitulo 1/Scripts/` | Câmera 2D com interpolação suave (`Vector3.SmoothDamp`) e *look-ahead* dinâmico baseado no estado de queda do jogador. |
| [`ControladorJogo.cs`](From%20the%20Abyss/Assets/Capitulo%201/Scripts/ControladorJogo.cs) | `Assets/Capitulo 1/Scripts/` | Singleton de sessão para contabilização de colecionáveis e atualização de HUD. |
| [`MenuManager.cs`](From%20the%20Abyss/Assets/Menu/Scripts%20Menu/MenuManager.cs) | `Assets/Menu/Scripts Menu/` | Gerenciamento de resolução, *Fullscreen*, *VSync*, persistência de preferências via `PlayerPrefs` e mixagem de áudio em escala logarítmica (`Mathf.Log10(volume) * 20`). |
| [`PauseManager.cs`](From%20the%20Abyss/Assets/Capitulo%201/Scripts/PauseManager.cs) | `Assets/Capitulo 1/Scripts/` | Controle de pausa em tempo de execução (`Time.timeScale`) e navegação entre cenas. |

---

## 🎮 Mecânicas e Funcionalidades

- **Gravidade Variável (*Better Jump*):** Ajuste dinâmico do `gravityScale` no `FixedUpdate` (`1.8f` em subida com botão pressionado, `4.0f` em pulo curto ao soltar o botão e `2.0f` em queda) para resposta precisa de plataforma.
- **Dash com Prevenção de Tunneling:** Uso de `Physics2D.Raycast` na camada `Ground` antes de aplicar o deslocamento de alta velocidade (`DashForce`).
- **Sistema de Áudio Persistente:** Transição contínua de trilha sonora entre cenas utilizando `DontDestroyOnLoad` e mixagem em decibéis via `AudioMixer`.

---

## 🛠️ Tecnologias e Ferramentas

- **Motor Gráfico:** Unity 2022.3.62f2 (LTS) — Universal Render Pipeline (URP 2D)
- **Linguagem:** C#
- **Design & Pixel Art:** Photoshop, Pixilart, Aseprite, Figma
- **Versionamento:** Git

---

## 🚀 Como Jogar

Você pode baixar a versão compilada para Windows através do portal oficial do projeto:

👉 **[https://from-the-abyss.vercel.app/](https://from-the-abyss.vercel.app/)**

### 🕹️ Controles

| Ação | Teclado |
| :--- | :--- |
| **Mover** | `A` / `D` ou `Setas Direcionais` |
| **Pular / Pulo Duplo** | `Espaço` (segure para salto alto; pressione 2x para pulo duplo) |
| **Dash** | `Shift Esquerdo` + Direção |
| **Pausar** | `Esc` |

---

## 👨‍💻 Autor

**Eduardo Guilherme Bruscagim**
- **GitHub:** [@EduardoBruscagim](https://github.com/EduardoBruscagim)
