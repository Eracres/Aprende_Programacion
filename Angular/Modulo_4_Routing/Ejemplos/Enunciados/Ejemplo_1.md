# 🧪 Ejemplo 1: Configuración básica del Router

## 🎯 Objetivo
Configurar las rutas principales de una aplicación Angular usando el módulo RouterModule.

## 📁 Ruta: src/app/app-routing.module.ts
```ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { InicioComponent } from './inicio/inicio.component';
import { AcercaComponent } from './acerca/acerca.component';

const routes: Routes = [
  { path: '', component: InicioComponent },
  { path: 'acerca', component: AcercaComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

---

## ✅ ¿Qué hace este ejemplo?
Este ejemplo muestra cómo crear un archivo de rutas (`app-routing.module.ts`) para gestionar la navegación entre componentes.  
Se definen dos rutas: la raíz (`''`) que carga el componente `InicioComponent`, y la ruta `/acerca` que carga `AcercaComponent`.

---

## 🧠 Conceptos aplicados
- Creación de rutas con `Routes`
- Importación del `RouterModule`
- Uso de `forRoot()` para rutas raíz de la aplicación
- Asociación de rutas con componentes

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar una nueva ruta

📁 Ruta: src/app/app-routing.module.ts
```ts
{ path: 'contacto', component: ContactoComponent }
```
📌 **¿Por qué?**: Añadir más secciones a la navegación principal de la app.

---

### ✅ 2. Crear una ruta por defecto con redirección

```ts
{ path: '**', redirectTo: '', pathMatch: 'full' }
```
📌 **¿Por qué?**: Mejora la UX redirigiendo cualquier ruta inválida a la página de inicio.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre el navegador en `http://localhost:4200/` y verifica que se carga el componente `InicioComponent`.
2. Navega a `http://localhost:4200/acerca` y verifica que se muestra el componente `AcercaComponent`.
3. Asegúrate de que el `RouterModule` está correctamente importado en `AppModule`.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)
### 🏠 - [Inicio](../../../README.md)

