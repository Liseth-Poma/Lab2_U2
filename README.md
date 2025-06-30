# Consumo de una API RESTful desde una Aplicación Frontend (React)

**Liseth Carolina Poma Lagos**

---

## RESUMEN

En esta práctica se implementó el consumo de una API RESTful utilizando React como frontend. Se empleó la API pública de [JSONPlaceholder](https://jsonplaceholder.typicode.com) para simular un sistema de gestión de usuarios, mensajes y comentarios. A lo largo del laboratorio se desarrollaron servicios reutilizables mediante `axios`, componentes interactivos para manejar datos de la API y una interfaz gráfica adaptada a la estructura existente de la aplicación. El proyecto permitió integrar funcionalidades CRUD (Crear, Leer, Actualizar, Eliminar) y validar el consumo y visualización de datos en tiempo real. Se logró una integración eficiente y dinámica con la API, afianzando conocimientos prácticos sobre el desarrollo frontend moderno y su conexión con servicios RESTful.

**Palabras Clave:** API RESTful, React, Axios

---

## 1. INTRODUCCIÓN

El objetivo de esta práctica es demostrar la capacidad de integrar una API RESTful dentro de una aplicación frontend utilizando React. Se busca aplicar buenas prácticas en el consumo de datos externos, el manejo de estados y errores, así como en la estructuración de componentes y servicios. Esta experiencia fortalece el aprendizaje práctico del desarrollo de interfaces interactivas conectadas con servicios web, resaltando la importancia de mantener una estructura limpia y organizada en los proyectos reales.

---

## 2. OBJETIVO(S)

**2.1 Objetivo General:**
Implementar un frontend funcional con React que consuma una API RESTful simulando operaciones CRUD sobre usuarios, mensajes y comentarios.

**2.2 Objetivos Específicos:**

* Aplicar el uso de `axios` para consumir una API.
* Estructurar componentes y servicios React de forma modular.
* Validar el funcionamiento de cada endpoint con pruebas interactivas.
* Integrar visualmente los resultados en la estructura existente del proyecto.

---

## 3. MARCO TEÓRICO

Una **API RESTful** (Application Programming Interface) permite a distintas aplicaciones comunicarse entre sí utilizando peticiones HTTP (GET, POST, PUT, DELETE). React, por su parte, es una biblioteca de JavaScript para construir interfaces de usuario, especialmente en aplicaciones de una sola página (SPA).

**Axios** es una librería basada en promesas que facilita las solicitudes HTTP hacia APIs desde el navegador. La arquitectura basada en componentes de React permite una separación clara de lógica y presentación, lo cual mejora la mantenibilidad del código.

---

## 4. DESCRIPCIÓN DEL PROCEDIMIENTO

### Paso 1: Instalar dependencias necesarias

```bash
npm install axios
```

![Instalación de axios](https://imgur.com/fLRj4vJ.png)

---

### Paso 2: Crear estructura para React

Se crea la siguiente estructura de carpetas:

```
public/
├── js/
│   ├── react/
│   │   ├── components/
│   │   └── services/
│   ├── register.js
│   └── script.js
```

---

### Paso 3: Crear el servicio API

Ruta: `public/js/react/services/apiService.js`
Se implementan los servicios para usuarios, mensajes y comentarios utilizando `axios`.

---

### Paso 4: Crear componente React para gestionar usuarios

Archivo: `components/gestionusuarios.js`
Implementación de lógica y renderizado de usuarios con formularios para crear y editar.

---

### Paso 5: Agregar ruta en Express

Ruta en `routes/routes.js`:

```js
router.get("/api-manager", isLoggedIn, (req, res) => {
  res.sendFile(views + "/api-manager.html");
});
```

---

### Paso 6: Crear la página HTML para React

Archivo: `views/api-manager.html`

Se integra el componente React que gestiona los usuarios y servicios.

---

### Paso 7: Validación y Presentación de Resultados

1. Iniciar servidor:

```bash
src/node index.js
```

![Servidor ejecutándose](https://imgur.com/pAvbBSU.png)

2. Ingresar a:

[http://localhost:3000/api-manager](http://localhost:3000/api-manager)


![Vista React en navegador](https://imgur.com/cCLTByK.png)

---

### Crear nuevo usuario


![Creación de usuario](https://imgur.com/aKmY6nr.png)

---

### Ver usuario creado en la lista


![Ver usuario creado](https://imgur.com/yiwUNv9.png)

---

### Ver los detalles del usuario


![Detalles de usuario](https://imgur.com/EqUUpQQ.png)

---

### Eliminar usuario


![Eliminar usuario](https://imgur.com/m1KT8Nw.png)

---

### Paso 8: Integrar con el chat existente

Se modifica `public/js/script.js` para obtener perfiles desde la API y enriquecer el sistema de chat con información de usuarios.

---

## 5. ANÁLISIS DE RESULTADOS

Durante el desarrollo de la práctica se verificó que la interacción entre React y la API se realiza de forma efectiva. Los datos obtenidos se visualizaron correctamente y se permitió realizar pruebas de creación, edición, lectura y eliminación. La implementación del `interceptor` en `axios` permitió manejar errores de forma global. Además, la integración con la interfaz actual demuestra la versatilidad de los componentes y la escalabilidad del proyecto.

| Funcionalidad      | Resultado esperado | Resultado obtenido |
| ------------------ | ------------------ | ------------------ |
| Listar usuarios    | ✔️                 | ✔️                 |
| Crear usuario      | ✔️                 | ✔️                 |
| Actualizar usuario | ✔️                 | ✔️                 |
| Eliminar usuario   | ✔️                 | ✔️                 |
| Cargar mensajes    | ✔️                 | ✔️                 |
| Cargar comentarios | ✔️                 | ✔️                 |

---

## Estructura final del proyecto

```
LAB2_U2
├── node_modules
├── src
│   ├── middlewares
│   ├── public
│   │   └── css
│   │   └── img
│   └── js
│       ├── react
│       │   └── services
│       │       └── apiService.js
│       └── components
│           ├── gestionusuarios.js
│           ├── register.js
│           └── script.js
├── routes
│   └── index.js
└── views
    ├── api-manager.html
    ├── index.html
    └── register.html
```


## 6. DISCUSIÓN

El trabajo realizado evidencia la importancia de la modularización del código al momento de consumir servicios REST. React, al ser una herramienta basada en componentes, facilitó la integración visual y lógica de los servicios. El uso de `axios` simplificó las operaciones HTTP y la implementación de pruebas manuales permitió identificar errores y verificar el correcto funcionamiento de las operaciones CRUD. Se destaca la utilidad de trabajar con APIs públicas como `jsonplaceholder` para prácticas académicas y prototipado rápido.

---

## 7. CONCLUSIONES

* Se implementó de forma exitosa el consumo de una API RESTful utilizando React.
* Se diseñó un servicio completo en `axios` que permitió realizar operaciones CRUD sobre los datos.
* Se desarrolló una interfaz interactiva que se integró al sistema existente, fortaleciendo las habilidades de integración entre frontend y backend.
* El uso de una API pública permitió concentrarse en el desarrollo del frontend y la lógica de consumo de datos.
* La estructura final del proyecto quedó ordenada y lista para escalar a nuevos módulos.

---

## 8. BIBLIOGRAFÍA

* Axios. (2024). *Axios HTTP client documentation*. [https://axios-http.com](https://axios-http.com)
* JSONPlaceholder. (2024). *Fake Online REST API*. [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)
* React Docs. (2024). *React – A JavaScript library for building user interfaces*. [https://reactjs.org](https://reactjs.org)

---

