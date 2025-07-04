---
sidebar_position: 1
title: Flujo de Recursos
---

## Consulta de Recursos

**Descripción del Flujo:**

Este flujo describe el proceso para consultar los recursos.
Existen dos formas de ver los recursos, la del administrador desde un panel administrativo y la del cliente que es la vista demostrativa.

### El Administrador Consulta los Recursos
1. **Acceso al dashboard de administración**
   - El Administrador debe iniciar sesión para poder acceder al panel.
   - La opción para acceder al panel solo se muestra en el menú si la sesión es activa
2. **Mostrar el dashboard administrativo**
   - El administrador accede al panel administrativo con una vista práctica y resumida de los recursos
   - Visualiza la lista de recursos.
3. **Acciones disponibles**
   - En la lista de recursos cada una muestra las siguientes acciones disponibles
      - Editar recurso mostrando la página de edición.
      - Eliminar recurso mostrando un mensaje de confirmación.
      - Detalle del recurso.

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Administrador accede a la aplicación]
    B --> C{¿Sesión activa?}
    C -->|No| D[Redirige a inicio de sesión]
    D --> B
    C -->|Sí| E[Muestra menú con opción de administración]
    E --> F[Selecciona opción: Panel de recursos]
    F --> G[Muestra dashboard con lista de recursos]
    G --> H[Selecciona acción sobre un recurso]
    H --> I{¿Acción seleccionada?}
    I -->|Editar| J[Redirige a formulario de edición]
    I -->|Eliminar| K[Muestra mensaje de confirmación]
    I -->|Detalle| L[Redirige a vista detallada del recurso]
    J --> M[Regresa al dashboard]
    K --> M
    L --> M
    M --> N[Fin]

```

### El Cliente Consulta los Recursos
1. **Visualización de la Página Principal**  
   - La página se muestra sin necesidad de iniciar sesión.
   - La pantalla muestra una carga inicial de todos los recursos disponibles para ese día.
   - El cliente ve la opción de buscar el recurso en el inventario disponible.
2. **Búsqueda y Consulta de Disponibilidad**  
   - El cliente selecciona la fecha (obligatorio), la hora (opcional) y el tipo de recurso (opcional).
     - Si hay recursos disponibles, continúa el flujo.
     - Si no, se muestra un mensaje que invita a elegir otra fecha o recurso.
3. **Selección de Recurso**  
   - El cliente puede acceder a los detalles de un recurso.

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Visualización de la Página Principal]
    B --> C[Muestra recursos disponibles para el día]
    C --> D[Cliente busca en el inventario]

    D --> E[Selecciona fecha, hora y tipo de recurso]
    E --> F{¿Hay recursos disponibles?}
    F -->|No| G[Muestra mensaje de error o sugiere otra fecha]
    G --> D
    F -->|Sí| H[Cliente accede al detalle del recurso]
    H --> I[Fin]

```

---

## Consulta del detalle de un recurso

**Descripción del Flujo:**

Este flujo describe el proceso para consultar el detalle del recurso.
Existen dos formas de ver el detalle del recurso, la del administrador desde un panel administrativo y la del cliente que es la vista demostrativa.

### El Administrador Consulta el detalle de un recurso.

1. **Acceso al dashboard de administración**
   - El Administrador debe iniciar sesión para poder acceder al panel.
   - La opción para acceder al panel solo se muestra en el menú si la sesión es activa
2. **Mostrar el dashboard administrativo**
   - El administrador accede al panel administrativo con una vista práctica y resumida de los recursos
   - Visualiza la lista de recursos.
3. **Selección de Recurso**  
   - El administrador puede acceder a los detalles de un recurso al seleccionar uno desde el dashboard.
4. **Visualización del detalle**
   - Se muestra la página con todos los detalles relevantes para el administrador relacionados con este recurso.
5. **Regresar al dashboard**
   - Al terminar de revisar el recurso el administrador puede regresar al dashboard y seguir consultando otros recursos.

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Administrador accede a la aplicación]
    B --> C{¿Sesión activa?}
    C -->|No| D[Redirige a inicio de sesión]
    D --> B
    C -->|Sí| E[Muestra menú con opción de administración]
    E --> F[Selecciona opción: Panel de recursos]
    F --> G[Muestra dashboard con lista de recursos]
    G --> H[Selecciona recurso para ver detalle]
    H --> I[Muestra información completa del recurso]
    I --> J[Regresa al dashboard]
    J --> K[Fin]

