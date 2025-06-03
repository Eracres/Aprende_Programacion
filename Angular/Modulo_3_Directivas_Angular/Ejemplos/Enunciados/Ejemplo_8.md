# 🧪 Ejemplo 8: Leer parámetros de ruta (`:id`)

## 🎯 Objetivo
Aprender a leer parámetros dinámicos desde la URL usando `ActivatedRoute` en un componente.

## 📁 Ruta: `src/app/producto-detalle/producto-detalle.component.ts`

```ts
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-producto-detalle',
  templateUrl: './producto-detalle.component.html'
})
export class ProductoDetalleComponent implements OnInit {
  idProducto: string | null = '';

  constructor(private route: ActivatedRoute) {}

  ngOnInit(): void {
    this.idProducto = this.route.snapshot.paramMap.get('id');
  }
}
```

## 📁 Ruta: `src/app/producto-detalle/producto-detalle.component.html`

```html
<h2>Detalle del Producto</h2>
<p>ID del producto: {{ idProducto }}</p>
```

---

## ✅ ¿Qué hace este componente?

Este componente accede a un parámetro de la URL llamado `id` y lo muestra en pantalla.  
El parámetro se define en el archivo de rutas como `path: 'producto/:id'`.  
El método `snapshot.paramMap.get('id')` permite capturarlo.

---

## 🧠 Conceptos aplicados

- Uso de `ActivatedRoute` para acceder a información de la ruta activa
- Lectura de parámetros dinámicos (`:id`)
- Inyección de dependencias en el constructor
- Visualización de valores obtenidos desde la URL

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar más detalles en base al ID recibido

```ts
// Supongamos que tienes un servicio con productos
producto: any;

ngOnInit(): void {
  const id = this.route.snapshot.paramMap.get('id');
  this.producto = this.productoService.obtenerProductoPorId(id);
}
```

📌 **¿Por qué?**: Permite mostrar datos reales basados en la URL y dar contexto dinámico al usuario.

---

### ✅ 2. Suscribirse a cambios de parámetros (si el componente no se destruye)

```ts
this.route.paramMap.subscribe(params => {
  this.idProducto = params.get('id');
});
```

📌 **¿Por qué?**: Es útil cuando se navega a la misma ruta con un nuevo parámetro sin recargar el componente.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Define la ruta en `app-routing.module.ts` como:
   ```ts
   { path: 'producto/:id', component: ProductoDetalleComponent }
   ```

2. Accede en el navegador a una URL como:  
   `http://localhost:4200/producto/45`

3. Verifica que en pantalla se muestre:  
   `ID del producto: 45`

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_7.md) Ejemplo 7 - Ejemplo 9 [➡️](./Ejemplo_9.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 3](../../Modulo_3.md)  
### 🏠 - [Inicio](../../../README.md)

