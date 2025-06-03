# 🧪 Ejemplo 1: Formulario con ngModel

## 🎯 Objetivo
Construir un formulario básico utilizando el modelo basado en plantillas (template-driven) con `[(ngModel)]` para el enlace de datos bidireccional.

---

## 📁 Ruta: src/app/formulario/formulario.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html'
})
export class FormularioComponent {
  nombre: string = '';
  email: string = '';

  enviarFormulario() {
    console.log('Nombre:', this.nombre);
    console.log('Email:', this.email);
  }
}
```

---

## 📁 Ruta: src/app/formulario/formulario.component.html

```html
<form (ngSubmit)="enviarFormulario()" #formulario="ngForm">
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" [(ngModel)]="nombre" required />

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" [(ngModel)]="email" required />

  <button type="submit" [disabled]="!formulario.valid">Enviar</button>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo crea un formulario simple con campos de texto para capturar el nombre y el correo electrónico del usuario.  
Gracias a `[(ngModel)]`, los datos del formulario están vinculados directamente con las propiedades del componente.  
Al hacer clic en “Enviar”, se llama al método `enviarFormulario()` que imprime los valores ingresados en la consola.

---

## 🧠 Conceptos aplicados

- Uso de formularios basados en plantillas (template-driven forms)
- Enlace de datos bidireccional con `[(ngModel)]`
- Validación básica con `required`
- Disparo de eventos con `(ngSubmit)`
- Referencia local a formularios (`#formulario="ngForm"`)

---

## 💡 Variaciones sugeridas

### ✅ 1. Añadir un campo de tipo `tel`

📁 Ruta: src/app/formulario/formulario.component.ts

```ts
telefono: string = '';
```

📁 Ruta: src/app/formulario/formulario.component.html

```html
<label for="telefono">Teléfono:</label>
<input type="tel" id="telefono" name="telefono" [(ngModel)]="telefono" />
```

📌 **¿Por qué?**: Aumenta la funcionalidad del formulario para recoger más datos.

---

### ✅ 2. Mostrar los datos en pantalla en vez de solo en consola

📁 Ruta: src/app/formulario/formulario.component.html

```html
<p *ngIf="nombre">Nombre ingresado: {{ nombre }}</p>
<p *ngIf="email">Email ingresado: {{ email }}</p>
```

📌 **¿Por qué?**: Mejora la experiencia del usuario al ver sus datos reflejados en tiempo real.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Ejecuta la app y navega al componente `<app-formulario>`.
2. Completa los campos de nombre y email.
3. Asegúrate de que el botón se habilita cuando ambos campos están completos.
4. Al hacer clic en “Enviar”, abre la consola y verifica que los valores aparecen correctamente.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 6](../../Modulo_6.md)
### 🏠 - [Inicio](../../../README.md)

