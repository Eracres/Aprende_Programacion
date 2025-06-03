# 📘 Módulo 4: Routing – Navegación entre páginas

## ❓ ¿Qué es el Routing en Angular?

Angular es un framework para crear SPA (Single Page Applications), lo que significa que no se recarga toda la página al navegar. En su lugar, Angular **simula la navegación** cargando dinámicamente componentes según la ruta del navegador.

Esto se logra gracias al **Router de Angular**, que permite:

- Navegar entre vistas
- Definir rutas y componentes asociados
- Cargar componentes de forma dinámica sin recargar la página

---

## 🔧 Configuración del Routing

1. Angular crea un archivo `app-routing.module.ts` cuando marcas la opción de routing al crear el proyecto.
2. En ese archivo defines las rutas con el array `Routes`:

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

## 🧩 ¿Cómo se usa?

### ✅ Enlace a rutas
Usamos `[routerLink]` para cambiar de ruta sin recargar la página:
```html
<a routerLink="/acerca">Acerca</a>
```

### ✅ Renderizado dinámico
El componente correspondiente se carga dentro del `<router-outlet>`:
```html
<router-outlet></router-outlet>
```

---

## ⚙️ Componentes típicos para navegación

- **InicioComponent** → para ruta raíz (`/`)
- **AcercaComponent** → información general (`/acerca`)
- **ServiciosComponent** → descripción de servicios (`/servicios`)
- **ContactoComponent** → formulario o datos de contacto (`/contacto`)
- **NotFoundComponent** → página de error (`**`)

---

## 🛑 Ruta por defecto y ruta 404

```ts
const routes: Routes = [
  { path: '', component: InicioComponent },
  { path: 'contacto', component: ContactoComponent },
  { path: '**', component: NotFoundComponent } // Página 404
];
```

---

## 🧠 ¿Por qué usar Routing?

- Mejora la experiencia del usuario (sin recargas)
- Permite organizar tu aplicación por páginas
- Es escalable: puedes crear módulos por ruta (Lazy Loading)
- Es compatible con el historial del navegador (back/forward)

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### 📘 - [⬅️](../Modulo_3_Directivas_Angular/Modulo_3.md) Módulo 3 - Módulo 5 [➡️](../Modulo_5_Servicios_y_Comunicación/Modulo_5.md)

### 🏠 [Inicio](../README.md)

