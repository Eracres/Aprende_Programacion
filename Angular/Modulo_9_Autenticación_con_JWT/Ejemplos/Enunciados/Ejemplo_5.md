# 🧪 Ejemplo 5: Ocultar enlaces si no hay token

## 🎯 Objetivo
Mostrar u ocultar elementos del menú de navegación según si el usuario está autenticado (es decir, si existe un token en localStorage).

## 📁 Ruta: src/app/navbar/navbar.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-navbar',
  templateUrl: './navbar.component.html'
})
export class NavbarComponent {
  get autenticado(): boolean {
    return !!localStorage.getItem('token');
  }
}
```

## 📁 Ruta: src/app/navbar/navbar.component.html
```html
<nav>
  <a routerLink="/">Inicio</a>
  <a routerLink="/dashboard" *ngIf="autenticado">Dashboard</a>
  <a routerLink="/login" *ngIf="!autenticado">Iniciar sesión</a>
  <a (click)="logout()" *ngIf="autenticado">Cerrar sesión</a>
</nav>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo controlar la visibilidad de enlaces en la navegación según si el usuario tiene un token almacenado.  
El método `autenticado` verifica si existe un token en `localStorage` y en función de eso se renderizan los enlaces con `*ngIf`.

---

## 🧠 Conceptos aplicados

- Uso de `localStorage` para gestionar estado de sesión
- Evaluación de expresión booleana con `!!`
- Directiva estructural `*ngIf` para mostrar u ocultar elementos
- Seguridad en navegación

---

## 💡 Variaciones sugeridas

### ✅ 1. Extraer la lógica a un servicio

```ts
get autenticado(): boolean {
  return this.authService.estaAutenticado();
}
```

📌 **¿Por qué?**: Mantiene la lógica centralizada y reutilizable.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de que el token no exista en `localStorage` y observa que solo aparece "Inicio" e "Iniciar sesión".
2. Ejecuta `localStorage.setItem('token', 'falso')` desde la consola y recarga.
3. Verifica que ahora se muestra el enlace a "Dashboard" y "Cerrar sesión".

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 9](../../Modulo_9.md)

### 🏠 - [Inicio](../../../README.md)

