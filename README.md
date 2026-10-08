# Emby Dashboard Native

Aplicación nativa para **macOS, iPhone y iPad** desarrollada en **SwiftUI** para controlar y consultar un dashboard personal de servidor multimedia.

La aplicación consume la API del dashboard web y permite consultar el estado del sistema, gestionar descargas, revisar actividad, ofertas y logs desde una interfaz nativa adaptada a cada dispositivo.

---

## Captura general

La aplicación mantiene la misma identidad visual que el dashboard web:

- Fondo oscuro
- Tonos azul, violeta y cian
- Indicadores de estado en verde, amarillo y rojo
- Diseño adaptado para macOS, iPhone y iPad

---

## Plataformas

- macOS
- iOS
- iPadOS

El proyecto comparte prácticamente todo el código SwiftUI entre las distintas plataformas.

---

## Características

### Dashboard

Consulta del estado general del sistema:

- CPU del Mac mini
- Memoria RAM
- Almacenamiento
- Estado de servicios
- CPU del servidor Emby
- RAM del servidor Emby
- Carga del sistema
- Información de almacenamiento remoto

### Descargas

Permite gestionar descargas directamente desde la aplicación:

- Añadir una descarga mediante URL
- Subir archivos `.torrent`
- Consultar descargas activas
- Ver progreso
- Consultar cola de descargas
- Ver estado de cada tarea

### Actividad

Historial completo de descargas:

- En cola
- En curso
- Completadas
- Fallidas
- Canceladas

Las fechas y estados se muestran completamente en castellano.

### Ofertas

Sección separada por plataforma:

- PlayStation 5
- Nintendo Switch

Cada plataforma dispone de su propio panel para facilitar la lectura.

### Logs

Consulta de logs del sistema directamente desde la aplicación.

### Ajustes

Configuración de:

- URL del servidor
- Usuario
- Contraseña

La contraseña se almacena utilizando **Keychain**.

---

## Seguridad

Las credenciales no están incluidas en el código fuente.

La aplicación utiliza:

- HTTPS
- HTTP Basic Authentication
- Keychain de Apple para almacenar la contraseña
- Comunicación únicamente con el servidor configurado por el usuario

La contraseña no se guarda en archivos del proyecto ni en `UserDefaults`.

---

## Backend

La aplicación utiliza los endpoints del dashboard web existente.

Entre otros:

```text
/api/dashboard
/api/deals
/api/logs
/api/download
/api/torrent
```

La aplicación no incluye un servidor preconfigurado. La URL se configura desde **Ajustes** y debe utilizar HTTPS.

Ejemplo:

```text
https://dashboard.example.com
```

---

## Tecnologías

- Swift
- SwiftUI
- URLSession
- Keychain Services
- Xcode
- JSON / REST API

---

## Requisitos

### macOS

Se necesita:

- macOS compatible con la versión de Xcode utilizada
- Xcode
- Acceso al dashboard configurado

### iPhone / iPad

Se necesita:

- iOS / iPadOS compatible
- Xcode para instalar la aplicación
- Apple ID configurado en Xcode

---

## Compilar para macOS

Abre:

```text
EmbyDashboard.xcodeproj
```

Selecciona:

```text
EmbyDashboard macOS
```

y ejecuta:

```text
Product → Run
```

o:

```text
⌘ + R
```

---

## Instalar en macOS

Compila la aplicación desde Xcode:

```text
Product → Build
```

Después puedes localizar el `.app` generado desde:

```text
Product → Show Build Folder in Finder
```

y copiar:

```text
EmbyDashboard.app
```

a:

```text
/Applications
```

---

## Instalar en iPhone

Conecta el iPhone al Mac y abre el proyecto en Xcode.

Selecciona:

```text
EmbyDashboard iOS
```

Después:

1. Selecciona tu iPhone como dispositivo de destino.
2. Abre `Signing & Capabilities`.
3. Selecciona tu Apple ID / Development Team.
4. Pulsa `Run`.

Xcode instalará la aplicación directamente en el dispositivo.

---

## Primera configuración

Al abrir la aplicación por primera vez entra en:

```text
Ajustes
```

Configura:

```text
URL del servidor
Usuario
Contraseña
```

Ejemplo:

```text
URL: https://dashboard.example.com
Usuario: usuario
```

Pulsa:

```text
Guardar y comprobar
```

Si las credenciales son correctas, la aplicación comenzará a cargar la información del dashboard.

---

## Estructura del proyecto

```text
EmbyDashboard/
├── APIClient.swift
├── ActivityView.swift
├── Components.swift
├── ContentView.swift
├── DashboardSession.swift
├── DealsView.swift
├── DownloadsView.swift
├── EmbyDashboardApp.swift
├── Formatters.swift
├── KeychainStore.swift
├── LogsView.swift
├── Models.swift
├── OverviewView.swift
├── SettingsView.swift
└── Assets.xcassets/
```

---

## Diseño

La aplicación utiliza la misma paleta visual que el dashboard web.

Colores principales:

```text
Fondo:       #07111F
Azul:        #6EA8FF
Violeta:     #8F7CFF
Cian:        #49D6FF
Verde:       #30D158
Amarillo:    #FFB340
Rojo:        #FF5D73
Texto:       #EEF4FF
```

La interfaz utiliza un diseño responsive:

### macOS

- Navegación lateral
- Paneles en varias columnas
- Vista optimizada para escritorio

### iPad

- Distribución adaptable
- Varias columnas cuando hay espacio disponible

### iPhone

- Diseño en una sola columna
- Controles adaptados para uso táctil
- Navegación optimizada para pantallas pequeñas

---

## Icono

La aplicación utiliza un icono personalizado diseñado específicamente para **Emby Dashboard Native**, incluido dentro de:

```text
Assets.xcassets/AppIcon.appiconset
```

Incluye todos los tamaños requeridos para:

- iPhone
- iPad
- macOS

---

## Estado del proyecto

Proyecto personal en desarrollo activo.

Actualmente incluye:

- Dashboard
- Métricas del sistema
- Descargas
- Torrents
- Historial
- Ofertas
- Logs
- Autenticación
- Keychain
- Compatibilidad macOS / iOS / iPadOS

---

## Futuras mejoras

Algunas posibles mejoras:

- Notificaciones push
- Widgets de iOS
- Widgets de macOS
- Live Activities
- Historial con filtros
- Gráficas de CPU y RAM
- Acciones rápidas
- Face ID / Touch ID
- Estado de servicios en tiempo real
- Notificaciones al finalizar descargas

---

## Uso

Este proyecto está pensado principalmente para uso personal y para funcionar junto con una instancia compatible del backend de Emby Dashboard.

---

## Autor

**Antón Reino**

Proyecto personal para la gestión de mi infraestructura multimedia.
