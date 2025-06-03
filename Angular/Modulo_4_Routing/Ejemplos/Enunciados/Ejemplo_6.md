# 🧪 Ejemplo 6: Redirección de rutas

## 🎯 Objetivo
Aprender a redirigir automáticamente rutas vacías o no válidas a una ruta válida mediante el uso de `redirectTo`.

---

## 📁 Ruta: src/app/app-routing.module.ts
```ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { InicioComponent } from './inicio/inicio.component';

const routes: Routes = [
  { path: '', redirectTo: '/inicio', pathMatch: 'full' },
  { path: 'inicio', component: InicioComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

---

## ✅ ¿Qué hace este ejemplo?

Esta configuración del enrutado redirige automáticamente la ruta raíz (`''`) hacia `/inicio`.

Cuando un usuario accede a `http://localhost:4200`, Angular lo lleva directamente al componente asociado a la ruta `/inicio`.  
Es importante usar `pathMatch: 'full'` para evitar coincidencias parciales no deseadas.

---

## 🧠 Conceptos aplicados

- Redirección de rutas con `redirectTo`
- Importancia de `pathMatch: 'full'`
- Rutas raíz y componentes asociados

---

## 💡 Variaciones sugeridas

### ✅ 1. Redirigir otra ruta como `/home` → `/inicio`

```ts
{ path: 'home', redirectTo: '/inicio', pathMatch: 'full' }
```

📌 **¿Por qué?**: Útil para mantener compatibilidad con URLs antiguas o alias de navegación.

---

### ✅ 2. Redirigir rutas no válidas usando comodín `**`

```ts
{ path: '**', redirectTo: '/inicio', pathMatch: 'full' }
```

📌 **¿Por qué?**: Mejora la experiencia de usuario al evitar errores de navegación cuando se introduce una URL incorrecta.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre `http://localhost:4200` y verifica que se carga el componente `InicioComponent`.
2. Prueba acceder a rutas como `/`, `/home`, o rutas inválidas y observa si redirige correctamente a `/inicio`.
3. Asegúrate de que `RouterModule` esté importado en `AppModule`.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - Módulo 5 [➡️](../../../Modulo_5_Servicios_y_Comunicación/Modulo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md)

### 🏠 - [Inicio](../../../README.md)

