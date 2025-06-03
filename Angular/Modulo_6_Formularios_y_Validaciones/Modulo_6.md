# 📘 Módulo 6: Formularios y Validaciones

## ❓ ¿Qué son los formularios en Angular?

Angular ofrece potentes herramientas para trabajar con formularios web. Podemos recoger información del usuario, validar campos, reaccionar a eventos de cambio y enviar datos de manera eficiente.

Existen dos enfoques principales para formularios:

- **Template-driven (basado en plantilla):** Se configura desde el HTML usando `[(ngModel)]`
- **Reactive forms (basado en clases):** Se configura desde TypeScript usando `FormGroup` y `FormControl`

En este módulo trabajaremos **con formularios template-driven**.

---

## ✅ ¿Cómo usar Template-driven forms?

1. Importa el módulo `FormsModule` en `app.module.ts`:
```ts
import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [FormsModule]
})
export class AppModule {}
```

2. Usa `[(ngModel)]` en los campos del formulario:
```html
<form (ngSubmit)="enviar()">
  <input [(ngModel)]="nombre" name="nombre" required>
  <button type="submit">Enviar</button>
</form>
```

3. Define las propiedades en el componente:
```ts
export class FormularioComponent {
  nombre: string = '';
  enviar() {
    alert('Enviado: ' + this.nombre);
  }
}
```

---

## 🧩 ¿Qué es ngModel?

Es una directiva que permite el **two-way data binding**. Lo que el usuario escribe se refleja automáticamente en la variable, y viceversa.

```html
<input [(ngModel)]="usuario" name="usuario">
```

---

## ✅ Validaciones básicas en Angular

Angular permite aplicar validaciones automáticamente usando atributos estándar como:

- `required`
- `minlength`
- `maxlength`
- `pattern`
- `email`

También puedes mostrar mensajes de error con condiciones:

```html
<input [(ngModel)]="correo" name="correo" required email #campo="ngModel">
<div *ngIf="campo.invalid && campo.touched">
  <small *ngIf="campo.errors?.required">Este campo es obligatorio</small>
  <small *ngIf="campo.errors?.email">Formato de email inválido</small>
</div>
```

---

## 🧠 ¿Por qué usar formularios en Angular?

- Facilitan la interacción con el usuario
- Validan datos antes de enviarlos
- Permiten capturar, procesar y enviar información de forma segura
- Se integran con servicios y backends

---

## ✅ Casos típicos de uso

- Formulario de contacto
- Registro de usuario
- Autenticación/login
- Encuestas o encuestas dinámicas

---

## 🧪 Ejemplos de este módulo

#### [🔗 Ver ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Ver ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_5_Servicios_y_Comunicación/Modulo_5.md) Módulo 5 - Módulo 7 [➡️](../Modulo_7_Consumo_de_APIs_con_HttpClient/Modulo_7.md)

### 🏠 [Inicio](../README.md)
