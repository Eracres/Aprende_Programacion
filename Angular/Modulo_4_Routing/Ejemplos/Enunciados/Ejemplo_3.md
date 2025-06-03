# 🧪 Ejemplo 3: Navegación con routerLink

## 🎯 Objetivo
Configurar enlaces de navegación en la plantilla usando `routerLink` para cambiar de ruta sin recargar la página.

## 📁 Ruta: src/app/app.component.html
```html
<nav>
  <a routerLink="/">Inicio</a>
  <a routerLink="/acerca">Acerca</a>
</nav>
<router-outlet></router-outlet>
```

## 📁 Ruta: src/app/app.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {}
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo muestra cómo usar el atributo `routerLink` en enlaces HTML para navegar entre rutas definidas en la aplicación Angular.  
Permite cambiar de vista sin recargar la página, lo que mantiene la experiencia tipo SPA (Single Page Application).

Los enlaces apuntan a rutas configuradas previamente en `app-routing.module.ts`.  
El componente `<router-outlet>` es donde se carga dinámicamente el contenido asociado a cada ruta.

---

## 🧠 Conceptos aplicados

- Enlace de rutas con `routerLink`
- Navegación sin recarga con Angular Router
- Uso del `<router-outlet>` como contenedor de vistas

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar clase activa a enlaces
```html
<a routerLink="/acerca" routerLinkActive="activo">Acerca</a>
```
📌 **¿Por qué?**: Para resaltar visualmente el enlace activo mediante estilos CSS.

---

### ✅ 2. Incluir más enlaces
```html
<a routerLink="/contacto">Contacto</a>
<a routerLink="/servicios">Servicios</a>
```
📌 **¿Por qué?**: Permite una navegación más completa en aplicaciones con múltiples vistas.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Haz clic en los enlaces "Inicio" o "Acerca".
2. Verifica que el contenido cambia sin recargar la página.
3. Comprueba que `<router-outlet>` muestra el componente correcto según la ruta.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md)

### 🏠 - [Inicio](../../../README.md)


