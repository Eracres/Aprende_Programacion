# 📘 Módulo 7: Consumo de APIs con HttpClient

## ❓ ¿Qué es HttpClient?

HttpClient es el servicio de Angular para realizar peticiones HTTP. Permite conectar tu aplicación con APIs REST para enviar y recibir datos.

Angular proporciona este servicio a través del módulo `HttpClientModule`, que debes importar en tu módulo principal o en el módulo correspondiente.

---

## ⚙️ Configuración

Para comenzar a trabajar con APIs necesitas importar el módulo `HttpClientModule`:

```ts
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [
    HttpClientModule
  ]
})
export class AppModule { }
```

También necesitarás inyectar `HttpClient` en tus servicios para realizar peticiones:

```ts
import { HttpClient } from '@angular/common/http';

constructor(private http: HttpClient) {}
```

---

## 📡 Ejemplo de servicio que consume una API

Supongamos que queremos obtener una lista de usuarios desde JSONPlaceholder:

```ts
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class UsuarioService {
  private apiUrl = 'https://jsonplaceholder.typicode.com/users';

  constructor(private http: HttpClient) {}

  getUsuarios(): Observable<any> {
    return this.http.get(this.apiUrl);
  }
}
```

---

## 🧩 Cómo usar el servicio en un componente

```ts
import { Component, OnInit } from '@angular/core';
import { UsuarioService } from '../usuario.service';

@Component({
  selector: 'app-usuarios',
  templateUrl: './usuarios.component.html'
})
export class UsuariosComponent implements OnInit {
  usuarios: any[] = [];

  constructor(private usuarioService: UsuarioService) {}

  ngOnInit(): void {
    this.usuarioService.getUsuarios().subscribe(data => {
      this.usuarios = data;
    });
  }
}
```

```html
<ul>
  <li *ngFor="let usuario of usuarios">{{ usuario.name }}</li>
</ul>
```

---

## ✅ Tipos de peticiones

Angular HttpClient permite realizar varias operaciones comunes:

```ts
this.http.get('url');        // Obtener datos
this.http.post('url', body); // Enviar datos
this.http.put('url', body);  // Actualizar datos
this.http.delete('url');     // Eliminar datos
```

---

## 🛡️ Manejo de errores

Usamos operadores de RxJS como `catchError` para manejar errores:

```ts
import { catchError } from 'rxjs/operators';
import { throwError } from 'rxjs';

getUsuarios(): Observable<any> {
  return this.http.get(this.apiUrl).pipe(
    catchError(error => {
      console.error('Error al obtener usuarios', error);
      return throwError(() => new Error('Error en la petición'));
    })
  );
}
```

---

## 🧠 Buenas prácticas

- Siempre manejar errores con `.pipe(catchError(...))`
- Crear interfaces para los datos que recibes
- Evitar la lógica de negocio directamente en el componente
- Usar `async` en el HTML solo si estás trabajando con `Observables` directamente

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_6_Formularios_y_Validaciones/Modulo_6.md) Módulo 6 - Módulo 8 [➡️](../Modulo_8/Modulo_8.md)

### 🏠 [Inicio](../README.md)
