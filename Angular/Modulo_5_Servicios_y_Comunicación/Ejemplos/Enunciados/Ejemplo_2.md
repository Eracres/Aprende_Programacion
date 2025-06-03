# 🧪 Ejemplo 2: Inyección de servicio en componente

## 🎯 Objetivo
Aprender cómo inyectar un servicio dentro de un componente y utilizarlo para obtener datos.

---

## 📁 Ruta: src/app/productos/productos.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { ProductoService } from '../servicios/producto.service';

@Component({
  selector: 'app-productos',
  templateUrl: './productos.component.html'
})
export class ProductosComponent implements OnInit {
  productos = [];

  constructor(private productoService: ProductoService) {}

  ngOnInit() {
    this.productos = this.productoService.obtenerProductos();
  }
}
```

---

## 📁 Ruta: src/app/productos/productos.component.html
```html
<ul>
  <li *ngFor="let prod of productos">{{ prod.nombre }} - ${{ prod.precio }}</li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo **inyectar un servicio** en un componente Angular para consumir datos.  
Cuando el componente se inicializa (`ngOnInit`), invoca el método del servicio `obtenerProductos()` y lo asigna a la propiedad `productos`, que luego se renderiza en una lista mediante `*ngFor`.

---

## 🧠 Conceptos aplicados

- Inyección de dependencias en Angular
- Ciclo de vida del componente (`ngOnInit`)
- Renderizado de datos mediante `*ngFor`
- Separación de responsabilidades: lógica de datos en servicios

---

## 💡 Variaciones sugeridas

### ✅ 1. Filtrar productos por precio

```ts
ngOnInit() {
  const todos = this.productoService.obtenerProductos();
  this.productos = todos.filter(p => p.precio > 30);
}
```

📌 **¿Por qué?**: Permite mostrar solo productos relevantes según criterios personalizados.

---

### ✅ 2. Mostrar productos ordenados alfabéticamente

```ts
ngOnInit() {
  this.productos = this.productoService.obtenerProductos().sort((a, b) => a.nombre.localeCompare(b.nombre));
}
```

📌 **¿Por qué?**: Mejora la presentación visual y experiencia del usuario.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de que `ProductoService` esté bien declarado e importado.
2. Coloca el selector `<app-productos>` en el componente principal (`app.component.html`).
3. Comprueba que se muestran los datos al cargar la aplicación.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)

