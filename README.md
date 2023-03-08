<p align="center">
  <img width="440" height="110" src="https://user-images.githubusercontent.com/42705449/222922168-8548c7b0-92c0-4db8-b219-a286281c844d.png" alt="Panel Admin" tooltip="asd">
</p>

Panel Admin es un la parte FrontEnd de un panel de administración, desarrollado en Vue 3, basado en CoreUI v4.

## Características

- Vue 3 con la modalidad Composition API
- Vuex para mantener el estado de la aplicación
- Desarrollo por módulos
- Fácil escalabilidad
- Rutas autenticadas y no autenticadas
- Fácil de conectar con cualquier backend.

## Módulos

- App: Todo lo relacionado al funcionamiento básico del sistema
- Auth: Autenticación de usuarios para ingreso al sistema (Se puede implementar el registro independiente)
- Sistema. Control de menús, submenús, usuarios

Se pueden agregar más para añadir funcionalidades

## Funcionalidades

- :lock: Ingreso: Validación de usuario y contraseña
- :bookmark_tabs: Menús y Submenús: Listado, creación, actualización y eliminación
- :bust_in_silhouette: Usuarios: Listado, creación, actualización y eliminación
- :package: Inventario: Pagina vacía para la creación de otras secciones
- :shield: Protección de rutas: Solicita al usuario iniciar sesión para acceder a las secciones protegidas.
- :bell: Panel de Acciones Rapidas: Sección para mostrar notificaciones, mensajes o alguna otra información.

## Por desarrollar

- :white_check_mark: Validaciones en formularios
- :warning: Cambio de alertas y mensajes

## Demostración

<div style="text-align:center">

![Página de Ingreso](https://user-images.githubusercontent.com/42705449/222923256-7f57e58b-9d24-4f02-a6e6-7db95b2e75c7.png)

<p align = "center">Página de ingreso</p>

![Página Principal](https://user-images.githubusercontent.com/42705449/222923698-0617d371-2b58-45fa-a446-cd7705c88675.png)

<p align="center">Página principal</p>

![Menús](https://user-images.githubusercontent.com/42705449/222923767-23fc7188-32d9-478a-aa74-aa3471d91a4b.png)

<p align="center">Listado de Menús</p>

![Registrat Menú](https://user-images.githubusercontent.com/42705449/223197021-707bc0fb-8eae-4325-986e-1486e3fba0de.png)

<p align="center">Registrar Menú</p>

![Listado de Usuarios](https://user-images.githubusercontent.com/42705449/223197203-444f2438-7cc4-46e1-96a2-2b055aa8793e.png)

<p align="center">Listado de Usuarios</p>

![Registrar Usuario](https://user-images.githubusercontent.com/42705449/223197598-223d3854-271a-416b-8234-e67cd9efd46c.png)

<p align="center">Registrar Usuario</p>

</div>

## Añadir otro menú

Para este ejemplo, se creará la pagina de _Permisos_ perteneciente al módulo de _Sistema_.

1. Crear page

```
    /src/modules/sistema/views/Permisos.vue
```

2. Registrar el componente y la ruta

```javascript
// src/modules/sistema/routes/index.js

/**
 * Rutas del Módulo Sistema
 */
const routes = [
  // ...
  {
    path: "sistema/permisos",
    name: "sistema-permisos",
    component: () => import("../views/Permisos.vue"),
  },
  // ...
];

export default routes;
```

3. Registrar la ruta en el _state_ de App

```javascript
// src/modules/app/store/state.js

// Menus del Sidebar
menus: [
  {
    name: "Sistema",
    options: [
      // ...
      {
        name: "Permisos",
        icon: "fa-solid fa-user-lock",
        path_name: "sistema-permisos",
        type: 1,
      },
      // ...
    ],
  },
];
```

Ya se puede visualizar el componente
![Nueva Page](https://user-images.githubusercontent.com/42705449/223278630-00c6b68b-e6f6-4754-ab4a-fbe0591378d5.png)

## Instalación

1. Clonar repositorio

```
git clone https://github.com/larh1/panel_admin_vue3.git
```

2. Mover al directorio
3. Instalar dependencias

```
yarn instal
```

4. Lanzar el servidor local

```
yarn serve
```

Se puede acceder por el navegador web, mediante la dirección `http://localhost:8080/` (o la que muestre la terminal)

## Tecnologías usadas

- [Vue](https://vuejs.org/)
- Diseño base: [CoreUI](https://coreui.io/)
- Componentes: [Bootstrap](https://getbootstrap.com/)
- Iconos: [Fontawesome](https://fontawesome.com/)
- Imágen de logotipo: [Flaticon](https://www.flaticon.es/iconos-gratis/collage)
