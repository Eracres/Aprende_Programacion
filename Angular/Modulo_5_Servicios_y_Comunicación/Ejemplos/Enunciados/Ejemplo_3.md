# 🧪 Ejemplo 3: Servicio compartido entre componentes

## 🎯 Objetivo
Demostrar cómo compartir un estado o funcionalidad entre componentes independientes usando un servicio inyectado.

---

## 📁 Ruta: src/app/contador.service.ts

```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class ContadorService {
  valor = 0;

  incrementar() {
    this.valor++;
  }

  obtenerValor() {
    return this.valor;
  }
}
```

---

## 📁 Ruta: src/app/boton/boton.component.ts

```ts
import { Component } from '@angular/core';
import { ContadorService } from '../contador.service';

@Component({
  selector: 'app-boton',
  template: `<button (click)="incrementar()">Incrementar</button>`
})
export class BotonComponent {
  constructor(private contador: ContadorService) {}

  incrementar() {
    this.contador.incrementar();
  }
}
```

---

## 📁 Ruta: src/app/resultado/resultado.component.ts

```ts
import { Component } from '@angular/core';
import { ContadorService } from '../contador.service';

@Component({
  selector: 'app-resultado',
  template: `<p>Valor actual: {{ contador.obtenerValor() }}</p>`
})
export class ResultadoComponent {
  constructor(public contador: ContadorService) {}
}
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo permite que varios componentes compartan una **única instancia de un servicio**, facilitando así la comunicación indirecta entre ellos.

- `BotonComponent` modifica el estado del servicio.
- `ResultadoComponent` muestra el estado actualizado automáticamente.
- El servicio `ContadorService` actúa como una **fuente centralizada de datos**.

---

## 🧠 Conceptos aplicados

- Inyección de dependencias
- Servicios como Singleton en Angular (`providedIn: 'root'`)
- Compartir estado entre componentes
- Comunicación sin `@Input()` / `@Output()`

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar un método para reiniciar el contador

```ts
reiniciar() {
  this.valor = 0;
}
```

📌 **¿Por qué?**: Permite reiniciar el estado desde cualquier componente.

---

### ✅ 2. Mostrar el valor actualizado en tiempo real con Observables

📁 Ruta: src/app/contador.service.ts

```ts
import { BehaviorSubject } from 'rxjs';

private valorSubject = new BehaviorSubject<number>(0);
valor$ = this.valorSubject.asObservable();

incrementar() {
  this.valorSubject.next(this.valorSubject.value + 1);
}
```

📌 **¿Por qué?**: Mejora la reactividad del estado compartido.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de declarar los componentes en tu `AppModule`.
2. Añade `<app-boton>` y `<app-resultado>` en tu plantilla principal (`app.component.html`).
3. Haz clic en el botón y verifica que el contador se incrementa y actualiza en pantalla.
4. Si modificas el servicio, todos los componentes reflejan los cambios.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)
