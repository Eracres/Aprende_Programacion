# 🧪 Ejemplo 1: Crear un servicio básico

## 🎯 Objetivo
Crear un servicio en Angular que encapsule la lógica para acceder a un listado de productos.

## 📁 Ruta: src/app/producto.service.ts
```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class ProductoService {
  productos = [
    { id: 1, nombre: 'Teclado', precio: 50 },
    { id: 2, nombre: 'Mouse', precio: 25 }
  ];

  obtenerProductos() {
    return this.productos;
  }
}
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo define un servicio llamado `ProductoService` que contiene una lista de productos y un método para devolverlos.  
Gracias a `providedIn: 'root'`, Angular inyecta este servicio automáticamente en toda la aplicación sin necesidad de registrarlo en `AppModule`.

---

## 🧠 Conceptos aplicados

- Creación de servicios con Angular CLI (`ng generate service`)
- Decorador `@Injectable()` para declarar servicios
- Inyección de dependencias
- Encapsulamiento de lógica de negocio

---

## 💡 Variaciones sugeridas

### ✅ 1. Devolver los productos como `Observable`

```ts
import { of } from 'rxjs';

obtenerProductos() {
  return of(this.productos);
}
```
📌 **¿Por qué?**: Esto permite trabajar de forma reactiva, como si viniera de una API real.

---

### ✅ 2. Añadir más propiedades a los productos

```ts
productos = [
  { id: 1, nombre: 'Teclado', precio: 50, stock: 20 },
  { id: 2, nombre: 'Mouse', precio: 25, stock: 15 },
  { id: 3, nombre: 'Monitor', precio: 200, stock: 5 }
];
```
📌 **¿Por qué?**: Mejora el ejemplo con una estructura de datos más completa.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de que `ProductoService` esté en la ruta indicada.
2. Inyéctalo en un componente con el constructor:  
   ```ts
   constructor(private productoService: ProductoService) {}
   ```
3. Llama al método `obtenerProductos()` y muestra los resultados por consola o en plantilla.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)

