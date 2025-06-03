# 🧪 Ejemplo 6: Manejo de errores con catchError

## 🎯 Objetivo
Mostrar cómo capturar y manejar errores al consumir un servicio HTTP en Angular utilizando el operador `catchError` de RxJS.

## 📁 Ruta: src/app/servicios/producto.service.ts
```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable, catchError, throwError } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class ProductoService {
  private apiUrl = 'https://fakestoreapi.com/products';

  constructor(private http: HttpClient) {}

  obtenerProductos(): Observable<any> {
    return this.http.get(this.apiUrl).pipe(
      catchError(error => {
        console.error('Error al obtener productos:', error);
        return throwError(() => new Error('Error al obtener productos.'));
      })
    );
  }
}
```

## 📁 Ruta: src/app/productos/productos.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { ProductoService } from '../servicios/producto.service';

@Component({
  selector: 'app-productos',
  templateUrl: './productos.component.html'
})
export class ProductosComponent implements OnInit {
  productos: any[] = [];
  errorMensaje: string = '';

  constructor(private productoService: ProductoService) {}

  ngOnInit(): void {
    this.productoService.obtenerProductos().subscribe({
      next: datos => this.productos = datos,
      error: err => this.errorMensaje = err.message
    });
  }
}
```

## 📁 Ruta: src/app/productos/productos.component.html
```html
<div *ngIf="errorMensaje" class="error">
  {{ errorMensaje }}
</div>

<ul *ngIf="!errorMensaje">
  <li *ngFor="let producto of productos">
    {{ producto.title }}
  </li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo demuestra cómo manejar errores HTTP con `catchError` al consumir un servicio.  
Cuando se produce un error, se captura y se muestra un mensaje en la interfaz.  
Se evita que la aplicación falle silenciosamente o que muestre un estado inconsistente.

---

## 🧠 Conceptos aplicados

- Uso de `HttpClient` para peticiones GET
- Aplicación de operadores RxJS (`pipe`, `catchError`)
- Mecanismo de manejo de errores reactivo
- Mostrar mensajes de error en la plantilla condicionalmente

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar un mensaje de error personalizado
```ts
return throwError(() => new Error('No se pudo cargar la información. Intente más tarde.'));
```
📌 **¿Por qué?**: Mejora la experiencia del usuario con mensajes amigables.

---

### ✅ 2. Usar un loader mientras se cargan los datos
```html
<div *ngIf="!productos.length && !errorMensaje">Cargando productos...</div>
```
📌 **¿Por qué?**: Informa al usuario que la aplicación está trabajando.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Detén la conexión a internet o cambia la URL para forzar un error.
2. Asegúrate de ver el mensaje de error en pantalla.
3. Si no hay errores, se debe mostrar la lista de productos correctamente.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - Módulo 8 [➡️](../../../Modulo_8/Modulo_8.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 7](../../Modulo_7.md)

### 🏠 - [Inicio](../../../README.md)
