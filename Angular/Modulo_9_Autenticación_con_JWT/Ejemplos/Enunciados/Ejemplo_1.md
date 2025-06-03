# 🧪 Ejemplo 1: Simular login con AuthService

## 🎯 Objetivo
Implementar un servicio de autenticación simulado que almacene un token falso en el localStorage al hacer login.

## 📁 Ruta: src/app/servicios/auth.service.ts
```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class AuthService {
  login(email: string, password: string): void {
    // Simulación de login
    localStorage.setItem('token', 'falso-token');
  }
}
```

---

## ✅ ¿Qué hace este ejemplo?
Este servicio simula un inicio de sesión sin conexión a un backend real.  
Al ejecutar `login()`, se guarda un token ficticio en `localStorage`.

---

## 🧠 Conceptos aplicados

- Creación de servicios en Angular
- Simulación de lógica de autenticación
- Uso del localStorage para persistencia de datos

---

## 💡 Variaciones sugeridas

### ✅ Validar credenciales ficticias

```ts
login(email: string, password: string): boolean {
  if (email === 'admin@angular.com' && password === '1234') {
    localStorage.setItem('token', 'falso-token');
    return true;
  }
  return false;
}
```

📌 **¿Por qué?**: Para controlar acceso con datos simulados.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Llama al método `login()` desde un componente.
2. Abre las herramientas del navegador y verifica que el token esté en el `localStorage`.
3. Comprueba que no se recarga la página ni hay errores.

---

## 🔁 Navegación
### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 9](../../Modulo_9.md)
### 🏠 - [Inicio](../../../README.md)


