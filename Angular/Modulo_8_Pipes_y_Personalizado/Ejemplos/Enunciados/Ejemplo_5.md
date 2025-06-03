# 🧪 Ejemplo 5: Pipe personalizado: mayusInvertido

## 🎯 Objetivo
Crear un pipe personalizado que transforme un texto a mayúsculas y luego invierta su contenido.

## 📁 Ruta: src/app/pipes/mayus-invertido.pipe.ts
```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({ name: 'mayusInvertido' })
export class MayusInvertidoPipe implements PipeTransform {
  transform(valor: string): string {
    return valor.toUpperCase().split('').reverse().join('');
  }
}
```

## 📁 Ruta: src/app/app.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
  mensaje: string = 'angular';
}
```

## 📁 Ruta: src/app/app.component.html
```html
<p>{{ mensaje | mayusInvertido }}</p>
```

---

## ✅ ¿Qué hace este componente?
El pipe `mayusInvertido` transforma un texto a mayúsculas y luego invierte los caracteres.  
Por ejemplo, `angular` se convierte en `RALUGNA`.

---

## 🧠 Conceptos aplicados
- Creación de pipes personalizados
- Transformaciones de cadenas en Angular
- Encapsulamiento de lógica de presentación

---

## 💡 Variaciones sugeridas

### ✅ Invertir sin convertir a mayúsculas
```ts
return valor.split('').reverse().join('');
```
📌 **¿Por qué?**: Para mantener el formato original y solo invertir el texto.

### ✅ Añadir validación de entrada
```ts
if (!valor) return '';
```
📌 **¿Por qué?**: Evita errores si el valor es `null` o `undefined`.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Declara el pipe en el módulo correspondiente (`declarations`).
2. Usa el pipe en una interpolación dentro del HTML.
3. Asegúrate de que la salida sea el texto invertido y en mayúsculas.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 8](../../Modulo_8.md)
### 🏠 - [Inicio](../../../README.md)

