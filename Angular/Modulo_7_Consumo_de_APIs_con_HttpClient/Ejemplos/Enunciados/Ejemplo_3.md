# 🧪 Ejemplo 3: Inyección de HttpClient en un servicio

## 🎯 Objetivo
Mostrar cómo inyectar el servicio `HttpClient` dentro de un servicio personalizado en Angular para realizar peticiones HTTP.

## 📁 Ruta: src/app/app.module.ts
```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, HttpClientModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## 📁 Ruta: src/app/servicios/datos.service.ts
```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root'
})
export class DatosService {
  constructor(private http: HttpClient) {}

  obtenerDatos() {
    return this.http.get('https://jsonplaceholder.typicode.com/posts');
  }
}
```

## 📁 Ruta: src/app/app.component.ts
```ts
import { Component, OnInit } from '@angular/core';
import { DatosService } from './servicios/datos.service';

@Component({
  selector: 'app-root',
  template: `<ul><li *ngFor="let dato of datos">{{ dato.title }}</li></ul>`
})
export class AppComponent implements OnInit {
  datos: any[] = [];

  constructor(private datosService: DatosService) {}

  ngOnInit(): void {
    this.datosService.obtenerDatos().subscribe(res => {
      this.datos = res;
    });
  }
}
```

---

## ✅ ¿Qué hace este componente?

Este ejemplo muestra cómo inyectar `HttpClient` en un servicio (`DatosService`) para obtener datos de una API externa.  
Luego, el componente principal (`AppComponent`) consume ese servicio y muestra los datos utilizando `*ngFor`.

---

## 🧠 Conceptos aplicados

- Inyección de dependencias en Angular
- Uso de `HttpClient` en servicios
- Subcripción a observables de tipo `HttpClient.get()`
- Visualización dinámica con `*ngFor`

---

## 💡 Variaciones sugeridas

### ✅ 1. Usar tipado con interfaces
```ts
interface Post {
  userId: number;
  id: number;
  title: string;
  body: string;
}

obtenerDatos() {
  return this.http.get<Post[]>('https://jsonplaceholder.typicode.com/posts');
}
```
📌 **¿Por qué?**: Mejora el control de tipos y ayuda a prevenir errores en tiempo de desarrollo.

---

### ✅ 2. Agregar manejo de errores
```ts
obtenerDatos() {
  return this.http.get('https://jsonplaceholder.typicode.com/posts').pipe(
    catchError(error => {
      console.error('Error al obtener los datos', error);
      return of([]);
    })
  );
}
```
📌 **¿Por qué?**: El manejo de errores evita que la app se rompa si la API falla.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de importar `HttpClientModule` en `AppModule`.
2. Verifica que el servicio `DatosService` está inyectado correctamente en el componente.
3. Comprueba que al cargar la app se muestran los títulos de los datos en la plantilla.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 7](../../Modulo_7.md)

### 🏠 - [Inicio](../../../README.md)

