# 🧪 Ejemplo 3: *ngSwitch – Condición múltiple

## 🎯 Objetivo
Utilizar la directiva `*ngSwitch` para mostrar distintos bloques de contenido en función del valor de una variable.

## 📁 Ruta: src/app/switch/switch.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-switch',
  templateUrl: './switch.component.html'
})
export class SwitchComponent {
  nivel = 2;
}
```

## 📁 Ruta: src/app/switch/switch.component.html
```html
<div [ngSwitch]="nivel">
  <p *ngSwitchCase="1">Nivel uno</p>
  <p *ngSwitchCase="2">Nivel dos</p>
  <p *ngSwitchDefault>Nivel desconocido</p>
</div>
```

---

## ✅ ¿Qué hace este componente?

Este componente muestra cómo usar la directiva `*ngSwitch` para evaluar una variable (`nivel`) y mostrar diferentes bloques HTML dependiendo de su valor.

- Si `nivel` es 1, se muestra "Nivel uno".
- Si `nivel` es 2, se muestra "Nivel dos".
- Si `nivel` no coincide con ninguno de los casos anteriores, se muestra "Nivel desconocido".

Esto permite condicionar múltiples posibilidades sin necesidad de múltiples `*ngIf`.

---

## 🧠 Conceptos aplicados

- Directiva `ngSwitch`
- Directivas auxiliares `*ngSwitchCase` y `*ngSwitchDefault`
- Evaluación condicional múltiple en plantillas Angular
- Limpieza estructural del HTML

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar el valor de `nivel` a 1 o 3
```ts
nivel = 1; // Mostrará "Nivel uno"
nivel = 3; // Mostrará "Nivel desconocido"
```
📌 **¿Por qué?**: Puedes probar cómo reacciona la interfaz a distintos valores del modelo.

---

### ✅ 2. Reemplazar `<p>` por componentes completos
```html
<app-nivel1 *ngSwitchCase="1"></app-nivel1>
<app-nivel2 *ngSwitchCase="2"></app-nivel2>
```
📌 **¿Por qué?**: Permite cargar componentes completos según el contexto lógico.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Declara el componente `SwitchComponent` en el módulo.
2. Usa su selector (`<app-switch>`) en una vista para visualizarlo.
3. Cambia el valor de `nivel` y verifica cómo cambia el contenido renderizado.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)


