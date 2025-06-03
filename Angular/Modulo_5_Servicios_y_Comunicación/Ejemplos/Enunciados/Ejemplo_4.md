
# 🧪 Ejemplo 4: Servicio con lógica para carrito

## 🎯 Objetivo
Encapsular la lógica del carrito de compras en un servicio inyectable que permita agregar y mostrar productos en cualquier componente.

---

## 📁 Ruta: src/app/carrito/carrito.service.ts
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

---

## 📁 Ruta: src/app/carrito/carrito.component.ts
```ts
import { Component } from '@angular/core';
import { CarritoService } from './carrito.service';

@Component({
  selector: 'app-carrito',
  templateUrl: './carrito.component.html'
})
export class CarritoComponent {
  constructor(public carritoService: CarritoService) {}
}
```

---

## 📁 Ruta: src/app/carrito/carrito.component.html
```html
<ul>
  <li *ngFor="let item of carritoService.carrito">
    {{ item.nombre }} - ${{ item.precio }}
  </li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo utiliza un **servicio (`CarritoService`)** para almacenar productos agregados al carrito y acceder a ellos desde un componente.

- El servicio mantiene el array de productos (`carrito`) y provee métodos para manipularlo.
- El componente inyecta el servicio y accede a los datos directamente para mostrarlos en la vista.
- Permite que cualquier componente pueda reutilizar la lógica del carrito sin duplicación de código.

---

## 🧠 Conceptos aplicados

- Creación de servicios con `@Injectable`
- Inyección de dependencias
- Patrón singleton para compartir estado
- Directiva `*ngFor` para mostrar contenido dinámico

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar método para eliminar productos del carrito

```ts
eliminar(index: number) {
  this.carrito.splice(index, 1);
}
```

📌 **¿Por qué?**: Permite gestionar mejor los elementos del carrito, añadiendo control total desde el componente.

---

### ✅ 2. Mostrar mensaje si el carrito está vacío

```html
<p *ngIf="carritoService.carrito.length === 0">El carrito está vacío.</p>
```

📌 **¿Por qué?**: Mejora la experiencia de usuario mostrando mensajes adecuados según el estado del carrito.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Declara `CarritoService` en el `providers` del módulo (o usa `providedIn: 'root'` como en el ejemplo).
2. Añade el componente con `<app-carrito></app-carrito>` en la plantilla principal.
3. Crea un botón o lógica que use `carritoService.agregar(...)` para añadir productos y visualízalos en el HTML.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)