```

### El Cliente Consulta el detalle del Recurso
1. **Visualización de la Página Principal**  
   - La página se muestra sin necesidad de iniciar sesión.
   - La pantalla muestra una carga inicial de todos los recursos disponibles para ese día.
   - El cliente ve la opción de buscar el recurso en el inventario disponible.
2. **Búsqueda y Consulta de Disponibilidad**  
   - El cliente selecciona la fecha (obligatorio), la hora (opcional) y el tipo de recurso (opcional).
     - Si hay recursos disponibles, continúa el flujo.
     - Si no, se muestra un mensaje que invita a elegir otra fecha o recurso.
3. **Selección de Recurso**  
   - El cliente puede acceder a los detalles de un recurso al seleccionar uno desde la página principal.
4. **Visualización del detalle**
   - Se muestra la página con todos los detalles relevantes para el cliente relacionados con este recurso.
5. **Regresar a la página principal**
   - Al terminar de revisar el recurso el cliente puede regresar a la página principal para seguir buscando.

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Visualización de la Página Principal]
    B --> C[Muestra recursos disponibles para el día]
    C --> D[Cliente busca en el inventario]

    D --> E[Selecciona fecha, hora y tipo de recurso]
    E --> F{¿Hay recursos disponibles?}
    F -->|No| G[Muestra mensaje de error o sugiere otra fecha]
    G --> D
    F -->|Sí| H[Cliente selecciona un recurso]
    H --> I[Muestra detalle del recurso]
    I --> J[Regresa a la página principal]
    J --> K[Fin]

```

---

## Crear un Recurso

**Descripción del Flujo:**

Este flujo describe el proceso para que un administrador cree un recurso en el sistema. 

1. **Acceso al dashboard de administración**
   - El Administrador debe iniciar sesión para poder acceder al panel.
   - La opción para acceder al panel solo se muestra en el menú si la sesión es activa.
2. **Mostrar el dashboard administrativo**
   - El administrador accede al panel administrativo con una vista práctica y resumida de los recursos
   - Visualiza la lista de recursos.
3. **Crear un recurso**
   - En la parte superior de la lista se encuentra la acción para crear un nuevo recurso
   - Al seleccionarla se llevará al usuario a la página de creación.
4. **Mostrar Formulario**
   - Al ingresar a la página de creación de recursos se mostrará el formulario de los datos requeridos
   - Se validarán los campos obligatorios antes de guardar los datos
   - Si pasa las validaciones se guarda la información
5. **Notificación de Resultado:**  
   - El usuario recibe una notificación confirmando que el recurso ha sido registrado, o si ocurrió algún error.
6. **Regreso al panel principal**
   - Al finalizar la acción de creación se regresa al dashboard

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Administrador accede a la aplicación]
    B --> C{¿Sesión activa?}
    C -->|No| D[Redirige a inicio de sesión]
    D --> B
    C -->|Sí| E[Muestra menú con opción de administración]
    E --> F[Selecciona opción: Panel de recursos]
    F --> G[Muestra dashboard con lista de recursos]
    G --> H[Selecciona acción: Crear nuevo recurso]
    H --> I[Muestra formulario de creación]
    I --> J{¿Formulario válido?}
    J -->|No| K[Muestra errores de validación]
    K --> I
    J -->|Sí| L[Guarda información del recurso]
    L --> M[Notifica resultado al administrador]
    M --> N[Regresa al dashboard]
    N --> O[Fin]

