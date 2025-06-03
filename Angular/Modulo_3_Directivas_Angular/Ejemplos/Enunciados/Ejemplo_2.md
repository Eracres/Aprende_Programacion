# 🧪 Ejemplo 2: *ngFor – Listado de elementos

## 🎯 Objetivo
Utilizar la directiva `*ngFor` para iterar sobre una lista y mostrar los elementos en pantalla.


## `lista.component.ts`
```ts
export class ListaComponent {
  frutas = ['Manzana', 'Banana', 'Naranja'];
}
```

## `lista.component.html`
```html
<ul>
  <li *ngFor="let fruta of frutas">{{ fruta }}</li>
</ul>
```

## ✅ ¿Qué hace este componente?
Este componente recorre un array de frutas y genera un `li` por cada ítem usando `*ngFor`.

---

## ✅ ¿Cómo verificar que funciona correctamente?

Agrega o elimina elementos del array y verifica que se actualice el listado en pantalla.


## 🧠 Conceptos aplicados
- Uso de `*ngFor` para iterar arrays
- Creación dinámica de listas
- Interpolación en elementos generados


---

## 💡 Variaciones sugeridas
```ts
Agregar un índice: `let i = index`
```
```ts
<li *ngFor="let fruta of frutas; let i = index">{{ i + 1 }}. {{ fruta }}</li>
```

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)

