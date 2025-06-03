# 📘 Módulo 8: Pipes y Pipes Personalizados

## ❓ ¿Qué es un Pipe en Angular?

Un **Pipe** (tubería) en Angular permite **transformar visualmente datos en plantillas HTML**.  
Se usan con la sintaxis `{{ valor | pipe }}` para aplicar formatos como fechas, monedas, mayúsculas, etc.

---

## 🔤 Pipes Comunes en Angular

Angular ofrece varios **pipes integrados** para tareas frecuentes:

| Pipe        | Uso                            | Ejemplo                            |
|-------------|--------------------------------|-------------------------------------|
| `uppercase` | Convierte texto a mayúsculas   | `{{ 'hola' | uppercase }}` → HOLA   |
| `lowercase` | Convierte texto a minúsculas   | `{{ 'HOLA' | lowercase }}` → hola   |
| `currency`  | Formatea como moneda           | `{{ 1500 | currency }}` → €1,500.00 |
| `date`      | Formatea fechas                | `{{ fecha | date:'short' }}`        |
| `json`      | Muestra objetos como JSON      | `{{ objeto | json }}`               |

---

## 🛠️ Crear un Pipe Personalizado

Un pipe personalizado nos permite crear transformaciones específicas.

```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({ name: 'descuento' })
export class DescuentoPipe implements PipeTransform {
  transform(valor: number, porcentaje: number) {
    return valor - (valor * porcentaje / 100);
  }
}
```

Este pipe se usaría así en la vista:

```html
<p>{{ 200 | descuento:10 }}</p> <!-- Muestra 180 -->
```

---

## 🔧 Otros Pipes Personalizados (propuestos en ejercicios)

### 🔠 `mayusInvertido`

Convierte el texto: letras minúsculas a mayúsculas y viceversa.

```ts
@Pipe({ name: 'mayusInvertido' })
export class MayusInvertidoPipe implements PipeTransform {
  transform(valor: string): string {
    return valor
      .split('')
      .map(c => c === c.toUpperCase() ? c.toLowerCase() : c.toUpperCase())
      .join('');
  }
}
```

### 🎂 `calcularEdad`

Calcula la edad a partir de una fecha de nacimiento:

```ts
@Pipe({ name: 'calcularEdad' })
export class CalcularEdadPipe implements PipeTransform {
  transform(fechaNacimiento: Date): number {
    const hoy = new Date();
    const nacimiento = new Date(fechaNacimiento);
    let edad = hoy.getFullYear() - nacimiento.getFullYear();
    const m = hoy.getMonth() - nacimiento.getMonth();
    if (m < 0 || (m === 0 && hoy.getDate() < nacimiento.getDate())) {
      edad--;
    }
    return edad;
  }
}
```

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_7_Consumo_API_REST/Modulo_7.md) Módulo 7 - Módulo 9 [➡️](../Modulo_9_Routing_Avanzado/Modulo_9.md)

### 🏠 [Inicio](../README.md)
