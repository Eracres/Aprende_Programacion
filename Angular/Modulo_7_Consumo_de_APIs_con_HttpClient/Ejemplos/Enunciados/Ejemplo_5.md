# 🧪 Ejemplo 5: Mostrar datos en una lista con *ngFor

## 🎯 Objetivo
Utilizar un servicio para obtener datos desde una API y renderizarlos dinámicamente en el HTML mediante la directiva `*ngFor`.

## 📁 Ruta: src/app/services/producto.service.ts
```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class ProductoService {
  private apiUrl = 'https://fakestoreapi.com/products';

  constructor(private http: HttpClient) {}

  obtenerProductos(): Observable<any[]> {
    return this.http.get<any[]>(this.apiUrl);
  }
}
```

## 📁 Ruta: src/app/productos/productos.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { ProductoService } from '../services/producto.service';

@Component({
  selector: 'app-productos',
  templateUrl: './productos.component.html'
})
export class ProductosComponent implements OnInit {
  productos: any[] = [];

  constructor(private productoService: ProductoService) {}

  ngOnInit(): void {
    this.productoService.obtenerProductos().subscribe(data => {
      this.productos = data;
    });
  }
}
```

## 📁 Ruta: src/app/productos/productos.component.html
```html
<h2>Lista de productos</h2>
<ul>
  <li *ngFor="let producto of productos">
    {{ producto.title }} - {{ producto.price | currency }}
  </li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo conecta un componente con un servicio para **obtener productos de una API externa** y mostrarlos en la interfaz.  
La **directiva `*ngFor`** permite recorrer la lista de productos y renderizar cada uno como un elemento de la lista HTML.

---

## 🧠 Conceptos aplicados

- Servicios inyectables (`providedIn: 'root'`)
- Peticiones HTTP con `HttpClient`
- Enlace de datos asincrónico
- Directiva estructural `*ngFor`
- Pipes (`currency`) para formateo de datos

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar imagen de cada producto

📁 Ruta: src/app/productos/productos.component.html
```html
<li *ngFor="let producto of productos">
  <img [src]="producto.image" width="50" />
  {{ producto.title }} - {{ producto.price | currency }}
</li>
```
📌 **¿Por qué?**: Enriquece visualmente la interfaz y facilita la identificación del producto.

---

### ✅ 2. Agregar botón para recargar productos

📁 Ruta: src/app/productos/productos.component.html
```html
<button (click)="ngOnInit()">Recargar productos</button>
```
📌 **¿Por qué?**: Permite al usuario actualizar manualmente la lista.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Verifica que el servicio devuelva un array al hacer una petición HTTP.
2. Asegúrate de que los productos se muestren correctamente en la lista.
3. Prueba añadir un error de conexión y revisa cómo se comporta la vista.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 7](../../Modulo_7.md)

### 🏠 - [Inicio](../../../README.md)

