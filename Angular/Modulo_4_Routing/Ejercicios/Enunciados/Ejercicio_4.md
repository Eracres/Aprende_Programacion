# 📋 Ejercicio 4: Configurar una ruta 404

## 🎯 Objetivo
Practicar la configuración de una ruta comodín `**` para mostrar una página 404 personalizada.

---

## 📝 Instrucciones
1. Crea un componente llamado `NotFoundComponent`:

```bash
ng generate component not-found
```

3. Agrega esta ruta al final del arreglo en `app-routing.module.ts`:

```ts
{ path: '**', component: NotFoundComponent }
```

5. Incluye un mensaje y un enlace de retorno en la plantilla HTML.

---

## ✅ Criterios de evaluación
- La ruta comodín está correctamente definida.
- La página 404 aparece cuando la ruta no existe.
- Contiene un botón para volver al inicio.

---

## 🔁 Navegación

### 📋 - [⬅️](./Ejercicio_3.md) Ejercicio 3 - Ejercicio 5 [➡️](./Ejercicio_5.md)

### 📋 - [Volver a Ejercicios](../README.md)

### 🧪 - [Ir a Ejemplos](../../Ejemplos/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md) 

### 🏠 - [Inicio](../../../README.md)
