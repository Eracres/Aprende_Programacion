# 🧪 Ejemplo 2: Formulario con validación required

## 🎯 Objetivo
Construir un formulario básico usando `ngModel` y aplicar validación requerida (`required`) para controlar los envíos incompletos.

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

  enviarFormulario() {
    if (this.nombre.trim()) {
      alert(`Formulario enviado con nombre: ${this.nombre}`);
    } else {
      alert('El campo nombre es obligatorio');
    }
  }
}
```

---

## 📁 Ruta: src/app/formulario/formulario.component.html

```html
<form (ngSubmit)="enviarFormulario()" #miFormulario="ngForm">
  <label for="nombre">Nombre:</label>
  <input
    type="text"
    id="nombre"
    name="nombre"
    required
    [(ngModel)]="nombre"
    #nombreRef="ngModel"
  />

  <div *ngIf="nombreRef.invalid && nombreRef.touched" style="color: red;">
    El nombre es obligatorio.
  </div>

  <button type="submit" [disabled]="miFormulario.invalid">Enviar</button>
</form>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo usar **formularios basados en plantillas (template-driven)** en Angular.  
Se crea un input con `[(ngModel)]`, se marca como `required` y se valida que el campo tenga contenido antes de enviar.

- La directiva `ngModel` enlaza el valor del input con la variable `nombre` del componente.
- `ngForm` se usa para acceder al estado global del formulario.
- Se desactiva el botón si el formulario no es válido.

---

## 🧠 Conceptos aplicados

- Enlace bidireccional con `[(ngModel)]`
- Validación con `required`
- Acceso al estado del formulario vía `#miFormulario="ngForm"`
- Deshabilitar el botón de envío cuando el formulario no es válido

---

## 💡 Variaciones sugeridas

### ✅ 1. Validar campo tipo email

📁 Ruta: src/app/formulario/formulario.component.html

```html
<input
  type="email"
  name="email"
  required
  [(ngModel)]="email"
  #emailRef="ngModel"
/>
<div *ngIf="emailRef.invalid && emailRef.touched">
  Ingrese un correo válido.
</div>
```

📌 **¿Por qué?**: Angular aprovecha las validaciones nativas de HTML5 para validar emails automáticamente.

---

### ✅ 2. Mostrar un mensaje de éxito con estilos

```html
<p *ngIf="miFormulario.valid && miFormulario.submitted" class="success">
  ¡Formulario enviado correctamente!
</p>
```

📌 **¿Por qué?**: Mejora la experiencia de usuario al confirmar visualmente el envío exitoso.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Ejecuta la aplicación y navega al componente del formulario.
2. Intenta enviar el formulario vacío: debe mostrar un mensaje de error y deshabilitar el botón.
3. Escribe un nombre válido y verifica que el botón se activa.
4. Haz clic en "Enviar" y asegúrate de que aparece una alerta o mensaje correcto.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 6](../../Modulo_6.md)
### 🏠 - [Inicio](../../../README.md)

