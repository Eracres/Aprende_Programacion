# 🧪 Ejemplo 3: Mostrar precios con currency pipe

## 🎯 Objetivo
Aplicar el pipe `currency` de Angular para formatear precios en diferentes monedas y estilos.

## 📁 Ruta: src/app/precios/precios.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-precios',
  templateUrl: './precios.component.html'
})
export class PreciosComponent {
  precio1 = 1500;
  precio2 = 75.5;
}
```

## 📁 Ruta: src/app/precios/precios.component.html
```html
<p>Precio en euros: {{ precio1 | currency:'EUR' }}</p>
<p>Precio en dólares: {{ precio2 | currency:'USD' }}</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo aplicar el pipe `currency` para formatear valores numéricos como precios en una plantilla HTML.  
Utilizamos distintos códigos de moneda (`EUR`, `USD`) para mostrar los valores correctamente localizados.

---

## 🧠 Conceptos aplicados

- Uso del pipe `currency` integrado de Angular
- Formato de moneda basado en localización
- Transformación visual sin modificar los datos originales

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar el símbolo a código ISO

```html
<p>{{ precio1 | currency:'EUR':'code' }}</p>
```

📌 **¿Por qué?**: En lugar de mostrar `€`, verás `EUR`, lo cual es útil en contextos más formales.

---

### ✅ 2. Mostrar sin decimales

```html
<p>{{ precio2 | currency:'USD':'symbol':'1.0-0' }}</p>
```

📌 **¿Por qué?**: Para simplificar la visualización si no necesitas mostrar céntimos.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Comprueba que los valores `precio1` y `precio2` aparecen en formato moneda en la plantilla.
2. Cambia el valor de las propiedades y observa que el formato se mantiene correctamente.
3. Prueba con otros códigos de moneda como `GBP`, `JPY`, etc.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 8](../../Modulo_8.md)

### 🏠 - [Inicio](../../../README.md)

