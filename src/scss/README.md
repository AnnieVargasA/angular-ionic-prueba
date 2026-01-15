# Arquitectura 7-1 SCSS

Estructura de estilos implementada siguiendo la metodología 7-1 Pattern.

## Estructura

```
src/scss/
├── abstracts/          # Variables, mixins, funciones
│   ├── _variables.scss
│   ├── _mixins.scss
│   └── _functions.scss
├── base/               # Estilos base y reset
│   ├── _reset.scss
│   ├── _typography.scss
│   └── _helpers.scss
├── components/         # Componentes reutilizables
│   ├── _buttons.scss
│   └── _cards.scss
├── layout/             # Estructura principal
│   ├── _header.scss
│   └── _footer.scss
├── pages/              # Estilos específicos de páginas
│   └── _home.scss
├── themes/             # Temas de color
│   └── _default.scss
├── vendors/            # Sobrescrituras de librerías
│   └── _ionic-overrides.scss
└── main.scss           # Archivo principal que importa todo
```

## Uso

Los estilos se importan automáticamente en `global.scss`:

```scss
@import 'scss/main.scss';
```

## Orden de importación

1. **abstracts/** - Herramientas sin salida CSS
2. **vendors/** - CSS de terceros
3. **base/** - Reset y estilos fundamentales
4. **layout/** - Estructura de la aplicación
5. **components/** - Componentes individuales
6. **pages/** - Estilos específicos de páginas
7. **themes/** - Temas y variaciones

## Agregar nuevos archivos

Para agregar un nuevo archivo SCSS:

1. Crea el archivo en la carpeta correspondiente con `_` al inicio (ej: `_mycomponent.scss`)
2. Impórtalo en `main.scss` en la sección correspondiente:
   ```scss
   @import 'components/mycomponent';
   ```

## Variables disponibles

Variables principales definidas en `abstracts/_variables.scss`:

- **Colores**: `$primary-color`, `$secondary-color`, `$success-color`, etc.
- **Espaciado**: `$spacing-xs`, `$spacing-sm`, `$spacing-md`, `$spacing-lg`, `$spacing-xl`
- **Breakpoints**: `$breakpoint-xs`, `$breakpoint-sm`, `$breakpoint-md`, `$breakpoint-lg`, `$breakpoint-xl`
- **Tipografía**: `$font-family-base`, `$font-size-base`, etc.

## Mixins disponibles

Mixins útiles en `abstracts/_mixins.scss`:

- `@include respond-to('medium')` - Media queries
- `@include flex-center` - Centrar con flexbox
- `@include truncate` - Truncar texto
- `@include box-shadow(2)` - Sombras

## Funciones disponibles

Funciones en `abstracts/_functions.scss`:

- `rem(16)` - Convertir px a rem
- `spacing(2)` - Calcular espaciado
