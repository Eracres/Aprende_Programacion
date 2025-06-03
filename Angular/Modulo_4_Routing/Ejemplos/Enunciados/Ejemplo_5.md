# 🧪 Ejemplo 5: Página 404 personalizada

## 🎯 Objetivo
Implementar un componente que actúe como página de error para rutas no definidas, usando la ruta comodín `**`.

---

## 📁 Ruta: src/app/not-found/not-found.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-not-found',
  templateUrl: './not-found.component.html'
})
export class NotFoundComponent {}
```

---

## 📁 Ruta: src/app/not-found/not-found.component.html

```html
<h2>Página no encontrada 😢</h2>
<a routerLink="/">Volver al inicio</a>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo crea un componente para manejar rutas inválidas en la aplicación.  
Se asocia a la ruta comodín `**` en `app-routing.module.ts`, que captura cualquier URL no reconocida y muestra una página de error personalizada.  
Esto mejora la experiencia del usuario al navegar por rutas inexistentes.

---

## 🧠 Conceptos aplicados

- Uso de rutas comodín (`path: '**'`)
- Manejo de rutas no definidas
- Componente personalizado de error
- Navegación con `routerLink`

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar un botón visual con routerLink

📁 Ruta: src/app/not-found/not-found.component.html

```html
<button routerLink="/">Volver al inicio</button>
```

📌 **¿Por qué?**: Mejora la accesibilidad y la interacción del usuario al ofrecer una navegación clara.

---

### ✅ 2. Mostrar un diseño más visual con íconos o animaciones

```html
<h2>❌ Error 404 - Página no encontrada</h2>
<img src="assets/404.svg" alt="Página no encontrada">
```

📌 **¿Por qué?**: Una interfaz más llamativa hace que el error sea más comprensible y menos frustrante para el usuario.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener una ruta comodín (`{ path: '**', component: NotFoundComponent }`) en tu `app-routing.module.ts`.
2. Navega manualmente a una ruta inexistente, como `/no-existe`.
3. Verifica que el componente de error se muestra correctamente y el enlace o botón funciona.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md)

### 🏠 - [Inicio](../../../README.md)

