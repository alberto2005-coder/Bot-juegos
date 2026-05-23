
# 🤖 Bot de Minijuegos Interactivos para Discord

Un bot de Discord completo, moderno y completamente en español enfocado en entretenimiento y minijuegos interactivos. Desarrollado en Python, aprovecha al máximo la API de interacciones de Discord utilizando botones, menús desplegables (*Selects*) y ventanas emergentes (*Modals*).

---

## 🎮 Minijuegos Incluidos

### 1. ❌ Tres en Raya (`/tictactoe`)
* **Modo Un Jugador:** Enfréntate a una Inteligencia Artificial con estrategia de bloqueo y ataque automática.
* **Modo Dos Jugadores:** Reta a cualquier miembro del servidor mencionándolo en el comando.
* **Interfaz:** Tablero dinámico renderizado 100% con botones de Discord que cambian de color según el símbolo (Rojo para ❌ y Verde para ⭕).

### 2. 🤔 Adivina el Número (`/adivinar`)
* El bot piensa un número aleatorio entre 1 y 50.
* Tienes un máximo de 7 intentos para adivinarlo.
* **Mecánica interactiva:** Utiliza los **Modals (ventanas de texto nativas de Discord)** para enviar tus intentos de forma privada y limpia, evitando saturar el chat de texto.

### 3. 🤺 Duelo de Insultos (`/duelo`)
* Inspirado en los clásicos duelos de piratas del mítico *Monkey Island*. ¡Reta a otro miembro a una batalla de ingenio!
* Cada jugador inicia con 3 puntos de vida (❤️).
* El atacante debe responder de forma brillante seleccionando la réplica correcta desde un menú desplegable antes de que expire el tiempo. El que falle, pierde una vida.

---

## ✨ Características Técnicas

* **Comandos de Barra Diagonal (Slash Commands):** Sincronización automática de comandos globales usando `bot.tree.sync()`.
* **Componentes UI Modernos:** Uso eficiente de `discord.ui.View`, `discord.ui.Button`, `discord.ui.Select` y `discord.ui.Modal`.
* **Estructura Robusta:** Sistema centralizado de control de errores mediante `@bot.tree.error` y logs integrados con la librería `logging` de Python para monitorear partidas y capturar excepciones de forma limpia.
* **Control de Inactividad:** Sistema de `on_timeout` para deshabilitar automáticamente los tableros y menús si los jugadores dejan una partida colgada, editando el mensaje para reflejar que el juego expiró.

---

## 📂 Estructura del Proyecto

```text
BOT-MINIJUEGOS/
│── main.py            # Archivo principal con la lógica del bot y los 3 juegos
│── config.py          # Almacenamiento seguro del Token de Discord (excluido en .gitignore)
│── log_setup.py       # Configuración y formateo del sistema de logs
│── README.md          # Documentación del proyecto
└── LICENSE            # Licencia de código abierto

```

---

## 🚀 Instalación y Configuración

### 1. Clonar el repositorio

```bash
git clone [https://github.com/alberto2005-coder/Nombre-De-Tu-Repositorio.git](https://github.com/alberto2005-coder/Nombre-De-Tu-Repositorio.git)
cd Nombre-De-Tu-Repositorio

```

### 2. Configurar las credenciales

Crea un archivo llamado `config.py` en la raíz del proyecto y añade tu Token de Discord obtenido en el [Discord Developer Portal](https://discord.com/developers/applications/):

```python
DISCORD_TOKEN = "TU_TOKEN_SECRETO_AQUÍ"

```

### 3. Lanzar el bot

Asegúrate de tener instalada la librería `discord.py` y ejecuta el archivo principal:

```bash
python main.py

```

---

## 🛠️ Tecnologías Utilizadas

* **Python 3.8+**
* **discord.py 2.6.3+** (con soporte completo para componentes de UI y Slash Commands)
* **Logging** (Librería estándar de control de registros de Python)

---

## 📜 Licencia

Este proyecto se distribuye bajo la Licencia MIT. Consulta el archivo `LICENSE` para más información.

```

```
