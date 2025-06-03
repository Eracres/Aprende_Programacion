# 📘 Módulo 9: Autenticación con JWT

## ❓ ¿Qué es JWT?

JWT (**JSON Web Token**) es un estándar abierto que permite la transmisión segura de información entre partes como un objeto JSON.  
Se utiliza comúnmente para **autenticación y autorización** en aplicaciones web.

Un JWT típicamente contiene tres partes codificadas en base64:
1. **Header** – Tipo de token y algoritmo de firma
2. **Payload** – Datos del usuario y claims
3. **Signature** – Firma digital para verificar integridad

---

## 👤 ¿Cómo funciona la autenticación con JWT?

1. El usuario ingresa sus credenciales.
2. El servidor las valida y responde con un **token JWT**.
3. El cliente guarda el token (usualmente en `localStorage` o `sessionStorage`).
4. El token se incluye en futuras peticiones como encabezado `Authorization: Bearer`.

---

## 🛠️ Simulación de autenticación en Angular

Aunque no tengamos un backend real, podemos **simular el login** y protección de rutas con Angular:

### ✅ AuthService – Login simulado
```ts
import { Injectable } from '@angular/core';

@Injectable({ providedIn: 'root' })
export class AuthService {
  login(email: string, password: string): void {
    localStorage.setItem('token', 'falso-token');
  }

  logout(): void {
    localStorage.removeItem('token');
  }

  estaAutenticado(): boolean {
    return !!localStorage.getItem('token');
  }
}
```

---

### ✅ AuthGuard – Protección de rutas
```ts
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from './auth.service';

@Injectable({ providedIn: 'root' })
export class AuthGuard implements CanActivate {
  constructor(private auth: AuthService, private router: Router) {}

  canActivate(): boolean {
    if (this.auth.estaAutenticado()) {
      return true;
    }
    this.router.navigate(['/login']);
    return false;
  }
}
```

---

## 🔒 ¿Cómo proteger rutas en Angular?

```ts
const routes: Routes = [
  { path: 'dashboard', component: DashboardComponent, canActivate: [AuthGuard] }
];
```

Esto impide que usuarios no autenticados accedan a `dashboard`.

---

## 📄 ¿Dónde guardar el token?

- `localStorage`: persiste después de recargar
- `sessionStorage`: se borra al cerrar el navegador

> ⚠️ ¡Nunca guardes información sensible directamente en el token o en localStorage!

---

## 💬 ¿Cómo se vería un flujo completo?

1. Usuario rellena un formulario de login.
2. `AuthService.login()` guarda el token en localStorage.
3. `AuthGuard` impide el acceso a rutas si no hay token.
4. `logout()` borra el token y redirige al login.

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_8_Pipes_y_Personalizados/Modulo_8.md) Módulo 8 - Módulo 10 [➡️](../Modulo_10_HTTPClient/Modulo_10.md)

### 🏠 [Inicio](../README.md)
