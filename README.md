# 🤖 Bot de Telegram con Google Gemini AI

Este proyecto utiliza **Python**, la API de **Google Gemini** y el framework **LangChain** para crear un bot interactivo, integrando también la librería `python-telegram-bot` para su uso en Telegram.

## Tecnologías Utilizadas

- Python 3.9+
- LangChain
- langchain-google-genai
- Google Gemini API
- python-telegram-bot
- requests
- python-dotenv

## Instalación

1. **Clona el repositorio**:
   ```bash
   git clone <url-del-repositorio>
   ```

2. **Crea y activa un entorno virtual**:
   ```bash
   py -m venv bot_env
   ```

   - En **Windows**:
     ```bash
     bot_env\Scripts\activate
     ```
   
   - En **macOS/Linux**:
     ```bash
     source bot_env/bin/activate
     ```

3. **Instala las dependencias**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configurar Variables de Entorno**:
   
   Crea un archivo `.env` en la raíz del proyecto:
   ```env
   TELEGRAM_BOT_TOKEN=
   GEMINI_API_KEY=
   WEATHER_API_KEY
   WEATHER_BASE_URL
   ```

   **Obtener las API Keys:**
   - **Telegram Bot Token**: Habla con [@BotFather](https://t.me/BotFather) en Telegram
   - **Gemini API Key**: Regístrate en [Google AI Studio](https://ai.google.dev/)
   - **Weather API Key**: Regístrate en [Weather api](https://www.weatherapi.com/)

5. **Ejecutar el Bot**
   ```bash
   python bot.py || py bot.py
   ```
   
## Comandos Disponibles
   
| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
| `/start` | Inicia el bot y muestra bienvenida | `/start` |
| `/help` | Lista todos los comandos disponibles | `/help` |
| `/fecha` | Muestra fecha y hora actual | `/fecha` |
| `/clima [ciudad]` | Información meteorológica | `/clima San Salvador` |
| `/convertir [cantidad] [moneda_origen] a [moneda_destino]` | Convertir entre monedas | `/convertir 10 USD a EUR` |

**Estructura de archivos:**
   ```
   telegram_bot/
   ├── .env                 # Variables secretas
   ├── .gitignore          # Ignorar archivos sensibles
   ├── bot.py              # Archivo principal
   ├── config.py           # Configuraciones
   ├── handlers/           # Carpeta para manejadores
   │   ├── __init__.py
   │   ├── commands.py     # Comandos del bot
   │   └── messages.py     # Manejo de mensajes
   ├── utils/              # Utilidades
   │   ├── __init__.py
   │   └── gemini_client.py # Cliente de Gemini
   |   └── tools.py         # Tools personalizadas
   ├── requirements.txt    # Lista de dependencias
   └── README.md          # Documentación
   ```
## 🚀 Despliegue en Railway (Gratuito)
Pasos para desplegar en Railway:
Prepara tu código:

**Tu archivo principal debe ser bot.py (o modifica el nombre en Railway)**

Crea cuenta en Railway:

1. Ve a railway.app y regístrate con tu cuenta de GitHub

2. Crea un nuevo proyecto:

3. Haz clic en "New Project"

4. Selecciona "Deploy from GitHub repo"

5. Conecta tu cuenta de GitHub si no lo has hecho

6. Selecciona tu repositorio:

7. Elige el repositorio donde está tu bot

8. Railway detectará automáticamente que es Python

9. Configura las variables de entorno:

10. Ve a la pestaña "Variables" de tu proyecto

**Añade las siguientes variables** 
```
TELEGRAM_BOT_TOKEN=tu_token_de_telegram_aqui
GEMINI_API_KEY=tu_api_key_de_gemini_aqui
WEATHER_API_KEY=tu_api_key_de_clima_opcional
WEATHER_BASE_URL=https://api.weatherapi.com/v1
TZ = America/El_Salvador (para que configure correctamente la hora)
Espera el despliegue:
   ```
Railway comenzará a desplegar automáticamente

Deberías ver "Bot iniciado correctamente"

Prueba enviando /start a tu bot en Telegram

## 🛠 Solución de problemas en Railway:
Si el despliegue falla: Revisa los logs en la pestaña "Deployments"

Si el bot no inicia: Verifica que las variables de entorno estén correctas

Si hay errores de dependencias: Actualiza tu requirements.txt

## ¿Por qué Railway?

Railway ofrece opciones de despliegues sumamente sencilla, cero configuración de entorno y que ofrece la posibilidad de conectarlo con github para agilizar los despliegues y de igual manera hacer rollback de manera sencilla. así como el crear automatizaciones incorporando servicios. Sin embargo es de mencionar que sobre la capa gratuita ofrece una gran capacidad que para iniciar en despliegues pequeños que no requieran 
tanto cómputo es una buena opción, adicionalmente permite escalado vertical bastante flexible
