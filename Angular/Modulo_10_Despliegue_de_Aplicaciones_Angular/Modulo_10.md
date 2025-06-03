# 📘 Módulo 10: Despliegue de Aplicaciones Angular

## ❓ ¿Por qué desplegar una aplicación?

El despliegue permite hacer pública tu aplicación Angular para que pueda ser accedida desde cualquier parte del mundo.  
Aprender a compilar y publicar tu app es el último paso del ciclo de desarrollo.

---

## 🛠️ Compilar la aplicación para producción

Angular permite compilar la app optimizada para producción con el siguiente comando:

```bash
ng build --configuration production
```

Este comando genera una carpeta `dist/` con todos los archivos listos para ser publicados.

---

## 🔥 Despliegue en Firebase

### ✅ Paso a paso:

1. Instala Firebase CLI si no lo tienes:
   ```bash
   npm install -g firebase-tools
   ```

2. Inicia sesión en tu cuenta:
   ```bash
   firebase login
   ```

3. Inicializa el proyecto en la raíz del proyecto Angular:
   ```bash
   firebase init
   ```

   - Selecciona **Hosting**
   - Selecciona tu proyecto o crea uno nuevo
   - Indica `dist/[nombre-proyecto]` como carpeta a publicar
   - Acepta configuración como SPA

4. Despliega:
   ```bash
   firebase deploy
   ```

---

## 🌍 Despliegue en Netlify o Vercel

### Netlify (interfaz web)
1. Accede a [https://www.netlify.com](https://www.netlify.com)
2. Crea cuenta o inicia sesión
3. Arrastra la carpeta `dist/` al área de despliegue

### Vercel (usando CLI)
1. Instala Vercel CLI:
   ```bash
   npm install -g vercel
   ```

2. Ejecuta:
   ```bash
   vercel
   ```

   - Selecciona la carpeta `dist/` y sigue instrucciones.

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### [⬅️](../Modulo_9_Autenticacion_JWT/Modulo_9.md) Módulo 9 - Módulo 11 [➡️](../Modulo_11.md)

### 🏠 [Inicio](../README.md)
