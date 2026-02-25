# Servidor de Versiones - Oper360

## 🚀 Despliegue en GitHub Pages

### 1. Crear Repositorio
```bash
# Crea un nuevo repositorio en GitHub llamado: oper360-version-server
# Hazlo público para que GitHub Pages funcione
```

### 2. Subir Archivos
```bash
git init
git add .
git commit -m "Initial commit - Oper360 Version Server"
git branch -M main
git remote add origin https://github.com/[tu-username]/oper360-version-server.git
git push -u origin main
```

### 3. Activar GitHub Pages
1. Ve a tu repositorio en GitHub
2. Click en **Settings** ⚙️
3. En la sección **Pages**, selecciona:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/root**
4. Click **Save**

### 4. URLs Disponibles
- **Sitio web**: `https://[tu-username].github.io/oper360-version-server`
- **API de versiones**: `https://[tu-username].github.io/oper360-version-server/api/version.json`

### 5. Subir APKs
1. Crea una carpeta `releases/`
2. Sube tus archivos APK:
   - `Oper360v2.0.1.apk`
   - `Oper360v2.0.0.apk` (opcional)
   - `Oper360v1.02.apk` (opcional)

### 6. Actualizar Aplicación
Modifica tu `versionService.ts` para usar la nueva API:

```typescript
async checkVersion(): Promise<VersionCheckResponse> {
  const response = await fetch('https://[tu-username].github.io/oper360-version-server/api/version.json');
  return await response.json();
}
```

## 📁 Estructura de Archivos
```
oper360-version-server/
├── index.html          # Página de descargas
├── api/
│   └── version.json    # API de versiones
├── releases/           # Carpeta para APKs
│   ├── Oper360v2.0.1.apk
│   ├── Oper360v2.0.0.apk
│   └── Oper360v1.02.apk
└── README.md          # Este archivo
```

## 🔧 Configuración de Versiones
Edita `api/version.json` para controlar qué versiones son compatibles:

```json
{
  "forceUpdate": true,        // Forzar actualización
  "currentVersion": "2.0.1",  // Versión más reciente
  "minSupportedVersion": "2.0.1", // Versión mínima compatible
  "message": "Mensaje para usuarios",
  "downloadUrl": "URL directa al APK",
  "releaseNotes": "Notas de la versión"
}
```

## 📱 Beneficios
- ✅ Servidor gratuito en GitHub Pages
- ✅ Control centralizado de versiones
- ✅ Actualizaciones automáticas
- ✅ Bloqueo de versiones antiguas
- ✅ Estadísticas de descargas (GitHub Analytics)
