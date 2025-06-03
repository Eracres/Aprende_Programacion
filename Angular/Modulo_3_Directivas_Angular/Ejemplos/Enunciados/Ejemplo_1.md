# 🧪 Ejemplo 1: *ngIf – Mostrar elemento condicionalmente

## 🎯 Objetivo
Aprender a usar la directiva estructural `*ngIf` para mostrar u ocultar elementos en función de una condición lógica.

## 📁 Ruta: src/app/condicional/condicional.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-condicional',
  templateUrl: './condicional.component.html',
})
export class CondicionalComponent {
  mostrar: boolean = true;
}
```

## 📁 Ruta: src/app/condicional/condicional.component.html
```html
<p *ngIf="mostrar">Este mensaje solo se muestra si 'mostrar' es true</p>
```

---

## ✅ ¿Qué hace este componente?

Este componente utiliza `*ngIf`, una directiva estructural de Angular, para mostrar un párrafo **solo si la variable `mostrar` es `true`**.  
Al cambiar el valor de esta variable, Angular agregará o eliminará el contenido del DOM dinámicamente.

---

## 🧠 Conceptos aplicados

- Uso de la directiva `*ngIf`
- Enlace unidireccional de datos
- Lógica condicional en la vista
- Separación de lógica del componente y presentación

---

## 💡 Variaciones sugeridas

### ✅ 1. Ocultar el mensaje por defecto

```ts
mostrar = false;
```
📌 **¿Por qué?**: Comienza con el mensaje oculto y usa una acción para mostrarlo.

---

### ✅ 2. Agregar un botón para alternar el mensaje

```html
<button (click)="mostrar = !mostrar">Mostrar/Ocultar</button>
```
📌 **¿Por qué?**: Permite al usuario decidir cuándo ver el mensaje.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Cambia el valor de `mostrar` en el archivo `.ts`.
2. Observa que el contenido con `*ngIf` aparece o desaparece correctamente.
3. Usa un botón con `click` y asegúrate de que responde como se espera.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)
