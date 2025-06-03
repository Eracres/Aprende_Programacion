# 🧪 Ejemplo 6: Uso de servicio con ngOnInit

## 🎯 Objetivo
Consultar información desde un servicio al momento de inicializar un componente, usando el ciclo de vida `ngOnInit`.

---

## 📁 Ruta: src/app/login.service.ts

```ts
import { Injectable } from '@angular/core';

@Injectable({ providedIn: 'root' })
export class LoginService {
  logueado = false;

  login() {
    this.logueado = true;
  }

  logout() {
    this.logueado = false;
  }

  estaLogueado() {
    return this.logueado;
  }
}
```

---

## 📁 Ruta: src/app/header/header.component.ts

```ts
import { Component, OnInit } from '@angular/core';
import { LoginService } from '../login.service';

@Component({
  selector: 'app-header',
  templateUrl: './header.component.html'
})
export class HeaderComponent implements OnInit {
  logueado = false;

  constructor(private loginService: LoginService) {}

  ngOnInit() {
    this.logueado = this.loginService.estaLogueado();
  }
}
```

---

## 📁 Ruta: src/app/header/header.component.html

```html
<p *ngIf="logueado">Bienvenido usuario</p>
<p *ngIf="!logueado">Por favor inicia sesión</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo demuestra cómo consultar información desde un servicio en el momento en que el componente se inicializa.  
El componente `HeaderComponent` pregunta al `LoginService` si el usuario está logueado y muestra un mensaje en consecuencia.  
Se utiliza el hook `ngOnInit` para garantizar que la lógica se ejecute después de la creación del componente.

---

## 🧠 Conceptos aplicados

- Uso del ciclo de vida `ngOnInit`
- Servicios en Angular como fuente de estado global
- Inyección de dependencias
- Directiva `*ngIf` para mostrar contenido condicionalmente

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar el nombre del usuario logueado

📁 Ruta: src/app/login.service.ts

```ts
usuario = { nombre: 'Lucía' };
estaLogueado() {
  return this.usuario !== null;
}
getNombre() {
  return this.usuario?.nombre;
}
```

📁 Ruta: src/app/header/header.component.ts

```ts
nombreUsuario = '';

ngOnInit() {
  if (this.loginService.estaLogueado()) {
    this.nombreUsuario = this.loginService.getNombre();
  }
}
```

📁 Ruta: src/app/header/header.component.html

```html
<p *ngIf="nombreUsuario">Bienvenida, {{ nombreUsuario }}!</p>
```

📌 **¿Por qué?**: Mejora la experiencia del usuario mostrando su nombre personalizado tras el login.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener el `LoginService` inyectado correctamente en el componente.
2. Llama a `loginService.login()` desde otra parte de la app y observa que el mensaje cambia.
3. Modifica la lógica de `estaLogueado()` para retornar true y verificar que se muestra el texto correspondiente.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - [📘 Módulo 6 ➡️](../../../Modulo_6_Formularios_y_Validaciones/Modulo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)
