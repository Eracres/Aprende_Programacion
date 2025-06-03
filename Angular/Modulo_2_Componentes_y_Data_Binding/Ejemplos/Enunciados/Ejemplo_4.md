# 🧪 Ejemplo 4: Two-way binding con ngModel

## 🎯 Objetivo
Mostrar cómo enlazar una variable bidireccionalmente entre el componente y la vista usando `[(ngModel)]`.

## 📁 Ruta: src/app/formulario/formulario.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html'
})
export class FormularioComponent {
  nombre: string = '';
}
```

## 📁 Ruta: src/app/formulario/formulario.component.html
```html
<input [(ngModel)]="nombre" placeholder="Escribe tu nombre">
<p>Hola, {{ nombre }}!</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo utiliza `[(ngModel)]` para crear un enlace bidireccional entre el input y la variable del componente.  
Cada vez que el usuario escribe en el campo, el valor de `nombre` se actualiza automáticamente y se refleja en el DOM.

---

## 🧠 Conceptos aplicados

- Two-way data binding
- Uso de `FormsModule` (requisito para `ngModel`)
- Enlace en tiempo real entre datos y vista

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar un mensaje de bienvenida condicional

```html
<p *ngIf="nombre">¡Bienvenido, {{ nombre }}!</p>
```

📌 **¿Por qué?**: Aporta una mejor experiencia mostrando información solo cuando hay datos.

---

### ✅ 2. Limpiar el campo con un botón

```html
<button (click)="nombre = ''">Limpiar</button>
```

📌 **¿Por qué?**: Mejora la usabilidad permitiendo reiniciar el formulario fácilmente.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de importar `FormsModule` en el `AppModule`.
2. Usa el selector `<app-formulario>` y escribe en el input.
3. Verifica que el texto en pantalla se actualiza conforme se escribe.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)

