# 📘 Módulo 5: Servicios y Comunicación entre Componentes

## ❓ ¿Qué es un Servicio en Angular?

Un **servicio** en Angular es una clase que centraliza **lógica de negocio**, **peticiones HTTP**, **gestión de datos compartidos** y más.  
Se utiliza para evitar duplicar lógica y mantener el código limpio y desacoplado.

---

## 🛠️ ¿Para qué sirven?

- Compartir datos entre componentes
- Centralizar peticiones HTTP
- Implementar lógica reutilizable (carrito, auth, validaciones)
- Inyectar dependencias y modularizar el proyecto

---

## 🧩 Crear un Servicio en Angular

Angular CLI ofrece un comando directo:
```bash
ng generate service servicios/producto
```

Esto genera dos archivos:
- `producto.service.ts`
- `producto.service.spec.ts` (para tests)

---

## 📦 Ejemplo básico de servicio

```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class ProductoService {
  productos = [
    { id: 1, nombre: 'Laptop', precio: 1200 },
    { id: 2, nombre: 'Mouse', precio: 20 }
  ];

  obtenerProductos() {
    return this.productos;
  }
}
```

- `@Injectable({ providedIn: 'root' })` hace que Angular lo cree automáticamente como servicio global.

---

## 🔗 Inyectar servicio en componente

```ts
import { ProductoService } from '../servicios/producto.service';

constructor(private productoService: ProductoService) {}

ngOnInit() {
  this.productos = this.productoService.obtenerProductos();
}
```

---

## 🔁 Comunicación entre componentes

Si dos componentes necesitan compartir datos (como un carrito), pueden hacerlo mediante un servicio.

### 📦 Servicio compartido:
```ts
export class CarritoService {
  private items = [];

  agregarProducto(p) {
    this.items.push(p);
  }

  obtenerCarrito() {
    return this.items;
  }
}
```

Esto permite que varios componentes consulten o modifiquen el mismo estado centralizado.

---

## 💡 Tipos de comunicación comunes

- **Padre → Hijo**: `@Input()`
- **Hijo → Padre**: `@Output()`
- **Entre hermanos**: Servicio compartido
- **Entre cualquier parte**: Estado centralizado con servicios

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_4_Routing/Modulo_4.md) Módulo 4 - Módulo 6 [➡️](../Modulo_6_Formularios_y_Validaciones/Modulo_6.md)

### 🏠 [Inicio](../README.md)

