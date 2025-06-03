# 🧪 Ejemplo 4: Uso de servicio en componente

## 🎯 Objetivo
Demostrar cómo inyectar y utilizar un servicio personalizado en un componente para acceder y manipular datos compartidos, en este caso un carrito de compras.

## 📁 Ruta: src/app/servicios/carrito.service.ts
```ts
import { Injectable } from '@angular/core';

@Injectable({ providedIn: 'root' })
export class CarritoService {
  carrito: any[] = [];

  agregar(item: any) {
    this.carrito.push(item);
  }

  obtenerCarrito() {
    return this.carrito;
  }
}
```

## 📁 Ruta: src/app/carrito/carrito.component.ts
```ts
import { Component } from '@angular/core';
import { CarritoService } from '../servicios/carrito.service';

@Component({
  selector: 'app-carrito',
  templateUrl: './carrito.component.html'
})
export class CarritoComponent {
  constructor(public carritoService: CarritoService) {}
}
```

## 📁 Ruta: src/app/carrito/carrito.component.html
```html
<h3>Productos en el carrito:</h3>
<ul>
  <li *ngFor="let item of carritoService.carrito">
    {{ item.nombre }} - ${{ item.precio }}
  </li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo ilustra cómo inyectar un servicio (`CarritoService`) en un componente para gestionar datos compartidos, como el contenido de un carrito de compras.  
El servicio actúa como una fuente única de verdad que persiste mientras la app esté en funcionamiento.

---

## 🧠 Conceptos aplicados

- Inyección de dependencias en Angular
- Uso de `providedIn: 'root'` para servicios globales
- Acceso a propiedades y métodos del servicio desde el componente
- Visualización de datos compartidos usando `*ngFor`

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar botón para añadir productos desde el componente
```html
<button (click)="carritoService.agregar({ nombre: 'Producto X', precio: 9.99 })">
  Añadir Producto X
</button>
```
📌 **¿Por qué?**: Permite que el usuario interactúe directamente con el carrito.

---

### ✅ 2. Añadir método para eliminar elementos del carrito
```ts
eliminar(indice: number) {
  this.carrito.splice(indice, 1);
}
```

```html
<li *ngFor="let item of carritoService.carrito; let i = index">
  {{ item.nombre }} - ${{ item.precio }}
  <button (click)="carritoService.carrito.splice(i, 1)">Eliminar</button>
</li>
```

📌 **¿Por qué?**: Mejora la funcionalidad permitiendo gestionar los ítems.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Comprueba que el componente muestra correctamente los elementos del carrito.
2. Usa botones para añadir nuevos productos y verificar que se renderizan.
3. Añade el servicio al constructor e intenta acceder desde la plantilla.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 7](../../Modulo_7.md)  
### 🏠 - [Inicio](../../../README.md)
