# 📋 Ejercicio 1: Bienvenida con interpolación

## 🎯 Objetivo
Practicar la creación de un componente Angular básico que utilice interpolación de variables para mostrar contenido dinámico.

---

## 📝 Instrucciones

1. Crea un componente llamado `bienvenida`:
```bash
ng generate component bienvenida
```

2. En `bienvenida.component.ts`, declara una variable:
```ts
usuario: string = 'María';
```

3. En `bienvenida.component.html`, muestra el mensaje:
```html
<h3>Hola, {{ usuario }}. Bienvenida a Angular 👋</h3>
```

4. En `app.component.html`, usa el componente:
```html
<app-bienvenida></app-bienvenida>
```

---

## ✅ Criterios de evaluación

- ✅ El componente debe compilar sin errores
- ✅ El mensaje debe mostrar correctamente el nombre del usuario
- ✅ Se debe usar interpolación (`{{ }}`)

---

## 💡 Sugerencias opcionales

Haz que el nombre se reciba por `@Input()`:
```ts
@Input() usuario: string = '';
```

Y úsalo desde el padre:
```html
<app-bienvenida [usuario]="'Carlos'"></app-bienvenida>
```

---

## 🔁 Navegación

### 📋 - [⬅️](./Ejercicio_0.md) Ejercicio 0 - Módulo 2 [➡️](../../../Modulo_2_Componentes_y_Data_Binding/Modulo_2.md)

### 📋 - [Volver a Ejercicios](../README.md)

### 🧪 - [Ir a Ejemplos](../../Ejemplos/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md) 

### 🏠 - [Inicio](../../../README.md)
