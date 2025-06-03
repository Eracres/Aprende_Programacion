# 🧪 Ejemplo 4: ngClass – Aplicar clases condicionales

## 🎯 Objetivo
Aplicar clases CSS condicionalmente mediante la directiva `[ngClass]`, controlando estilos dinámicos en función de una variable booleana.

## 📁 Ruta: src/app/estilo/estilo.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-estilo',
  templateUrl: './estilo.component.html',
  styleUrls: ['./estilo.component.css']
})
export class EstiloComponent {
  error: boolean = true;
}
```

## 📁 Ruta: src/app/estilo/estilo.component.html
```html
<p [ngClass]="{ 'rojo': error, 'verde': !error }">
  Mensaje con estilo condicional
</p>
```

## 📁 Ruta: src/app/estilo/estilo.component.css
```css
.rojo {
  color: red;
}

.verde {
  color: green;
}
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo usar la directiva `[ngClass]` para **asignar clases CSS condicionalmente**.  
Dependiendo del valor de la propiedad `error`, se aplicará la clase `.rojo` o `.verde`.  
Esto permite cambiar el estilo visual de un elemento de forma dinámica según el estado del componente.

---

## 🧠 Conceptos aplicados

- Directiva `[ngClass]` para aplicar múltiples clases
- Evaluación condicional dentro de la plantilla
- Separación de lógica (`.ts`) y estilos (`.css`)
- Control de estado en la interfaz

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar clases adicionales
```html
<p [ngClass]="{ 'rojo': error, 'verde': !error, 'subrayado': true }">
  Texto con clase extra fija
</p>
```
📌 **¿Por qué?**: Puedes aplicar otras clases adicionales independientemente del estado lógico.

---

### ✅ 2. Intercambiar estado con un botón

```html
<button (click)="error = !error">Alternar estilo</button>
```
📌 **¿Por qué?**: Permite cambiar visualmente el estado del componente desde la vista.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Comprueba que el texto se muestra con color rojo al iniciar (cuando `error` es `true`).
2. Cambia `error` a `false` en el componente o con un botón, y verifica que el color cambia a verde.
3. Añade clases adicionales y comprueba que se aplican correctamente al HTML.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)

