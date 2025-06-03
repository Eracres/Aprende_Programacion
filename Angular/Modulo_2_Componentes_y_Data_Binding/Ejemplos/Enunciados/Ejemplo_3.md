# 🧪 Ejemplo 3: Event binding

## 🎯 Objetivo
Mostrar cómo capturar eventos del DOM (como clics) y ejecutar funciones del componente con `()`

## 📁 Ruta: src/app/boton/boton.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-boton',
  templateUrl: './boton.component.html'
})
export class BotonComponent {
  contador: number = 0;

  incrementar() {
    this.contador++;
  }
}
```

## 📁 Ruta: src/app/boton/boton.component.html
```html
<button (click)="incrementar()">Haz clic</button>
<p>Has hecho clic {{ contador }} veces</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo manejar eventos desde la vista, usando `event binding` con `()` para escuchar el evento `click`.  
Cada vez que el usuario hace clic en el botón, se ejecuta el método `incrementar()` del componente y se actualiza la vista automáticamente.

---

## 🧠 Conceptos aplicados

- Event binding con paréntesis `( )`
- Manejo de eventos del usuario
- Actualización de valores del componente

---

## 💡 Variaciones sugeridas

### ✅ 1. Restablecer el contador

```html
<button (click)="contador = 0">Resetear</button>
```

📌 **¿Por qué?**: Permite ofrecer al usuario más control en la interfaz.

---

### ✅ 2. Mostrar mensaje al llegar a un número

```html
<p *ngIf="contador >= 5">¡Has alcanzado 5 clics!</p>
```

📌 **¿Por qué?**: Mejora la experiencia de usuario mediante retroalimentación visual.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de importar y declarar el componente en el módulo.
2. Usa el selector `<app-boton>` en tu plantilla.
3. Haz clic en el botón y observa cómo cambia el contador.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)


