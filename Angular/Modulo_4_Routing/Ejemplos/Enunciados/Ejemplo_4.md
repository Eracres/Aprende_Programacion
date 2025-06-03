# 🧪 Ejemplo 4: Ruta por defecto y página 404

## 🎯 Objetivo
Configurar rutas especiales en Angular: una redirección por defecto y una ruta comodín (`**`) para mostrar una página de error 404.

---

## 📁 Ruta: src/app/app-routing.module.ts

```ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { InicioComponent } from './inicio/inicio.component';
import { ContactoComponent } from './contacto/contacto.component';
import { NotFoundComponent } from './not-found/not-found.component';

const routes: Routes = [
  { path: '', redirectTo: '/inicio', pathMatch: 'full' },
  { path: 'inicio', component: InicioComponent },
  { path: 'contacto', component: ContactoComponent },
  { path: '**', component: NotFoundComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo configura dos rutas especiales en Angular:

- Una **redirección por defecto** que lleva al usuario a `/inicio` si accede a la raíz (`/`).
- Una **ruta comodín `**`** que captura cualquier ruta no definida y muestra el componente `NotFoundComponent`.

Esto permite mejorar la experiencia del usuario y mostrar mensajes claros ante errores de navegación.

---

## 🧠 Conceptos aplicados

- Redirección por defecto usando `redirectTo` y `pathMatch`
- Ruta 404 usando comodín `**`
- Orden correcto de las rutas (la ruta `**` debe ir siempre al final)

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar mensaje de error personalizado

📁 Ruta: src/app/not-found/not-found.component.html

```html
<h2>Página no encontrada</h2>
<p>La ruta que buscas no existe.</p>
<a routerLink="/">Volver al inicio</a>
```

📌 **¿Por qué?**: Mejora la experiencia del usuario mostrando una página 404 amigable.

---

### ✅ 2. Redirigir directamente al componente de inicio

```ts
{ path: '', component: InicioComponent }
```

📌 **¿Por qué?**: En lugar de redireccionar, puedes mostrar directamente el componente sin cambiar la URL.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Entra en una URL inválida como `http://localhost:4200/ruta-inexistente`.
2. Verifica que se muestra el componente `NotFoundComponent`.
3. Accede a `http://localhost:4200/` y asegúrate de que redirige correctamente a `/inicio`.
4. Confirma que el orden de las rutas coloca `**` al final.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)  
### 🏠 - [Inicio](../../../README.md)

