# 🧪 Ejemplo 5: ngStyle – Estilos dinámicos

## 🎯 Objetivo
Aplicar la directiva `[ngStyle]` para cambiar estilos en línea de elementos HTML de manera dinámica desde el componente.

## 📁 Ruta: src/app/color/color.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-color',
  templateUrl: './color.component.html'
})
export class ColorComponent {
  colorTexto: string = 'blue';
}
```

## 📁 Ruta: src/app/color/color.component.html
```html
<p [ngStyle]="{ 'color': colorTexto }">Este texto cambia de color</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo aplicar estilos en línea dinámicamente con `ngStyle`.  
La propiedad `colorTexto` del componente determina el color del texto mostrado.  
Esto permite personalizar estilos de forma reactiva, sin necesidad de usar clases CSS.

---

## 🧠 Conceptos aplicados

- Directiva `[ngStyle]` para aplicar estilos dinámicos
- Uso de variables de clase para control visual
- Separación entre lógica (`.ts`) y presentación (`.html`)

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar el color dinámicamente

```ts
colorTexto = 'red';
```

📌 **¿Por qué?**: Permite reaccionar a diferentes estados o eventos.

---

### ✅ 2. Agregar más estilos en línea

```ts
<p [ngStyle]="{ 'color': colorTexto, 'fontWeight': 'bold' }">
  Texto con estilo dinámico
</p>
```

📌 **¿Por qué?**: Puedes aplicar múltiples estilos sin necesidad de definir clases CSS adicionales.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Verifica que el texto se muestre en azul por defecto.
2. Cambia el valor de `colorTexto` a otro color y asegúrate de que se aplique.
3. Añade nuevos estilos como tamaño de fuente o tipo de letra para experimentar.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)


