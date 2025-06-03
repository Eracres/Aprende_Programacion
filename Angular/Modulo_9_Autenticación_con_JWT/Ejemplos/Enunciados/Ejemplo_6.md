# 🧪 Ejemplo 6: Cerrar sesión y limpiar token

## 🎯 Objetivo
Implementar una función de cierre de sesión que elimine el token almacenado y redirija al usuario a la página de login.

## 📁 Ruta: src/app/servicios/auth.service.ts
```ts
import { Injectable } from '@angular/core';
import { Router } from '@angular/router';

@Injectable({
  providedIn: 'root'
})
export class AuthService {

  constructor(private router: Router) {}

  logout() {
    localStorage.removeItem('token');
    this.router.navigate(['/login']);
  }

  estaAutenticado(): boolean {
    return !!localStorage.getItem('token');
  }
}
```

## 📁 Ruta: src/app/navbar/navbar.component.ts
```ts
import { Component } from '@angular/core';
import { AuthService } from '../servicios/auth.service';

@Component({
  selector: 'app-navbar',
  templateUrl: './navbar.component.html'
})
export class NavbarComponent {
  constructor(private authService: AuthService) {}

  cerrarSesion() {
    this.authService.logout();
  }
}
```

## 📁 Ruta: src/app/navbar/navbar.component.html
```html
<nav>
  <a routerLink="/dashboard">Dashboard</a>
  <button (click)="cerrarSesion()">Cerrar sesión</button>
</nav>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo implementa un botón que, al hacer clic, llama a `logout()` del servicio `AuthService`, eliminando el token del `localStorage` y redirigiendo al usuario a `/login`.

---

## 🧠 Conceptos aplicados

- Eliminación de datos en `localStorage`
- Navegación programática con `Router`
- Control de sesión en servicios
- Separación de responsabilidades: vista y lógica

---

## 💡 Variaciones sugeridas

### ✅ Mostrar el botón solo si el usuario está autenticado
```html
<button *ngIf="authService.estaAutenticado()" (click)="cerrarSesion()">Cerrar sesión</button>
```

📌 **¿Por qué?**: Para mejorar la experiencia de usuario y evitar mostrar acciones innecesarias si el usuario ya ha cerrado sesión.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Inicia sesión y asegúrate de que se almacena un token.
2. Haz clic en el botón “Cerrar sesión”.
3. Comprueba que el token ha sido eliminado del `localStorage`.
4. Verifica que la redirección al login funciona correctamente.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 9](../../Modulo_9.md)

### 🏠 - [Inicio](../../../README.md)
