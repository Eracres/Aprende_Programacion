# 🧪 Ejemplo 2: Property binding

## 🎯 Objetivo
Mostrar cómo enlazar propiedades de elementos HTML con variables del componente utilizando `[property]`.

## 📁 Ruta: src/app/imagen/imagen.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-imagen',
  templateUrl: './imagen.component.html'
})
export class ImagenComponent {
  urlImagen: string = 'https://angular.io/assets/images/logos/angular/angular.png';
  descripcion: string = 'Logo de Angular';
}
```

## 📁 Ruta: src/app/imagen/imagen.component.html
```html
<img [src]="urlImagen" [alt]="descripcion" width="150">
```

---

## ✅ ¿Qué hace este componente?

Este componente utiliza **property binding** para asignar dinámicamente valores a atributos HTML (`src`, `alt`, etc.).  
Esto permite que el contenido visual se actualice automáticamente si cambian los valores del componente.

---

## 🧠 Conceptos aplicados

- Property binding con corchetes `[ ]`
- Enlace unidireccional desde el componente al DOM
- Uso de variables para modificar atributos HTML

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar la imagen desde el componente

```ts
urlImagen = 'https://upload.wikimedia.org/wikipedia/commons/2/2f/Google_2015_logo.svg';
```

📌 **¿Por qué?**: Permite hacer componentes reutilizables con distintas fuentes dinámicas.

---

### ✅ 2. Mostrar múltiples imágenes con *ngFor

```ts
imagenes = [
  { src: 'img1.jpg', alt: 'Imagen 1' },
  { src: 'img2.jpg', alt: 'Imagen 2' }
];
```

```html
<img *ngFor="let img of imagenes" [src]="img.src" [alt]="img.alt">
```

📌 **¿Por qué?**: Muy útil para galerías u obtener datos de una API.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de declarar el componente en el módulo.
2. Usa el selector `<app-imagen>` en tu plantilla principal.
3. Verifica que la imagen se carga y muestra con los atributos correctos.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)


