
# 📘 Módulo 1: Introducción a Angular

## ❓ ¿Qué es Angular?

Angular es un **framework frontend** de código abierto desarrollado por Google para construir aplicaciones web de una sola página (**SPA**, Single Page Applications). Utiliza **TypeScript** como lenguaje base y proporciona una arquitectura basada en componentes, inyección de dependencias, módulos y herramientas integradas para un desarrollo escalable y profesional.

---

## ✅ ¿Qué ofrece Angular?

- ✔️ Componentes reutilizables y modulares
- ✔️ Routing para navegación sin recargar la página
- ✔️ Sistema de módulos para estructurar proyectos grandes
- ✔️ Servicios e inyección de dependencias para compartir lógica
- ✔️ Soporte para formularios reactivos y por template
- ✔️ Observables y programación reactiva con RxJS
- ✔️ Herramientas de testing integradas
- ✔️ Soporte para internacionalización (i18n)
- ✔️ CLI oficial para productividad y automatización

---

## 🧠 Arquitectura básica de Angular

```plaintext
AppModule (app.module.ts)
 └── AppComponent (app.component.ts)
      ├── Otros componentes
      └── Servicios inyectados
```

Angular arranca desde el módulo raíz (`AppModule`) que declara el componente raíz (`AppComponent`). Desde ahí, se compone una jerarquía de componentes y servicios que forman la aplicación.

---

## 🔧 Instalación del entorno

### 1. Instalar Node.js

Descárgalo desde [https://nodejs.org](https://nodejs.org)

### 2. Instalar Angular CLI

```bash
npm install -g @angular/cli
```

### 3. Crear un nuevo proyecto Angular

```bash
ng new hola-angular
cd hola-angular
ng serve
```

Abre `http://localhost:4200` en tu navegador para ver la app en ejecución.

---

## 🗂️ Estructura inicial del proyecto

| Carpeta / Archivo           | Descripción                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| `src/`                      | Código fuente de la aplicación                                              |
| `src/app/`                  | Componentes, módulos y servicios de la app                                  |
| `app.module.ts`             | Módulo principal que agrupa toda la app                                     |
| `app.component.ts`          | Componente raíz que inicia la aplicación                                    |
| `app.component.html`        | Plantilla HTML del componente raíz                                          |
| `main.ts`                   | Punto de entrada de la app que arranca el módulo raíz                       |
| `angular.json`              | Configuración general del proyecto (build, estilos, rutas, etc.)            |

---

## 🧩 Crear un componente con Angular CLI

```bash
ng generate component saludo
```

Esto crea:

- `saludo.component.ts`: lógica del componente
- `saludo.component.html`: plantilla (vista)
- `saludo.component.css`: estilos asociados
- `saludo.component.spec.ts`: archivo para pruebas unitarias

El componente queda registrado automáticamente en `app.module.ts`.

---

## 🧠 Fundamentos internos de Angular

### 🔹 Motor de renderizado y detección de cambios

Angular usa su propio motor para analizar cambios en los datos y actualizar el DOM. Cada componente tiene un "contexto" que se evalúa automáticamente cuando ocurren eventos (clicks, cambios en inputs, etc.) gracias al sistema de **Change Detection**.

### 🔹 ¿Qué es Zone.js?

Angular usa `Zone.js` para detectar cuándo cambian los datos. Esta librería "intercepta" eventos asíncronos como `setTimeout`, `promesas`, eventos del DOM, etc., y fuerza a Angular a comprobar si debe actualizar la vista.

### 🔹 Compilación AOT vs JIT

- **JIT (Just In Time)**: compila la app en el navegador (usado durante desarrollo).
- **AOT (Ahead Of Time)**: compila la app antes de cargarla (usado en producción para mejor rendimiento).

### 🔹 Monorepos y múltiples aplicaciones

Angular permite gestionar varios proyectos dentro del mismo workspace, útil para apps grandes con paneles administrativos, sitios públicos y librerías compartidas.

### 🔹 Herramientas modernas de desarrollo

- **ESLint**: ayuda a mantener un código limpio y sin errores.
- **Prettier**: formateador automático de código.
- **Husky + commitlint**: controlan los commits antes de que lleguen al repositorio.
- **Vitest o Jest**: opciones modernas para testing más rápido que Jasmine/Karma.

### 🔹 Buenas prácticas desde el inicio

- Nombrar carpetas y archivos de forma coherente.
- Separar bien la lógica de negocio del HTML.
- Usar interfaces TypeScript para definir estructuras de datos.
- Comenzar organizando el proyecto por módulos desde el principio.

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### 📘 - Módulo 2 [➡️](../Modulo_2_Componentes_y_Data_Binding/Modulo_2.md)

### 🏠 - [Volver al Inicio](../README.md)


