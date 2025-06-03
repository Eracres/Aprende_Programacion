# 🧪 Ejemplo 2: Uso de `<router-outlet>`

## 🎯 Objetivo
Aprender a utilizar la directiva `<router-outlet>` para renderizar dinámicamente los componentes según la ruta activa definida en el enrutador.

---

## 📁 Ruta: src/app/app.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
  title = 'Mi App Angular';
}
```

---

## 📁 Ruta: src/app/app.component.html

```html
<h1>{{ title }}</h1>
<router-outlet></router-outlet>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo utilizar `<router-outlet>` en la plantilla principal (`app.component.html`).  
Angular reemplazará esta etiqueta con el componente correspondiente a la ruta activa.  
De esta forma se crea una navegación dinámica, donde el contenido cambia sin recargar la página.

---

## 🧠 Conceptos aplicados

- Directiva estructural `<router-outlet>` de Angular
- Renderizado condicional de componentes por ruta
- Separación de layout estático y contenido dinámico

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar navegación entre rutas

📁 Ruta: src/app/app.component.html

```html
<nav>
  <a routerLink="/">Inicio</a>
  <a routerLink="/acerca">Acerca</a>
</nav>
<router-outlet></router-outlet>
```

📌 **¿Por qué?**: Permite al usuario navegar entre rutas sin recargar la página usando `routerLink`.

---

### ✅ 2. Colocar `<router-outlet>` dentro de un layout principal

📁 Ruta: src/app/app.component.html

```html
<header>Cabecera fija</header>
<main>
  <router-outlet></router-outlet>
</main>
<footer>Pie de página</footer>
```

📌 **¿Por qué?**: Facilita mantener una estructura de layout fija en la aplicación y cambiar solo el contenido central.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener rutas definidas en `AppRoutingModule`.
2. Usa `routerLink` para navegar entre componentes.
3. El contenido dinámico debe renderizarse justo donde está `<router-outlet>`.
4. El componente por defecto debe cargarse al abrir la raíz `/`.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)  
### 🏠 - [Inicio](../../../README.md)

