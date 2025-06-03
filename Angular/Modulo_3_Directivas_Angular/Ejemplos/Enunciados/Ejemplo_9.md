# 🧪 Ejemplo 9: Lazy loading de módulos

## 🎯 Objetivo  
Implementar lazy loading en una aplicación Angular para cargar módulos solo cuando se navega a su ruta correspondiente.

## 📁 Ruta: src/app/app-routing.module.ts
```ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

const routes: Routes = [
  {
    path: 'tienda',
    loadChildren: () => import('./tienda/tienda.module').then(m => m.TiendaModule)
  }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}
```

## 📁 Ruta: src/app/tienda/tienda-routing.module.ts
```ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { ProductosComponent } from './productos/productos.component';

const routes: Routes = [
  { path: '', component: ProductosComponent }
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class TiendaRoutingModule {}
```

## 📁 Ruta: src/app/tienda/tienda.module.ts
```ts
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { ProductosComponent } from './productos/productos.component';
import { TiendaRoutingModule } from './tienda-routing.module';

@NgModule({
  declarations: [ProductosComponent],
  imports: [CommonModule, TiendaRoutingModule]
})
export class TiendaModule {}
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo implementa **lazy loading** para el módulo `TiendaModule`.  
El módulo se cargará dinámicamente solo si el usuario navega a la ruta `/tienda`.  
Esto mejora el rendimiento general de la aplicación al reducir el tamaño del bundle inicial.

---

## 🧠 Conceptos aplicados

- `loadChildren` con sintaxis dinámica (`import()`).
- División de la app en módulos funcionales.
- Enrutamiento con `RouterModule.forChild()` para módulos cargados perezosamente.

---

## 💡 Variaciones sugeridas

### ✅ 1. Cargar otro módulo con lazy loading

```ts
{ path: 'admin', loadChildren: () => import('./admin/admin.module').then(m => m.AdminModule) }
```

📌 **¿Por qué?**: Mejora la escalabilidad separando módulos funcionales y evita cargar partes innecesarias al inicio.

---

### ✅ 2. Añadir guardas al módulo lazy

```ts
{
  path: 'admin',
  loadChildren: () => import('./admin/admin.module').then(m => m.AdminModule),
  canLoad: [AuthGuard]
}
```

📌 **¿Por qué?**: Protege el módulo de ser cargado si el usuario no está autenticado.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Revisa que el componente `ProductosComponent` se muestre solo al ir a `/tienda`.
2. Verifica que en la red del navegador se cargue el archivo del módulo dinámicamente.
3. El módulo `TiendaModule` no debe estar incluido en el `AppModule`.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_8.md) Ejemplo 8 - Ejemplo 10 [➡️](./Ejemplo_10.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 3](../../Modulo_3.md)  
### 🏠 - [Inicio](../../../README.md)
