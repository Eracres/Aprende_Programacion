# 🧪 Ejemplo 3: Validación de email

## 🎯 Objetivo
Aplicar validaciones en campos de formulario utilizando formularios controlados por plantilla (template-driven forms), específicamente validando el campo de email.

---

## 📁 Ruta: src/app/formulario/formulario.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html'
})
export class FormularioComponent {
  email: string = '';
}
```

---

## 📁 Ruta: src/app/formulario/formulario.component.html

```html
<form #form="ngForm" (ngSubmit)="form.valid && enviarFormulario()">
  <label for="email">Correo electrónico:</label>
  <input
    type="email"
    id="email"
    name="email"
    [(ngModel)]="email"
    required
    email
    #emailRef="ngModel"
  />

  <div *ngIf="emailRef.invalid && emailRef.touched" class="error">
    <small *ngIf="emailRef.errors?.['required']">El correo es obligatorio.</small>
    <small *ngIf="emailRef.errors?.['email']">Formato de correo inválido.</small>
  </div>

  <button type="submit">Enviar</button>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este componente muestra cómo validar un campo de correo electrónico en un formulario Angular utilizando directivas de template (`[(ngModel)]`).  
Valida automáticamente si el campo está vacío o si no cumple con el formato de un email válido.  
Los mensajes de error aparecen solo cuando el usuario ha tocado el campo y la validación falla.

---

## 🧠 Conceptos aplicados

- Formularios controlados por plantilla
- Uso de `ngModel` y validadores (`required`, `email`)
- Validación reactiva con `#nombreRef="ngModel"`
- Despliegue de errores basado en el estado del control

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar mensajes solo si se ha intentado enviar

```html
<form #form="ngForm" (ngSubmit)="submitted = true; form.valid && enviarFormulario()">
  <!-- ... -->
  <div *ngIf="submitted && emailRef.invalid" class="error">
    <!-- Mensajes -->
  </div>
</form>
```

📌 **¿Por qué?**: Para no mostrar errores antes de que el usuario interactúe con el formulario.

---

### ✅ 2. Añadir validación de longitud mínima

```html
<input
  type="email"
  minlength="5"
  required
  [(ngModel)]="email"
  name="email"
/>
```

📌 **¿Por qué?**: Ayuda a asegurar que los correos tengan una longitud mínima aceptable.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Intenta enviar el formulario sin ingresar un email.
2. Escribe un email inválido como `usuario@`.
3. Observa cómo los mensajes de error cambian según la validación.
4. Introduce un email válido y verifica que el formulario se puede enviar.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 6](../../Modulo_6.md)

### 🏠 - [Inicio](../../../README.md)
