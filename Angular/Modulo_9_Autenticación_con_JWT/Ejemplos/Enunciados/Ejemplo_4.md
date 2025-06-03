# 🧪 Ejemplo 4: Proteger ruta con AuthGuard

## 🎯 Objetivo
Implementar un guard (`AuthGuard`) para restringir el acceso a rutas protegidas si el usuario no está autenticado.

## 📁 Ruta: src/app/guards/auth.guard.ts
```ts
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from '../servicios/auth.service';

@Injectable({
  providedIn: 'root'
})
export class AuthGuard implements CanActivate {
  constructor(private auth: AuthService, private router: Router) {}

  canActivate(): boolean {
    if (this.auth.estaAutenticado()) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}
```

## 📁 Ruta: src/app/app-routing.module.ts
```ts
const routes: Routes = [
  { path: 'dashboard', component: DashboardComponent, canActivate: [AuthGuard] },
  { path: 'login', component: LoginComponent },
  { path: '**', redirectTo: 'login' }
];
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo crea un guard (`AuthGuard`) que impide el acceso a la ruta `/dashboard` si no hay un token válido.  
Utiliza el servicio `AuthService` para verificar si el usuario está autenticado.

---

## 🧠 Conceptos aplicados

- Implementación de `CanActivate`
- Protección de rutas en Angular
- Navegación condicional con `Router`
- Uso de servicios en guards

---

## 💡 Variaciones sugeridas

### ✅ Redirigir a una ruta personalizada según el rol
```ts
if (!this.auth.estaAutenticado()) {
  this.router.navigate(['/acceso-denegado']);
}
```
📌 **¿Por qué?**: Puedes mostrar una pantalla distinta en vez del login si quieres manejar permisos granulares.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Intenta navegar manualmente a `/dashboard` sin estar autenticado.
2. Asegúrate de que el guard redirige automáticamente a `/login`.
3. Prueba iniciar sesión y luego acceder correctamente a `/dashboard`.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 9](../../Modulo_9.md)  
### 🏠 - [Inicio](../../../README.md)
