# 🧪 Ejemplo 2: Servicio básico con GET

## 🎯 Objetivo
Crear un servicio en Angular que realice una petición GET a una API externa utilizando `HttpClient`.

---

## 📁 Ruta: src/app/app.module.ts
```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, HttpClientModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

---

## 📁 Ruta: src/app/servicios/producto.service.ts
```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({ providedIn: 'root' })
export class ProductoService {
  private apiUrl = 'https://fakestoreapi.com/products';

  constructor(private http: HttpClient) {}

  obtenerProductos(): Observable<any> {
    return this.http.get(this.apiUrl);
  }
}
```

---

## 📁 Ruta: src/app/app.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { ProductoService } from './servicios/producto.service';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent implements OnInit {
  productos: any[] = [];

  constructor(private productoService: ProductoService) {}

  ngOnInit(): void {
    this.productoService.obtenerProductos().subscribe((data) => {
      this.productos = data;
    });
  }
}
```

---

## 📁 Ruta: src/app/app.component.html
```html
<h2>Listado de productos</h2>
<ul>
  <li *ngFor="let producto of productos">{{ producto.title }}</li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo define un servicio llamado `ProductoService` que utiliza `HttpClient` para realizar una petición GET a una API externa.  
El `AppComponent` consume este servicio al inicializarse (`ngOnInit`) y muestra el listado de productos obtenidos.

---

## 🧠 Conceptos aplicados

- Creación e inyección de servicios en Angular
- Uso de `HttpClient` para consumir APIs REST
- Petición HTTP de tipo GET
- Uso de `Observable` y suscripción con `subscribe`
- Ciclo de vida del componente (`ngOnInit`)
- Iteración con `*ngFor`

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar el precio junto al título

```html
<li *ngFor="let producto of productos">
  {{ producto.title }} - ${{ producto.price }}
</li>
```

📌 **¿Por qué?**: Agrega más contexto visual al usuario sobre cada producto.

---

### ✅ 2. Aplicar tipado fuerte al servicio

```ts
export interface Producto {
  id: number;
  title: string;
  price: number;
  description: string;
  image: string;
}

obtenerProductos(): Observable<Producto[]> {
  return this.http.get<Producto[]>(this.apiUrl);
}
```

📌 **¿Por qué?**: Mejora la legibilidad y ayuda con el autocompletado y validación en tiempo de compilación.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Ejecuta `ng serve` y abre `http://localhost:4200`.
2. Verifica que se muestra una lista de productos.
3. Revisa la pestaña de red en el navegador para confirmar la petición GET a la API.
4. Prueba a desconectar internet o cambiar la URL para simular errores.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 7](../../Modulo_7.md)

### 🏠 - [Inicio](../../../README.md)


