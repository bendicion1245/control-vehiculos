# 🚗 VehiControl Pro

Sistema profesional de control de acceso vehicular y peatonal. Aplicación web de una sola página (single-file HTML), sin instalación, pensada para funcionar directo desde el navegador en celular o computadora.

**Demo en vivo:** [bendicion1245.github.io/control-vehiculos](https://bendicion1245.github.io/control-vehiculos/)

---

## 📋 Descripción

VehiControl Pro permite a un equipo de guardias de seguridad registrar y controlar el ingreso y egreso de vehículos y personas a un predio, con roles diferenciados, alertas de lista negra, historial completo, exportación de reportes y manual de ayuda integrado.

---

## ✨ Funciones principales

### Control de acceso
- Registro de ingreso y salida de **vehículos** (matrícula, conductor, empresa, motivo, fotos)
- Registro de ingreso y salida de **personas** (empleados, visitas, contratistas, proveedores)
- Autocompletado de datos para vehículos, personas, conductores y empresas ya registrados
- Vista en tiempo real de todo lo que está dentro del predio
- Simulador de credenciales (`AccessSimulator`): huella, tarjeta RFID/NFC y QR — preparado para conectar hardware real a futuro

### Seguridad y control
- Lista negra de matrículas, personas o empresas con alertas automáticas
- Registro de auditoría de todas las acciones del sistema
- Roles diferenciados: **Guardia**, **Supervisor**, **Administrador**
- Modo mantenimiento (bloquea el sistema para todos menos el admin)

### Gestión y reportes
- Historial completo con filtros por fecha, estado y búsqueda de texto
- Exportación de reportes en **PDF** y **Excel**
- Gestión de usuarios (crear, activar/desactivar, asignar rol)
- Registro de turnos por guardia, con horario de inicio y fin

### Experiencia de usuario
- **Manual de ayuda integrado**, acordeón de 14 capítulos con buscador (botón `?`)
- **Ayuda contextual** en los campos más importantes de cada formulario (16 puntos de ayuda)
- **Tour guiado interactivo**, automático la primera vez que entra un usuario y disponible manualmente después
- Tema claro / oscuro
- Diseño responsive (mobile-first, con navegación inferior en celular y sidebar en pantallas grandes)
- PWA con Service Worker para cache básico offline

---

## 🛠️ Tecnología

| Capa | Tecnología |
|---|---|
| Frontend | HTML + CSS + JavaScript vanilla (sin frameworks, un solo archivo) |
| Backend / Base de datos | [Supabase](https://supabase.com) (Postgres, Auth, Storage, Realtime) |
| Hosting | GitHub Pages |
| Exportación | jsPDF (PDF), SheetJS/xlsx (Excel) |
| Tipografía | Inter + JetBrains Mono (Google Fonts) |

No requiere build, bundler ni instalación de dependencias: es un único `index.html` que se sirve tal cual.

---

## 🚀 Puesta en marcha

1. Cloná o descargá este repositorio.
2. Creá un proyecto en [supabase.com](https://supabase.com).
3. Ejecutá el schema SQL (tablas de usuarios, vehículos, registros, personas, credenciales, lista negra, auditoría, configuración) desde el SQL Editor de Supabase. Las definiciones de las tablas más recientes están documentadas como comentarios dentro del propio `index.html`.
4. Abrí el sistema en el navegador. La primera vez va a pedir la **Project URL** y la **anon public key** de tu proyecto Supabase (Project Settings → API).
5. Listo — las credenciales quedan guardadas en el navegador (`localStorage`) para las próximas veces.

Para desplegarlo en tu propio GitHub Pages: subí el `index.html` a la raíz de un repositorio público y activá GitHub Pages desde la configuración del repo (rama `main`, carpeta raíz).

---

## 👥 Roles del sistema

| Rol | Puede hacer |
|---|---|
| **Guardia** | Registrar ingresos y salidas de vehículos y personas |
| **Supervisor** | Todo lo del guardia + ver auditoría + exportar reportes |
| **Administrador** | Todo lo del supervisor + gestionar usuarios + modo mantenimiento + configuración de Supabase |

---

## 📁 Estructura

Todo el sistema vive en un único archivo:

```
index.html   → HTML + CSS + JavaScript completo del sistema
```

No hay carpetas de assets externos: los íconos son emojis, las fuentes se cargan desde Google Fonts, y las librerías (Supabase, jsPDF, SheetJS) se cargan desde CDN.

---

## 🗄️ Backups

El código fuente se respalda periódicamente en archivos `.zip` fuera de GitHub (Google Drive / almacenamiento personal), separados de los datos.

⚠️ **Importante:** este repositorio contiene únicamente el código de la aplicación. Los datos (vehículos, personas, registros, usuarios, fotos) viven en Supabase y **no** se respaldan acá — conviene exportarlos periódicamente desde el panel de Supabase (Database → Backups, o exportando tablas como CSV).

---

## 📝 Historial de cambios recientes

- **Julio 2026** — Limpieza de código (eliminación de botones de prueba de versiones anteriores)
- **Julio 2026** — Manual de ayuda integrado con acordeón de 14 capítulos y buscador
- **Julio 2026** — Ayuda contextual en formularios de vehículo, persona, usuario y lista negra
- **Julio 2026** — Tour guiado interactivo (automático + manual desde menú de usuario)
- **Julio 2026** — Manual de usuario en PDF con diagramas (documento separado)
- Sistema de credenciales simuladas (`AccessSimulator`) con soporte para huella, RFID/NFC y QR
- Splash screen y modal "Acerca del sistema"
- Modo mantenimiento con bloqueo global para guardias/supervisores

---

## 👤 Autor

**Pablo López** — Desarrollado para gestión de seguridad y control de accesos.

---

*VehiControl Pro — Documento de referencia del repositorio. Para la guía de uso del sistema, ver el manual de ayuda integrado (botón `?` dentro de la aplicación) o el manual en PDF.*
