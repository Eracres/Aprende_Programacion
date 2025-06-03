# 🧪 Ejemplo 6: Formulario completo de contacto

## 🎯 Objetivo
Construir un formulario completo con múltiples campos y validaciones integradas usando Reactive Forms.

## 📁 Ruta: src/app/contacto/contacto.component.ts
```ts
import { Component } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-contacto',
  templateUrl: './contacto.component.html'
})
export class ContactoComponent {
  contactoForm: FormGroup;

  constructor(private fb: FormBuilder) {
    this.contactoForm = this.fb.group({
      nombre: ['', Validators.required],
      email: ['', [Validators.required, Validators.email]],
      mensaje: ['', [Validators.required, Validators.minLength(10)]]
    });
  }

  enviar() {
    if (this.contactoForm.invalid) return;
    console.log('Formulario enviado:', this.contactoForm.value);
  }
}
```

## 📁 Ruta: src/app/contacto/contacto.component.html
```html
<form [formGroup]="contactoForm" (ngSubmit)="enviar()">
  <label>Nombre:</label>
  <input formControlName="nombre" />
  <div *ngIf="contactoForm.get('nombre')?.invalid && contactoForm.get('nombre')?.touched">
    El nombre es obligatorio.
  </div>

  <label>Email:</label>
  <input formControlName="email" />
  <div *ngIf="contactoForm.get('email')?.invalid && contactoForm.get('email')?.touched">
    Email no válido.
  </div>

  <label>Mensaje:</label>
  <textarea formControlName="mensaje"></textarea>
  <div *ngIf="contactoForm.get('mensaje')?.invalid && contactoForm.get('mensaje')?.touched">
    El mensaje debe tener al menos 10 caracteres.
  </div>

  <button type="submit">Enviar</button>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este formulario permite al usuario introducir su nombre, email y un mensaje.  
Incluye validaciones para asegurar que todos los campos sean completados correctamente.  
Al enviar el formulario válido, los datos se imprimen en consola.

---

## 🧠 Conceptos aplicados

- Formularios reactivos con múltiples campos
- Validaciones combinadas (`required`, `email`, `minLength`)
- Control de errores y feedback visual
- Envío de datos con `ngSubmit`

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar un mensaje de éxito tras el envío

```html
<div *ngIf="contactoForm.valid && enviado">
  ¡Gracias por tu mensaje!
</div>
```

📌 **¿Por qué?**: Mejora la UX confirmando que el envío fue exitoso.

---

### ✅ 2. Agregar un campo opcional de teléfono

```ts
telefono: ['']
```

📌 **¿Por qué?**: Permite capturar información adicional sin obligar al usuario.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Completa todos los campos y pulsa enviar.
2. Asegúrate de que los datos se muestren en consola.
3. Intenta enviar con campos vacíos para validar que aparecen los errores.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - Módulo 7 [➡️](../../../Modulo_7_Consumo_de_APIs_con_HttpClient/Modulo_7.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 6](../../Modulo_6.md)
### 🏠 - [Inicio](../../../README.md)

