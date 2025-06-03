# 📋 Ejercicio 5: Redirigir ruta vacía a /inicio

## 🎯 Objetivo
Configurar una redirección automática cuando la ruta está vacía.

---

## 📝 Instrucciones
1. En `app-routing.module.ts`, agrega esta entrada antes de cualquier otra:

```ts
{ path: '', redirectTo: '/inicio', pathMatch: 'full' }
```

3. Verifica que acceder a `/` redirige a `/inicio` correctamente.

---

## ✅ Criterios de evaluación
- La redirección está definida correctamente.
- Se usa `pathMatch: 'full'` para evitar conflictos.
- No hay errores al acceder a la ruta raíz.


---

## 🔁 Navegación

### 📋 - [⬅️](./Ejercicio_4.md) Ejercicio 4 - Ejercicio 6 [➡️](./Ejercicio_6.md)

### 📋 - [Volver a Ejercicios](../README.md)

### 🧪 - [Ir a Ejemplos](../../Ejemplos/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md) 

### 🏠 - [Inicio](../../../README.md)
