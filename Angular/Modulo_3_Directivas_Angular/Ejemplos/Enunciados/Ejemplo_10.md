# 🧪 Ejemplo 10: Uso de Route Resolver para precargar datos

## 🎯 Objetivo  
Implementar un `Route Resolver` en Angular para precargar los datos necesarios antes de que se cargue un componente.

---

## 📁 Ruta: `src/app/resolvers/usuario.resolver.ts`

```ts
import { Injectable } from '@angular/core';
import { Resolve } from '@angular/router';
import { Observable, of } from 'rxjs';

@Injectable({ providedIn: 'root' })
export class UsuarioResolver implements Resolve<any> {
  resolve(): Observable<any> {
    const usuarioSimulado = {
      id: 1,
      nombre: 'Juan Pérez',
      rol: 'Administrador'
    };
    return of(usuarioSimulado);
  }
}
```

---

## 📁 Ruta: `src/app/perfil/perfil.component.ts`

```ts
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-perfil',
  templateUrl: './perfil.component.html'
})
export class PerfilComponent implements OnInit {
  usuario: any;

  constructor(private route: ActivatedRoute) {}

  ngOnInit(): void {
    this.usuario = this.route.snapshot.data['usuario'];
  }
}
```

---

## 📁 Ruta: `src/app/perfil/perfil.component.html`

```html
<h2>Perfil de Usuario</h2>
<p>Nombre: {{ usuario.nombre }}</p>
<p>Rol: {{ usuario.rol }}</p>
```

---

## 📁 Ruta: `src/app/app-routing.module.ts`

```ts
const routes: Routes = [
  {
    path: 'perfil',
    component: PerfilComponent,
    resolve: {
      usuario: UsuarioResolver
    }
  }
];
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo define un `UsuarioResolver` que simula la obtención de un objeto de usuario.  
El `PerfilComponent` accede a los datos precargados usando `ActivatedRoute`, lo que garantiza que la información esté disponible cuando se renderiza la vista.

---

## 🧠 Conceptos aplicados

- Uso de `Resolve` para precargar datos
- Acceso a datos resueltos con `ActivatedRoute`
- Separación de responsabilidades (servicio vs. componente)
- Mejora del rendimiento de carga inicial

---

## 💡 Variaciones sugeridas

### ✅ 1. Resolver con llamada HTTP real

```ts
resolve(): Observable<Usuario> {
  return this.usuarioService.obtenerPorId(1);
}
```

📌 **¿Por qué?**: Simula un caso real donde los datos vienen desde una API externa.

---

### ✅ 2. Resolver con parámetros dinámicos

```ts
resolve(route: ActivatedRouteSnapshot): Observable<any> {
  const id = route.paramMap.get('id');
  return this.usuarioService.obtenerPorId(id);
}
```

📌 **¿Por qué?**: Permite precargar información específica según el parámetro de la ruta.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Navega a `/perfil` desde la app.
2. Verifica que el usuario ya está disponible al momento de la carga.
3. Reemplaza el objeto simulado con una llamada HTTP si deseas probar con datos reales.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_9.md) Ejemplo 9 - Modulo 4 [➡️](../../../Modulo_4_Routing/Modulo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)
