# 🧪 Ejemplo 3: Verificar autenticación con método estaAutenticado

## 🎯 Objetivo
Implementar una función que determine si el usuario está autenticado revisando si hay token en el localStorage.

## 📁 Ruta: src/app/servicios/auth.service.ts
```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class AuthService {
  estaAutenticado(): boolean {
    return localStorage.getItem('token') !== null;
  }
}
```

---

## ✅ ¿Qué hace este ejemplo?
Este método comprueba si hay un token guardado y devuelve `true` o `false`.  
Esto permite condicionar acceso a rutas o mostrar/ocultar elementos en la interfaz.

---

## 🧠 Conceptos aplicados

- Validación de estado autenticado
- Acceso al `localStorage`
- Métodos de servicio reutilizables

---

## 💡 Variaciones sugeridas

### ✅ Verificar expiración del token

```ts
estaAutenticado(): boolean {
  const token = localStorage.getItem('token');
  // Agrega lógica para verificar expiración
  return token !== null;
}
```

📌 **¿Por qué?**: Para evitar aceptar tokens viejos o inválidos.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Agrega un botón en un componente para mostrar el resultado de `estaAutenticado()`.
2. Guarda y borra el token manualmente desde el navegador para probarlo.
3. Comprueba si cambia el valor retornado correctamente.

---

## 🔁 Navegación
### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 9](../../Modulo_9.md)
### 🏠 - [Inicio](../../../README.md)

