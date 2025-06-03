# 📘 Módulo 2: Componentes y Data Binding en Angular

## ❓ ¿Qué es el Data Binding?

El **Data Binding** en Angular permite enlazar datos entre el componente (TypeScript) y la vista (HTML). Angular ofrece 4 tipos principales de enlaces:

---

## 📄 Tipos de Binding

### ✅ 1. Interpolación (`{{ variable }}`)

Permite mostrar valores de variables directamente en el HTML.
```html
<p>{{ mensaje }}</p>
```

### ✅ 2. Property Binding (`[propiedad]`)

Se usa para enlazar propiedades del DOM con datos del componente.
```html
<img [src]="imagenUrl">
```

### ✅ 3. Event Binding (`(evento)`)

Permite reaccionar a eventos del usuario.
```html
<button (click)="hacerAlgo()">Click</button>
```

### ✅ 4. Two-way Binding (`[(ngModel)]`)

Vincula el valor de una variable a un campo de formulario y viceversa.
```html
<input [(ngModel)]="usuario">
```

---

## 📦 Requisitos para usar `ngModel`

Para utilizar `[(ngModel)]` necesitas importar `FormsModule` en `app.module.ts`:

```ts
import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [ FormsModule ],
})
export class AppModule { }
```

---

## 🧠 Ventajas del Data Binding

- Permite interfaces dinámicas y reactivas
- Facilita la separación entre lógica y vista
- Es declarativo y fácil de mantener

---

## 🧪 Ejemplo práctico

```ts
nombre = 'Laptop Gamer';
precio = 1500;
mostrarInfo() {
  alert(`Producto: ${this.nombre}`);
}
```

```html
<h3>{{ nombre }}</h3>
<p>{{ precio }}</p>
<button (click)="mostrarInfo()">Ver detalles</button>
```
---

# 🧩 Ampliación: Formularios Reactivos

Angular también ofrece **formularios reactivos**, una alternativa más escalable a los formularios template-driven (`ngModel`). Permiten un control completo desde el código TypeScript.

---

## 🛠️ Fundamentos de formularios reactivos

Para empezar con formularios reactivos, necesitas importar el módulo `ReactiveFormsModule` en `app.module.ts`:

```ts
import { ReactiveFormsModule } from '@angular/forms';

@NgModule({
  imports: [ ReactiveFormsModule ]
})
export class AppModule { }
```

---

## ✅ Crear un formulario reactivo básico

```ts
import { Component } from '@angular/core';
import { FormGroup, FormControl } from '@angular/forms';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html'
})
export class FormularioComponent {
  formulario = new FormGroup({
    nombre: new FormControl(''),
    email: new FormControl('')
  });

  enviar() {
    console.log(this.formulario.value);
  }
}
```

### ✅ HTML asociado

```html
<form [formGroup]="formulario" (ngSubmit)="enviar()">
  <input formControlName="nombre" placeholder="Nombre">
  <input formControlName="email" placeholder="Email">
  <button type="submit">Enviar</button>
</form>
```

---

## 🛠️ Validaciones sincrónicas

Puedes usar validadores como `Validators.required`, `Validators.minLength`, etc.

```ts
import { Validators } from '@angular/forms';

formulario = new FormGroup({
  nombre: new FormControl('', [Validators.required]),
  email: new FormControl('', [Validators.required, Validators.email])
});
```

---

## 🔍 Validaciones personalizadas

```ts
function soloLetras(control: FormControl) {
  const regex = /^[a-zA-Z ]+$/;
  return regex.test(control.value) ? null : { soloLetras: true };
}
```

---

## 🌐 Validaciones asincrónicas

Se usan para consultar a un servidor si un dato es válido:

```ts
import { of } from 'rxjs';
import { delay } from 'rxjs/operators';

function emailNoExistente(control: FormControl) {
  return of(control.value === 'existe@mail.com' ? { emailDuplicado: true } : null).pipe(delay(1000));
}
```

---

## 📚 Formularios anidados

Puedes agrupar controles anidados:

```ts
formulario = new FormGroup({
  usuario: new FormGroup({
    nombre: new FormControl(''),
    email: new FormControl('')
  }),
  password: new FormControl('')
});
```

---

## 🎯 Mostrar errores dinámicamente

```html
<div *ngIf="formulario.get('email')?.errors?.['required']">
  El email es obligatorio
</div>
<div *ngIf="formulario.get('email')?.errors?.['email']">
  El formato no es válido
</div>
```

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### 📘 - [⬅️](../Modulo_1_Introduccion_a_Angular/Modulo_1.md) Módulo 1 - Módulo 3 [➡️](../Modulo_3_Directivas_Angular/Modulo_3.md)

### 🏠 - [Volver al Inicio](../README.md)
