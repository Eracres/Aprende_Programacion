# 📋 Ejercicio 6: Crear navegación con parámetros (por ID)

## 🎯 Objetivo
Implementar rutas dinámicas que usen parámetros, como `/producto/:id`.

---

## 📝 Instrucciones
1. Crea un componente `ProductoComponent`:

```bash
ng generate component producto
```

3. Agrega una ruta con parámetro `id`:

```ts
{ path: 'producto/:id', component: ProductoComponent }
```

5. Usa `ActivatedRoute` para mostrar el valor del ID en pantalla.

6. Agrega enlaces de prueba como:

7. `<a [routerLink]="['/producto', 1]">Ver Producto 1</a>`

---

## ✅ Criterios de evaluación
- El parámetro `id` se captura correctamente.
- La navegación muestra datos dinámicos.
- La sintaxis `[routerLink]` es utilizada correctamente.

---

## 🔁 Navegación

### 📋 -  [⬅️](./Ejercicio_5.md) Ejercicio 5 - Modulo 5 [➡️](../../../Modulo_5_Servicios_y_Comunicación/Modulo_5.md)

### 📋 - [Volver a Ejercicios](../README.md)

### 🧪 - [Ir a Ejemplos](../../Ejemplos/README.md) 

### 📘 - [Volver a Módulo 4](../../Modulo_4.md) 

### 🏠 - [Inicio](../../../README.md)
