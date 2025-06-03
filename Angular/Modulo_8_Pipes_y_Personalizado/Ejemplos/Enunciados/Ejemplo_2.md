# 🧪 Ejemplo 2: Formatear fechas con date pipe

## 🎯 Objetivo
Utilizar el pipe `date` de Angular para mostrar fechas con diferentes formatos directamente en la vista.

## 📁 Ruta: src/app/fecha/fecha.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-fecha',
  templateUrl: './fecha.component.html'
})
export class FechaComponent {
  fechaActual = new Date();
}
```

## 📁 Ruta: src/app/fecha/fecha.component.html
```html
<p>Fecha corta: {{ fechaActual | date:'shortDate' }}</p>
<p>Fecha larga: {{ fechaActual | date:'fullDate' }}</p>
<p>Hora: {{ fechaActual | date:'shortTime' }}</p>
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo utilizar el **pipe `date`** para formatear una variable `Date` directamente desde el HTML.  
Permite mostrar la fecha en múltiples formatos sin necesidad de manipularla en el componente.

---

## 🧠 Conceptos aplicados

- Uso de `Date` en TypeScript
- Aplicación del pipe `date` en Angular
- Formateo directo en la plantilla sin modificar la lógica

---

## 💡 Variaciones sugeridas

### ✅ 1. Usar el formato completo de fecha y hora

```html
<p>{{ fechaActual | date:'full' }}</p>
```

📌 **¿Por qué?**: Es útil para mostrar fechas completas en informes o detalles.

---

### ✅ 2. Mostrar solo el día de la semana

```html
<p>{{ fechaActual | date:'EEEE' }}</p>
```

📌 **¿Por qué?**: Muestra solo el nombre del día, útil para resúmenes diarios o agendas.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de que `fechaActual` esté definido como instancia de `Date`.
2. Verifica que en el navegador se muestran las fechas formateadas correctamente.
3. Cambia el valor de `fechaActual` manualmente para ver otras fechas y formatos.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 8](../../Modulo_8.md)

### 🏠 - [Inicio](../../../README.md)

