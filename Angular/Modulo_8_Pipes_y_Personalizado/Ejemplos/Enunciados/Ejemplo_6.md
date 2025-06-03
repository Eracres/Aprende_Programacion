# 🧪 Ejemplo 6: Pipe personalizado: calcularEdad

## 🎯 Objetivo
Crear un pipe personalizado que calcule la edad a partir de una fecha de nacimiento.

## 📁 Ruta: src/app/pipes/calcular-edad.pipe.ts
```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({ name: 'calcularEdad' })
export class CalcularEdadPipe implements PipeTransform {
  transform(fechaNacimiento: string | Date): number {
    const nacimiento = new Date(fechaNacimiento);
    const hoy = new Date();
    let edad = hoy.getFullYear() - nacimiento.getFullYear();
    const mes = hoy.getMonth() - nacimiento.getMonth();

    if (mes < 0 || (mes === 0 && hoy.getDate() < nacimiento.getDate())) {
      edad--;
    }
    return edad;
  }
}
```

## 📁 Ruta: src/app/app.component.html
```html
<p>Edad: {{ '1990-06-15' | calcularEdad }} años</p>
```

---

## ✅ ¿Qué hace este componente?
Este ejemplo define un pipe llamado `calcularEdad` que calcula la edad a partir de una fecha de nacimiento en formato `string` o `Date`.  
Utiliza diferencias de fechas para determinar la edad exacta.

---

## 🧠 Conceptos aplicados
- Creación de pipes personalizados
- Manipulación de fechas en JavaScript
- Cálculo de edad con lógica condicional

---

## 💡 Variaciones sugeridas

### ✅ Mostrar edad junto a un mensaje
```html
<p>Tienes {{ '2001-10-30' | calcularEdad }} años</p>
```

### ✅ Mostrar edad de hoy
```html
<p>Edad hoy: {{ today | calcularEdad }}</p>
```

En el componente:
```ts
today = new Date();
```

---

## ✅ ¿Cómo verificar que funciona correctamente?
1. Usa fechas conocidas y comprueba que devuelve la edad correcta.
2. Prueba con fechas cercanas al día actual para validar lógica de meses y días.
3. Cambia el formato de entrada y verifica la respuesta.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 8](../../Modulo_8.md)

### 🏠 - [Inicio](../../../README.md)

