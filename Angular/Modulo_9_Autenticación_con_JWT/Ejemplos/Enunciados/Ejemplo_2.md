# 🧪 Ejemplo 2: Guardar token en localStorage

## 🎯 Objetivo
Persistir un token de autenticación en el navegador usando `localStorage`.

## 📁 Ruta: src/app/servicios/auth.service.ts
```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class AuthService {
  login(): void {
    const token = 'token-de-prueba';
    localStorage.setItem('token', token);
  }
}
```

---

## ✅ ¿Qué hace este ejemplo?
Al llamar al método `login`, el token de prueba se guarda localmente.  
Esto permite que Angular lo lea después para validar autenticaciones o proteger rutas.

---

## 🧠 Conceptos aplicados

- Uso del localStorage en Angular
- Persistencia de sesión sin backend
- Servicios como contenedores de lógica

---

## 💡 Variaciones sugeridas

### ✅ Agregar expiración manual

```ts
login(): void {
  const tokenData = {
    token: 'token-de-prueba',
    expira: new Date().getTime() + 3600000
  };
  localStorage.setItem('token', JSON.stringify(tokenData));
}
```

📌 **¿Por qué?**: Puedes comprobar la validez del token más adelante con fecha de expiración.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Llama al método `login()` y revisa el almacenamiento del navegador.
2. Asegúrate de que se guarde el valor correctamente.
3. Elimina o cambia el token para simular cierre de sesión.

---

## 🔁 Navegación
### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 9](../../Modulo_9.md)
### 🏠 - [Inicio](../../../README.md)


