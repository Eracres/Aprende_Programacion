# 🧪 Ejemplo 4: Validación de longitud mínima

## 🎯 Objetivo
Aplicar la validación de longitud mínima (`minlength`) en un campo de formulario para restringir la entrada del usuario.

## 📁 Ruta: src/app/formulario/formulario.component.ts
```ts
import { Component } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html'
})
export class FormularioComponent {
  miFormulario: FormGroup;

  constructor(private fb: FormBuilder) {
    this.miFormulario = this.fb.group({
      usuario: ['', [Validators.required, Validators.minLength(5)]]
    });
  }
}
```

## 📁 Ruta: src/app/formulario/formulario.component.html
```html
<form [formGroup]="miFormulario">
  <label for="usuario">Usuario:</label>
  <input id="usuario" formControlName="usuario" />
  <div *ngIf="miFormulario.get('usuario')?.errors?.['minlength']">
    El nombre de usuario debe tener al menos 5 caracteres.
  </div>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo define un formulario reactivo con una validación de longitud mínima en el campo `usuario`.  
El mensaje de error se muestra si el valor ingresado tiene menos de 5 caracteres.

---

## 🧠 Conceptos aplicados

- Formulario reactivo con `FormBuilder`
- Validadores incorporados (`Validators.minLength`)
- Acceso y visualización de errores de formulario

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar la longitud mínima a 8 caracteres
```ts
usuario: ['', [Validators.required, Validators.minLength(8)]]
```
📌 **¿Por qué?**: Para forzar nombres de usuario más seguros.

### ✅ 2. Usar el validador en otro campo (e.g. contraseña)
```ts
contrasena: ['', [Validators.required, Validators.minLength(6)]]
```
📌 **¿Por qué?**: Las contraseñas suelen requerir validaciones más estrictas.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Intenta escribir un nombre de menos de 5 caracteres.
2. Verifica que se muestra el mensaje de error.
3. Escribe más de 5 caracteres y asegúrate de que el error desaparece.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 6](../../Modulo_6.md)
### 🏠 - [Inicio](../../../README.md)

