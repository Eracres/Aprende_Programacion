# 🧪 Ejemplo 7: Parámetros dinámicos en rutas

## 🎯 Objetivo
Aprender a configurar rutas que acepten parámetros dinámicos y capturarlos en un componente usando `ActivatedRoute`.

## 📁 Ruta: src/app/producto-detalle/producto-detalle.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-producto-detalle',
  templateUrl: './producto-detalle.component.html'
})
export class ProductoDetalleComponent implements OnInit {
  id: string | null = null;

  constructor(private route: ActivatedRoute) {}

  ngOnInit(): void {
    this.id = this.route.snapshot.paramMap.get('id');
  }
}
```

## 📁 Ruta: src/app/producto-detalle/producto-detalle.component.html
```html
<h3>Detalles del producto con ID: {{ id }}</h3>
```

## 📁 Ruta: src/app/app-routing.module.ts
```ts
const routes: Routes = [
  { path: 'producto/:id', component: ProductoDetalleComponent }
];
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo define una ruta con parámetro dinámico `:id` y lo recupera en el componente mediante `ActivatedRoute`.  
Permite construir URLs como `/producto/5` y acceder al valor `"5"` dentro del componente para mostrar información relevante.

---

## 🧠 Conceptos aplicados

- Rutas dinámicas con `:param`
- Servicio `ActivatedRoute`
- Lectura de parámetros con `snapshot.paramMap.get()`
- Enlace entre rutas y componentes

---

## 💡 Variaciones sugeridas

### ✅ 1. Acceder a parámetros reactivos

```ts
ngOnInit(): void {
  this.route.paramMap.subscribe(params => {
    this.id = params.get('id');
  });
}
```
📌 **¿Por qué?**: Útil cuando el mismo componente se reutiliza en diferentes rutas y los parámetros cambian sin recargar el componente.

---

### ✅ 2. Mostrar múltiples parámetros

```ts
{ path: 'producto/:id/:categoria', component: ProductoDetalleComponent }
```
```ts
const id = this.route.snapshot.paramMap.get('id');
const categoria = this.route.snapshot.paramMap.get('categoria');
```
📌 **¿Por qué?**: Permite mostrar contenido más específico o filtrar por contexto.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Define la ruta `/producto/:id` en `app-routing.module.ts`.
2. Navega a `/producto/10` en tu navegador.
3. Verifica que en la vista se muestre “Detalles del producto con ID: 10”.
4. Prueba con otros valores como `/producto/abc` y comprueba el resultado.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_6.md) Ejemplo 6 - Ejemplo 8 [➡️](./Ejemplo_8.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)
