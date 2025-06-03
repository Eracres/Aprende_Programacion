# 🧪 Ejemplo 5: Mostrar errores condicionales

## 🎯 Objetivo
Controlar cuándo se muestran los errores de validación en el formulario, para mejorar la experiencia de usuario.

## 📁 Ruta: src/app/errores/errores.component.ts
```ts
import { Component } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-errores',
  templateUrl: './errores.component.html'
})
export class ErroresComponent {
  miFormulario: FormGroup;

  constructor(private fb: FormBuilder) {
    this.miFormulario = this.fb.group({
      email: ['', [Validators.required, Validators.email]]
    });
  }

  campoNoValido(campo: string): boolean {
    const control = this.miFormulario.get(campo);
    return control?.invalid && control?.touched || false;
  }
}
```

## 📁 Ruta: src/app/errores/errores.component.html
```html
<form [formGroup]="miFormulario" (ngSubmit)="miFormulario.markAllAsTouched()">
  <label for="email">Correo electrónico:</label>
  <input id="email" formControlName="email" />
  <div *ngIf="campoNoValido('email')">
    El correo es obligatorio y debe tener un formato válido.
  </div>
  <button type="submit">Validar</button>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo condicionar la visualización de los errores solo si el campo fue tocado (`touched`).  
Esto evita mostrar errores desde el inicio y mejora la interacción del usuario con el formulario.

---

## 🧠 Conceptos aplicados

- `touched` para saber si el campo fue manipulado
- Función de utilidad para evaluación de errores
- `markAllAsTouched()` al enviar el formulario

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar errores solo después de intentar enviar
```ts
(submit logic) => form.markAllAsTouched()
```
📌 **¿Por qué?**: Previene mostrar errores antes de que el usuario interactúe.

### ✅ 2. Personalizar los mensajes según el tipo de error
```html
<div *ngIf="campoNoValido('email')">
  <ng-container *ngIf="miFormulario.get('email')?.errors?.['required']">
    El campo es obligatorio.
  </ng-container>
  <ng-container *ngIf="miFormulario.get('email')?.errors?.['email']">
    Debe tener formato válido.
  </ng-container>
</div>
```

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Haz clic en “Validar” sin llenar el campo.
2. El mensaje debe aparecer solo si el campo fue tocado.
3. Rellena el campo correctamente y verifica que el mensaje desaparece.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 6](../../Modulo_6.md)
### 🏠 - [Inicio](../../../README.md)