```

---

## Editar un Recurso

**Descripción del Flujo:**

Este flujo describe el proceso para que se edite un recurso en el sistema.

1. **Acceso al panel de administración**
   - El Administrador debe iniciar sesión para poder acceder al panel.
   - La opción para acceder al panel solo se muestra en el menú si la sesión es activa.
2. **Mostrar el panel administrativo**
   - El administrador accede al panel administrativo con una vista práctica y resumida de los recursos
   - Visualiza la lista de recursos.
3. **Editar un recurso**
   - En la lista se encuentra la acción para editar un recurso
   - Al seleccionarla se llevará al usuario a la página de edición.
4. **Mostrar Formulario**
   - Al ingresar a la página de edición de recursos se mostrará el formulario con los datos en sus respectivos campos
   - Se validarán los campos obligatorios antes de guardar los datos
   - Si pasa las validaciones se guarda la información
5. **Notificación de Resultado:**  
   - El usuario recibe una notificación confirmando que el recurso ha sido actualizado, o si ocurrió algún error.
6. **Regreso al panel principal**
   - Al finalizar la acción de edición se regresa al dashboard

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Administrador accede a la aplicación]
    B --> C{¿Sesión activa?}
    C -->|No| D[Redirige a inicio de sesión]
    D --> B
    C -->|Sí| E[Muestra menú con opción de administración]
    E --> F[Selecciona opción: Panel de recursos]
    F --> G[Muestra dashboard con lista de recursos]
    G --> H[Selecciona acción: Editar recurso]
    H --> I[Muestra formulario con datos actuales]
    I --> J{¿Formulario válido?}
    J -->|No| K[Muestra errores de validación]
    K --> I
    J -->|Sí| L[Guarda cambios en la base de datos]
    L --> M[Notifica resultado al administrador]
    M --> N[Regresa al dashboard]
    N --> O[Fin]

```

---

## Eliminar un Recurso

**Descripción del Flujo:**

Este flujo describe el proceso para que se elimine un recurso en el sistema.
1. **Acceso al panel de administración**
   - El Administrador debe iniciar sesión para poder acceder al panel.
   - La opción para acceder al panel solo se muestra en el menú si la sesión es activa.
2. **Mostrar el panel administrativo**
   - El administrador accede al panel administrativo con una vista práctica y resumida de los recursos
   - Visualiza la lista de recursos.
3. **Eliminar un recurso**
   - En la lista se encuentra la acción para eliminar o bloquear un recurso
   - La acción de bloqueo siempre está presente.
   - La acción de eliminación solo se muestra si ese recurso no tiene ninguna reserva activa y pagada asociada.
4. **Mostrar mensaje de confirmación**
   - Se muestra un mensaje para confirmar la acción en dos escenarios posibles.
      - Si el recurso tiene al menos una reserva activa y pagada, se bloqueará el recurso para que nadie más pueda reservarlo.
      - Si no tiene ninguna reserva asociada se pedirá confirmar la acción de eliminación y se actualizará la base de datos
   - En caso de cancelar la acción el mensaje solo se cerrará y no se guardará ningún cambio.
5. **Proceso de eliminación**
   - Existen dos formas dependiendo el historial de reservas del recurso
      - Si se reservó y pagó al menos una vez, el estatus del recurso se cambia a eliminado.
      - Si nunca se reservó y pagó al menos una vez, se eliminará físicamente de la base de datos.
5. **Notificación de cambios**
   - El sistema notifica de la cancelación de la reserva a todos los clientes donde los estatus fueran pendiente o autorizada.
   - También se mostrará un mensaje de confirmación de acción al administrador.
6. **Ocultar mensaje**
   - Se cierra el mensaje y se muestra de nuevo el dashboard.

**Diagrama**
```mermaid
graph TD;
    A[Inicio] --> B[Administrador accede a la aplicación]
    B --> C{¿Sesión activa?}
    C -->|No| D[Redirige a inicio de sesión]
    D --> B
    C -->|Sí| E[Muestra menú con opción de administración]
    E --> F[Selecciona opción: Panel de recursos]
    F --> G[Muestra dashboard con lista de recursos]
    G --> H[Selecciona acción: Eliminar o Bloquear recurso]
    H --> I{¿Tiene reservas activas y pagadas?}
    I -->|Sí| J[Actualiza estado del recurso a Bloqueado]
    I -->|No| K[Muestra mensaje de confirmación de eliminación]
    K --> L{¿Confirma eliminación?}
    L -->|Sí| N{¿Tiene historial de reservas pagadas?}
    L -->|No| M[Cierra mensaje sin cambios]
    N -->|Sí| O[Actualiza estado del recurso a Eliminado]
    N -->|No| P[Elimina recurso físicamente de la base de datos]
    O --> Q[Notifica a clientes con reservas pendientes o autorizadas]
    P --> Q
    J --> Q
    Q --> R[Notifica al administrador]
    R --> S[Muestra nuevamente el dashboard]
    M --> S
    S --> T[Fin]

```