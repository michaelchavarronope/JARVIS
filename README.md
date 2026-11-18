# JARVIS

**Asistente virtual de escritorio para Windows con inteligencia artificial.** JARVIS se controla por voz o por texto, entiende el contexto de lo que haces en el computador y automatiza tareas del sistema, la web, los archivos y las comunicaciones desde una sola interfaz.

> **Versión beta.** El proyecto está en desarrollo activo y puede tener cambios importantes entre versiones.

## Funciones

| Área | Qué hace |
|---|---|
| **Voz** | Activación en cualquier momento con la tecla global `Insert`, incluso con la ventana minimizada. Reconocimiento de voz local con Vosk y respuesta hablada. |
| **Interfaz** | Interfaz holográfica con orbe reactivo, tema dorado y animaciones mientras procesa. |
| **Control del sistema** | Volumen, brillo, energía y *Focus Assist* según tus hábitos y la ventana activa. |
| **Automatización** | Puede escribir sus propias habilidades (`auto_programmer`), probarlas en un entorno aislado con tiempo límite e incorporarlas si funcionan. |
| **Web y multimedia** | Búsqueda en la web, reproducción de música y videos en YouTube y control de Spotify. |
| **Archivos y documentos** | Abre, crea y edita documentos; clasifica archivos y elimina duplicados exactos mediante MD5. |
| **Comunicaciones** | Envío de mensajes por correo, Telegram, Discord y WhatsApp desde la misma interfaz. |
| **Modelos de IA** | Integración con Gemini y OpenRouter. |

## Requisitos

- Windows 10 u 11.
- [Python 3.12](https://www.python.org/downloads/), con la opción "Add Python to PATH" marcada.
- Llaves de API de los servicios que quieras usar (Gemini u OpenRouter como mínimo).

## Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/michaelchavarronope/JARVIS.git
   ```
2. Ejecuta `Instalar_JARVIS.bat`. Crea el entorno virtual (`.venv`), instala las dependencias de `requirements.txt` y genera la configuración inicial.
3. Copia `config/api_keys.example.json` como `config/api_keys.json` (si el instalador no lo hizo) y escribe tus llaves de API.
4. Inicia JARVIS con `Iniciar JARVIS Beta.vbs`, que lo abre en segundo plano.

Algunos módulos se distribuyen compilados (`.pyc`) para Python 3.12, por lo que esa versión de Python es obligatoria.

## Tecnologías

| Componente | Tecnología |
|---|---|
| Lenguaje | Python 3.12 |
| Interfaz | PyQt6 y Qt WebEngine |
| IA | Gemini (`google-genai`) y OpenRouter |
| Voz | Vosk (reconocimiento local), gTTS y Edge TTS |
| Integración con Windows | `pycaw`, `pygetwindow`, `pywinauto`, `psutil`, `ctypes` (Win32) |
| Automatización web | Playwright |

## Seguridad y privacidad

- Las llaves de API se guardan solo en tu equipo, en `config/api_keys.json`. Ese archivo está excluido del repositorio por `.gitignore` y no debe compartirse.
- El perfil de usuario y la memoria del asistente (`config/user_profile.json`, `memory/long_term.json`) se crean y guardan localmente; tampoco se suben al repositorio.
- JARVIS puede controlar el sistema, ejecutar comandos y enviar mensajes en tu nombre: revisa los permisos que le das y úsalo en un equipo de confianza.

## Licencia

Este proyecto no tiene licencia de código abierto: todos los derechos reservados por su autor.
