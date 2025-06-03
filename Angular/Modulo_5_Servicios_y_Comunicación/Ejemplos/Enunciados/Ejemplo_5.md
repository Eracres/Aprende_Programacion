# 🧪 Ejemplo 5: Servicio con arreglo dinámico

## 🎯 Objetivo
Crear un servicio que gestione un arreglo de mensajes, permitiendo agregar y limpiar elementos desde distintos componentes de la aplicación.

## 📁 Ruta: src/app/mensaje.service.ts

```ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class MensajeService {
  mensajes: string[] = [];

  agregar(mensaje: string) {
    this.mensajes.push(mensaje);
  }

  limpiar() {
    this.mensajes = [];
  }
}
```

---

## ✅ ¿Qué hace este servicio?

Este servicio proporciona una lógica centralizada para manejar mensajes en la aplicación.  
Es útil para mostrar notificaciones, logs u otros textos generados por los usuarios o eventos.  
Gracias a que está decorado con `@Injectable({ providedIn: 'root' })`, está disponible globalmente sin necesidad de registrarlo en los módulos manualmente.

---

## 🧠 Conceptos aplicados

- Creación de servicios reutilizables con `@Injectable`
- Inyección de dependencias a través del sistema de Angular
- Uso de arreglos como estructura de almacenamiento dinámico
- Patrón de diseño singleton en servicios

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar timestamps a los mensajes

```ts
agregar(mensaje: string) {
  const fecha = new Date().toLocaleTimeString();
  this.mensajes.push(`[${fecha}] ${mensaje}`);
}
```

📌 **¿Por qué?**: Permite saber cuándo se generó cada mensaje. Muy útil para depuración o trazabilidad.

---

### ✅ 2. Exponer los mensajes como `Observable`

```ts
import { BehaviorSubject } from 'rxjs';

private mensajesSubject = new BehaviorSubject<string[]>([]);
mensajes$ = this.mensajesSubject.asObservable();

agregar(mensaje: string) {
  this.mensajesSubject.next([...this.mensajesSubject.value, mensaje]);
}
```

📌 **¿Por qué?**: Para reaccionar a los cambios de mensajes en tiempo real desde la vista.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Inyecta el servicio `MensajeService` en un componente.
2. Llama a `agregar()` y comprueba que se añade correctamente al arreglo.
3. Visualiza los mensajes en el HTML con `*ngFor`.
4. Usa `limpiar()` y verifica que el arreglo queda vacío.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 5](../../Modulo_5.md)

### 🏠 - [Inicio](../../../README.md)
