# 🧪 Ejemplo 5: Binding combinado

## `app.component.ts`
```ts
export class AppComponent {
  producto = 'Laptop Gamer';
  precio = 1500;
}
```

## `app.component.html`
```html
<h2>{{ producto }}</h2>
<p>Precio: ${{ precio }}</p>
<button (click)="alert('Producto: ' + producto)">Ver</button>
```

## ✅ ¿Qué hace este componente?
Este ejemplo combina interpolación para mostrar datos y event binding para responder a eventos del usuario.

---

## 🧠 Conceptos aplicados
- Interpolación con variables
- Event binding en botones
- Presentación de datos y respuesta a eventos

---

## 💡 Variaciones sugeridas
```ts
Agregar más propiedades como `stock` o `marca`
```
```ts
Cambiar el mensaje del botón
```

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)
