# 🤖 NOBA CORE: Next-Gen General Services & Biometric Security
> **Protocolo de Acceso Inteligente v2.0** | *Desarrollado para el ecosistema NOBA 2026.*

![Status](https://img.shields.io/badge/Status-In_Development-blue)
![Tech](https://img.shields.io/badge/Stack-Flask_%7C_MediaPipe_%7C_MySQL-brightgreen)

## 🌌 Visión General
NOBA CORE no es solo un portal de servicios; es una infraestructura de seguridad diseñada para mitigar el fraude de identidad en la contratación de servicios generales. Utilizando **Computer Vision** y **Redes Neuronales**, el sistema garantiza que solo el usuario autorizado pueda operar en la plataforma.



---

## 🛠️ Arquitectura Técnica

### 1. Motor de Biometría (Edge AI)
A diferencia de los sistemas tradicionales que envían el video al servidor (lentos y menos seguros), NOBA utiliza **MediaPipe Tasks Vision**. 
- **Modelo:** BlazeFace (Short-range).
- **Procesamiento:** Ejecución en el cliente vía GPU (WASM).
- **Lógica de Validación:** El sistema no concede acceso con una simple detección; requiere una persistencia de 30 frames con un puntaje de confianza $> 0.60$ para evitar el uso de fotografías estáticas.

### 2. Backend Robusto
El núcleo está construido sobre **Flask**, gestionando:
- **Session Management:** Cookies cifradas para mantener la persistencia del usuario.
- **Security Hashing:** Implementación de `bcrypt` con sal (salt) para proteger las contraseñas contra ataques de diccionario.
- **REST API:** Endpoints específicos para el intercambio de estados entre la IA del navegador y la base de datos.

### 3. Interfaz Futurista (UI/UX)
Diseño basado en el concepto **Glass-Neón**:
- **HUD (Head-Up Display):** Interfaz de escaneo inspirada en sistemas operativos avanzados.
- **Chatbot Neural:** Un asistente que soporta interacción multimedia, stickers y protocolos de comunicación cifrada.

---

## 📦 Requisitos del Sistema
Para desplegar NOBA CORE en tu entorno local, necesitas:
- **Python 3.10+**
- **MySQL Server 8.0+**
- **Navegador moderno** (Chrome o Edge recomendado por soporte de WebGL/GPU).

---

## 4. Estructura del Proyecto 📂
SISTEMA_SERVICIOS/
├── app.py              # Servidor principal (Flask)
├── README.md           # Documentación del sistema
├── .gitignore          # Archivos omitidos por Git
├── pyvenv.cfg          # Configuración del entorno virtual
├── static/             # Archivos estáticos
│   ├── css/            # Hojas de estilo
│   │   ├── index.css   # Estilos globales y HUD
│   │   ├── login.css   # Estilos para acceso manual
│   │   └── registro.css# Estilos para nuevos usuarios
│   ├── img/            # Recursos gráficos
│   │   ├── logo.png
│   │   ├── logochatbot.png
│   │   ├── logoSimbolo.png
│   │   └── loguito.png
│   └── video/          # Fondos y recursos multimedia
│       ├── servicios.mp4
│       └── serviciosregistro.mp4
├── templates/          # Vistas HTML (Jinja2)
│   ├── index.html      # Landing & Scanner Biométrico
│   ├── login.html      # Interfaz de acceso manual
│   └── registro.html   # Formulario de registro
└── venv/               # Entorno virtual de Python
    ├── Include/
    ├── Lib/
    └── Scripts/


    
## 🚀 Instalación Paso a Paso

1. **Clonación del Repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/noba-core.git](https://github.com/tu-usuario/noba-core.git)
   cd noba-core