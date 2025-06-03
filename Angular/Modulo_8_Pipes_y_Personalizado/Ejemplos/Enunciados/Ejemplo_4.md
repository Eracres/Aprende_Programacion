# 🧪 Ejemplo 4: Pipe personalizado: descuento

## 🎯 Objetivo  
Crear un pipe personalizado en Angular que aplique un descuento porcentual a un precio numérico.

## 📁 Ruta: src/app/descuento.pipe.ts
```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'descuento'
})
export class DescuentoPipe implements PipeTransform {
  transform(valor: number, porcentaje: number): number {
    return valor - (valor * porcentaje / 100);
  }
}
```

## 📁 Ruta: src/app/descuento/descuento.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-descuento',
  templateUrl: './descuento.component.html'
})
export class DescuentoComponent {
  precioOriginal = 100;
  porcentajeDescuento = 15;
}
```

## 📁 Ruta: src/app/descuento/descuento.component.html
```html
<p>Precio con descuento: {{ precioOriginal | descuento: porcentajeDescuento }} €</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo utiliza un **pipe personalizado** llamado `descuento` para calcular el precio final después de aplicar un porcentaje de descuento.  
El valor original (`precioOriginal`) se reduce automáticamente mediante el pipe sin necesidad de lógica adicional en el componente.

---

## 🧠 Conceptos aplicados

- Creación de pipes personalizados con `@Pipe`
- Implementación de `PipeTransform`
- Paso de argumentos al pipe desde la plantilla
- Transformación de valores directamente en la vista

---

## 💡 Variaciones sugeridas

### ✅ 1. Mostrar el precio original y el final
```html
<p>Precio original: {{ precioOriginal }} €</p>
<p>Precio final: {{ precioOriginal | descuento: porcentajeDescuento }} €</p>
```

📌 **¿Por qué?**: Ayuda a visualizar claramente el efecto del descuento.

---

### ✅ 2. Mostrar también el importe descontado
```html
<p>Descuento aplicado: {{ precioOriginal * (porcentajeDescuento / 100) }} €</p>
```

📌 **¿Por qué?**: Muestra al usuario cuánto se está ahorrando.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de declarar el pipe `DescuentoPipe` en el módulo correspondiente.
2. Comprueba en el navegador que el valor mostrado corresponde a la operación `precio - (precio * porcentaje / 100)`.
3. Cambia los valores de `precioOriginal` y `porcentajeDescuento` para comprobar que el cálculo es dinámico.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)  
### 🧪 - [Volver a Ejemplos](../README.md)  
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)  
### 📘 - [Volver a Módulo 8](../../Modulo_8.md)  
### 🏠 - [Inicio](../../../README.md)

