# Bot de minijuegos para Discord

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![discord.py](https://img.shields.io/badge/discord.py-2.6%2B-5865F2?logo=discord&logoColor=white)](https://discordpy.readthedocs.io/)
[![MIT](https://img.shields.io/badge/Licencia-MIT-green)](LICENSE)

[Español](#español) · [English](#english)

---

## Español

### Índice

- [Descripción](#descripción)
- [Minijuegos](#minijuegos)
- [Características técnicas](#características-técnicas)
- [Requisitos](#requisitos)
- [Instalación](#instalación)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Licencia](#licencia)

### Descripción

Bot de Discord en **Python** centrado en entretenimiento y minijuegos interactivos. Aprovecha la API de interacciones al completo: **slash commands**, botones, menús desplegables y ventanas modales, de modo que casi todo se juega sin escribir en el chat.

### Minijuegos

| Comando | Juego | Cómo funciona |
|---|---|---|
| `/tictactoe` | Tres en raya | Contra la IA o contra otro miembro mencionado. El tablero son botones que se colorean según el símbolo. |
| `/adivinar` | Adivina el número | El bot piensa un número del 1 al 50 y tienes 7 intentos; cada intento se envía por un **modal** privado. |
| `/duelo` | Duelo de insultos | Duelo por turnos con 3 puntos de vida: hay que elegir la réplica correcta en el menú antes de que acabe el tiempo. |

**Detalles de diseño**

- **Tres en raya**: la IA prioriza ganar, después bloquear, y elige el resto por heurística de centro y esquinas.
- **Adivinar**: el modal evita llenar el canal de mensajes y mantiene cada intento privado.
- **Duelo**: cada fallo o tiempo agotado resta una vida; gana quien deje al rival a cero.

### Características técnicas

- **Slash commands** sincronizados automáticamente con `bot.tree.sync()`.
- **Componentes de UI**: `discord.ui.View`, `Button`, `Select` y `Modal`.
- **Errores centralizados** con `@bot.tree.error` y trazas limpias en el log.
- **Control de inactividad**: los tableros y menús se desactivan solos con `on_timeout` y el mensaje se edita para indicar que la partida expiró.
- **Logs** con la librería estándar `logging`, separados en su propio módulo.

### Requisitos

- **Python 3.8 o superior**.
- **discord.py 2.6.3+** (necesario para componentes y `app_commands`).
- Una aplicación de bot en el [Discord Developer Portal](https://discord.com/developers/applications) con el token a mano.
- Permisos de **applications.commands** y **bot** al invitar el bot al servidor.

### Instalación

```bash
git clone https://github.com/alberto2005-coder/Bot-juegos.git
cd Bot-juegos
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

pip install -U discord.py
```

Crea `config.py` en la raíz con tu token:

```python
DISCORD_TOKEN = "TU_TOKEN_AQUI"
```

Y arranca el bot:

```bash
python main.py
```

> [!IMPORTANT]
> `config.py` está en `.gitignore` precisamente para que el token no acabe en el repositorio. No lo subas ni lo compartas: si se filtra, regenera el token en el portal.

Los comandos globales pueden tardar hasta una hora en propagarse la primera vez; para probar en un servidor concreto, sincroniza en el guild desde el propio código.

### Estructura del proyecto

```text
Bot-juegos/
├── main.py          # Bot, vistas y lógica de los tres juegos
├── config.py        # Token de Discord (excluido de git)
├── log_setup.py     # Configuración y formato de logs
├── LICENSE
└── README.md
```

### Licencia

**MIT** — consulta [LICENSE](LICENSE).

---

## English

### Table of contents

- [Overview](#overview)
- [Minigames](#minigames)
- [Technical highlights](#technical-highlights)
- [Requirements](#requirements)
- [Installation](#installation)
- [Project structure](#project-structure)
- [License](#license)

### Overview

A **Python** Discord bot focused on entertainment and interactive minigames. It leans on the interaction API end to end: **slash commands**, buttons, select menus and modals, so almost everything is played without typing in chat.

### Minigames

| Command | Game | How it works |
|---|---|---|
| `/tictactoe` | Tic-tac-toe | Against the AI or a mentioned member. The board is made of buttons that recolour per symbol. |
| `/adivinar` | Guess the number | The bot picks 1–50 and you get 7 attempts; each guess is sent through a private **modal**. |
| `/duelo` | Insult duel | Turn-based duel with 3 lives: pick the right comeback from the menu before the timer runs out. |

**Design notes**

- **Tic-tac-toe**: the AI wins when it can, blocks when it must, and otherwise scores centre and corners.
- **Guess the number**: the modal keeps the channel clean and every guess private.
- **Duel**: a wrong answer or a timeout costs a life; the last player standing wins.

### Technical highlights

- **Slash commands** synced automatically with `bot.tree.sync()`.
- **UI components**: `discord.ui.View`, `Button`, `Select` and `Modal`.
- **Centralised errors** through `@bot.tree.error` with clean log traces.
- **Idle handling**: boards and menus disable themselves via `on_timeout` and the message is edited to show the game expired.
- **Logging** with the standard `logging` module, kept in its own file.

### Requirements

- **Python 3.8 or later**.
- **discord.py 2.6.3+** (required for components and `app_commands`).
- A bot application in the [Discord Developer Portal](https://discord.com/developers/applications) with its token at hand.
- **applications.commands** and **bot** scopes when inviting the bot.

### Installation

```bash
git clone https://github.com/alberto2005-coder/Bot-juegos.git
cd Bot-juegos
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

pip install -U discord.py
```

Create `config.py` in the project root with your token:

```python
DISCORD_TOKEN = "YOUR_TOKEN_HERE"
```

Then start the bot:

```bash
python main.py
```

> [!IMPORTANT]
> `config.py` is git-ignored precisely so the token never lands in the repository. Never commit or share it: if it leaks, regenerate the token in the portal.

Global commands can take up to an hour to propagate the first time; to test in a single server, sync to that guild from the code.

### Project structure

```text
Bot-juegos/
├── main.py          # Bot, views and the three games
├── config.py        # Discord token (git-ignored)
├── log_setup.py     # Logging configuration and format
├── LICENSE
└── README.md
```

### License

**MIT** — see [LICENSE](LICENSE).
