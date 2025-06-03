# 🧪 Ejemplo 1: Importación de HttpClientModule

## 🎯 Objetivo

Habilitar el uso del cliente HTTP en una aplicación Angular mediante la importación del módulo `HttpClientModule` en el módulo raíz.

---

## 📁 Ruta: src/app/app.module.ts

```ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  declarations: [AppComponent],
  imports: [
    BrowserModule,
    HttpClientModule // Importación clave para trabajar con APIs
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo muestra cómo **habilitar el módulo `HttpClientModule`** de Angular para poder hacer peticiones HTTP.  
Sin esta importación, **no se pueden consumir APIs REST** en Angular.

- Angular no activa el servicio `HttpClient` por defecto, por lo que **es obligatorio importar** `HttpClientModule` dentro del `@NgModule` principal (normalmente en `app.module.ts`).
- Una vez hecho esto, cualquier servicio de la aplicación podrá inyectar `HttpClient` y usarlo para peticiones GET, POST, PUT, DELETE, etc.

---

## 🧠 Conceptos aplicados

- Importación de módulos externos en Angular  
- Habilitación del cliente HTTP de Angular (`HttpClient`)  
- Estructura del `AppModule` y su función de configuración

---

## 💡 Variaciones sugeridas

### ✅ 1. Importar `HttpClientModule` en un módulo de características

📁 Ruta: `src/app/otro-modulo/otro-modulo.module.ts`

```ts
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [HttpClientModule]
})
export class UsuarioModule { }
```
📌 **¿Por qué?**: Ideal para mantener el proyecto modularizado. Solo cargas `HttpClient` donde se necesita.

---

### ✅ 2. Usar `HttpClientModule` junto a interceptores HTTP

📁 Ruta: `src/app/interceptors/auth.interceptor.ts`

```ts
import { HTTP_INTERCEPTORS } from '@angular/common/http';
import { MiInterceptor } from './interceptores/mi-interceptor';

@NgModule({
  providers: [
    {
      provide: HTTP_INTERCEPTORS,
      useClass: MiInterceptor,
      multi: true
    }
  ]
})
export class AppModule { }
```
📌 **¿Por qué?**: Los interceptores permiten modificar todas las peticiones o respuestas HTTP (por ejemplo, para agregar tokens JWT o manejar errores globalmente).

---

## ✅ ¿Cómo verificar que funciona correctamente?

Sigue estos pasos para asegurarte de que el ejemplo está implementado correctamente:

1. **Revisa la consola del navegador:**
   - No deben aparecer errores como:
     ```
     NullInjectorError: No provider for HttpClient!
     ```
2. **Ejecuta el proyecto con `ng serve`**
   - Accede a `http://localhost:4200`
   - Si todo está correcto, la app carga sin errores.

3. **Probar HttpClient (opcional):**

📁 Ruta: `src/app/prueba-http.service.ts`

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root'
})
export class PruebaHttpService {
  constructor(private http: HttpClient) {
    this.http.get('https://jsonplaceholder.typicode.com/posts')
      .subscribe(data => console.log('✅ Datos recibidos:', data));
  }
}
```

📌 Inyecta este servicio en `app.component.ts` para probar que la petición se realiza correctamente.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 7](../../Modulo_7.md)

### 🏠 - [Inicio](../../../README.md)
