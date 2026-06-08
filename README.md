# 🌌 Aurora — Free Pterodactyl Theme

**Un tema oscuro, moderno y redondeado para Pterodactyl.  
Inspirado en Nebula, completamente gratis.**

<div align="center">

![Version](https://img.shields.io/badge/versión-1.0.0-8b5cf6?style=for-the-badge)
![Blueprint](https://img.shields.io/badge/Blueprint-requerido-14b8a6?style=for-the-badge)
![Licencia](https://img.shields.io/badge/licencia-MIT-10b981?style=for-the-badge)
![Gratis](https://img.shields.io/badge/precio-GRATIS-8b5cf6?style=for-the-badge)

</div>

---

## ✨ Qué incluye

- 🌑 Fondo negro profundo con glow ambiental púrpura/teal
- 💜 Paleta púrpura/violeta idéntica a Nebula
- 🃏 Server cards redondeadas con efecto hover elevado + glow
- ✨ Barra de gradiente en hover sobre cada server card
- 📊 Barras de recursos con gradiente púrpura → teal
- 🖥️ Consola con JetBrains Mono y colores de sintaxis
- 🎨 Panel de admin completo (sidebar, tablas, modales, forms)
- ⚡ Animaciones de entrada escalonadas en las cards
- 🔡 Fuente Plus Jakarta Sans (igual de moderna que Nebula)
- 📱 Funciona en móvil y escritorio

---

## 📋 Requisitos

| | Versión |
|---|---|
| Pterodactyl Panel | `1.x` |
| Blueprint Framework | `beta-2026-01` o superior |

---

## 🚀 Instalación (3 pasos)

### Paso 1 — Descarga

Descarga el archivo `aurora.blueprint` desde la sección [Releases](../../releases) de este repositorio.

### Paso 2 — Sube e instala

```bash
# Copia el archivo a tu servidor
scp aurora.blueprint usuario@tu-vps:/var/www/pterodactyl/

# Conéctate al VPS
ssh usuario@tu-vps

# Instala el tema
cd /var/www/pterodactyl
blueprint -install aurora
```

### Paso 3 — Limpia la caché

```bash
php artisan view:clear
php artisan cache:clear
```

✅ **¡Listo!** Recarga el panel.

---

## 🔄 Construir el .blueprint desde el código fuente

Si clonaste el repositorio y quieres crear el archivo `.blueprint` tú mismo:

```bash
git clone https://github.com/TuUsuario/aurora-ptero.git
cd aurora-ptero

# Crear el archivo .blueprint (es un ZIP renombrado)
zip -r aurora.blueprint conf.yml admin/ public/ LICENSE -x "*.git*" "*.md"

# Mover a Pterodactyl e instalar
cp aurora.blueprint /var/www/pterodactyl/
cd /var/www/pterodactyl
blueprint -install aurora
```

---

## ❌ Desinstalar

```bash
cd /var/www/pterodactyl
blueprint -remove aurora
```

---

## 🎨 Personalizar colores

Edita las variables CSS en `public/css/theme.css` y `admin/admin.css`:

```css
:root {
  --au-purple:   #8b5cf6;   /* Color primario */
  --au-teal:     #14b8a6;   /* Color secundario */
  --au-base:     #0d0d1a;   /* Fondo principal */
  --au-card:     #1c1c30;   /* Fondo de cards */
}
```

Después reconstruye:
```bash
blueprint -build aurora
```

---

## 🗂️ Estructura del proyecto

```
aurora/
├── conf.yml                      # Manifiesto Blueprint
├── admin/
│   ├── wrapper.blade.php         # Inyecta CSS en el admin <head>
│   └── admin.css                 # Estilos del panel de administración
├── public/
│   ├── views/wrapper.blade.php   # Inyecta CSS en el dashboard <head>
│   └── css/theme.css             # Estilos del dashboard del cliente
├── .github/workflows/release.yml # Auto-build del .blueprint en releases
├── LICENSE
└── README.md
```

---

## 📄 Licencia

MIT — libre para usar, modificar y distribuir.

---

<div align="center">
Hecho con 💜 · Inspirado en <a href="https://nebula.style">Nebula</a> · 100% gratis
</div>
