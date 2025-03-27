[![isotipo.png](https://i.postimg.cc/ZKjJr2r9/isotipo.png)](https://postimg.cc/2VbpYH9m)

# Estructura para Proyectos con ReactJs 🚀

Este documento establece los lineamientos para estructurar y desarrollar proyectos frontend con ReactJS. Su objetivo es garantizar la consistencia, escalabilidad y mantenibilidad del código, promoviendo buenas prácticas y un enfoque modular.

---

## Estructura de Carpetas

La estructura del proyecto está diseñada para fomentar la organización y la separación de responsabilidades:

```
src/
├── adapters/
│   ├── index.ts
│   └── userAdapter.ts
├── components/
│   ├── UserComponent.jsx
│   └── AdminComponent.jsx
├── models/
│   └── userModel.ts
├── hooks/
│   ├── useUser.ts
│   └── useAdmin.ts
├── services/
│   └── userService.ts
├── utilities/
│   └── formatter.ts
├── contexts/
│   └── UserContext.ts
└── pages/
    └── home/
        ├── adapters/
        │   ├── home.index.ts
        │   └── home.userAdapter.ts
        ├── page.jsx
        ├── components/
        │   └── home.HomeButton.jsx
        ├── models/
        │   └── home.homeModel.ts
        ├── hooks/
        │   └── home.useHomeLogic.ts
        ├── services/
        │   └── home.homeService.ts
        └── utilities/
            └── home.homeFormatter.ts
```

### Detalles de las Carpetas

- **`adapters/`**: Contiene funciones o clases que transforman datos entre diferentes capas o formatos.
- **`components/`**: Componentes reutilizables en toda la aplicación, como botones, modales o formularios genéricos.
- **`models/`**: Define las estructuras de datos utilizadas en la aplicación.
- **`hooks/`**: Hooks personalizados que encapsulan lógica reutilizable, como manejo de formularios o peticiones HTTP.
- **`services/`**: Contiene la lógica para interactuar con APIs o servicios externos.
- **`utilities/`**: Funciones auxiliares como formateadores, validadores o cálculos comunes.
- **`contexts/`**: Implementa el manejo de estado global utilizando React Context API.
- **`pages/`**: Cada página encapsula su lógica, componentes y recursos específicos.

---

## Principios de Organización

### 1. **Regla del Alcance**
- **Componentes Globales**: Los componentes en `components/` deben ser reutilizables en toda la aplicación. Ejemplo: botones genéricos, encabezados, etc.
- **Componentes Específicos**: Los componentes dentro de una funcionalidad específica (por ejemplo, `app/home/components/`) solo deben ser utilizados en su contexto. Esto asegura que cada página sea autónoma y fácil de mantener.

### 2. **Patrón Contenedor**
El patrón contenedor encapsula los componentes, lógica y recursos específicos de una funcionalidad dentro de su propia subcarpeta. Esto fomenta la modularidad y la separación de responsabilidades.

Ejemplo para la página `home`:

```
src/
└── pages/
    └── home/
        ├── page.jsx         # Contenedor principal
        ├── components/      # Componentes específicos de Home
        │   └── home.HomeButton.jsx
        ├── models/          # Modelos usados en Home
        │   └── home.model.js
        ├── hooks/           # Hooks específicos de Home
        │   └── home.useHomeLogic.js
        ├── services/        # Servicios usados por Home
        │   └── home.service.js
        └── utilities/       # Funciones auxiliares para Home
            └── home.formatter.js
```

### 3. **Convenciones de Nomenclatura**
Para mantener la consistencia en el proyecto, se deben seguir estas convenciones:

- **Carpetas**: `kebab-case` (ejemplo: `user-profile`).
- **Archivos**: `camelCase` (ejemplo: `userService.ts`).
- **Componentes**: `PascalCase` (ejemplo: `UserComponent.jsx`).
- **Prefijos Contextuales**: Los archivos dentro de un contexto deben llevar el nombre del contexto como prefijo (ejemplo: `home.HomeButton.jsx` en `pages/home/components/`).


---
## Lineamientos Adicionales
1. **Reglas generales en el desarrollo**
   [Lineamientos Frontend](https://apuestatotal.atlassian.net/wiki/x/AoClBg)

2. **Estilo de Código JavaScript**:  
   El código JavaScript debe seguir la guía de estilo de [StandardJS](https://standardjs.com/readme-esla). Esto asegura un código limpio, consistente y fácil de mantener.

3. **Estilo de CSS con Tailwind**:  
   El CSS debe escribirse utilizando [TailwindCSS](https://tailwindcss.com/), y se debe habilitar la funcionalidad de ordenamiento automático de clases con Prettier. Más información aquí:  
   [Ordenamiento Automático de Clases con Prettier](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier#how-classes-are-sorted).

---

## Extensiones Recomendadas para Visual Studio Code

### Obligatorias
- **Prettier**: Formateador de código ([Prettier](https://prettier.io/)).
- **ESLint**: Identificación y corrección de problemas en JavaScript ([ESLint](https://eslint.org/)).
- **Error Lens**: Visualización de errores en línea ([Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)).
- **Tailwind CSS IntelliSense**: Herramientas inteligentes para Tailwind CSS ([Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)).

### Recomendadas
- **Image Preview**: Previsualización de imágenes en el editor ([Image Preview](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview)).
- **Version Lens**: Visualización de versiones en `package.json` ([Version Lens](https://marketplace.visualstudio.com/items?itemName=pflannery.vscode-versionlens)).
- **GitHub Copilot**: Asistente de código ([GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)).
- **Figma Dev Mode**: Integración con Figma ([Figma Dev Mode](https://marketplace.visualstudio.com/items?itemName=figma.figma-vscode-extension)).

---

## Recursos Adicionales

- [Guía Clean Code](https://slides.com/diegorodrigosamamesalazar/deck/fullscreen)
- [Guía de Estimación Frontend](https://apuestatotal.atlassian.net/wiki/x/C4BvBg)

---