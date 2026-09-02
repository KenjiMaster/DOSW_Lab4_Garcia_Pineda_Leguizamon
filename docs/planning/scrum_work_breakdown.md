# Planeación del Sistema

## Desglose de trabajo: Épicas, Historias de Usuario y Tareas

La implementación del requerimiento RF-03 ("La aplicación TechCup debe tener un sistema de registro de la forma usuario - contraseña") se desglosa de la siguiente manera:

---

### 1. Épica

| Campo | Descripción |
|------|-------------|
| **ID** | EP-01 |
| **Título** | Autenticación y gestión de identidad de usuarios en TechCup |
| **Descripción** | TechCup necesita esta épica porque ninguna otra funcionalidad del sistema puede exponerse de forma segura sin antes saber quién es el usuario y qué rol tiene. Sin un mecanismo de registro, autenticación y diferenciación de roles (estudiante, capitán, organizador), no es posible aplicar las reglas de negocio que dependen del actor. |
| **Stakeholder** | Organizadores del torneo y la Decanatura. |

---

### 2. Historias de usuario

| Campo | Descripción |
|------|-------------|
| **ID** | HU-01 |
| **Título** | Registro de nuevos usuarios |
| **Descripción** | Como estudiante, quiero registrarme en TechCup con un usuario y una contraseña, para poder acceder a la plataforma y participar en los torneos. |
| **Prioridad** | Alta |
| **Estimación** |  |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-02 |
| **Título** | Inicio de sesión |
| **Descripción** | Como usuario registrado, quiero iniciar sesión con mi usuario y contraseña, para acceder a las funcionalidades de TechCup correspondientes a mi cuenta. |
| **Prioridad** | Alta |
| **Estimación** | |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-03 |
| **Título** | Validación y rechazo de credenciales inválidas |
| **Descripción** | Como usuario, quiero recibir un mensaje claro cuando ingreso credenciales incorrectas o un usuario ya registrado, para entender qué debo corregir y evitar quedar bloqueado sin explicación. |
| **Prioridad** | Media |
| **Estimación** |  |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-04 |
| **Título** | Diferenciación de roles al autenticarse |
| **Descripción** | Como sistema, quiero identificar y asignar el rol correspondiente (estudiante, capitán u organizador) a cada usuario autenticado, para mostrarle únicamente las funcionalidades permitidas según su rol. |
| **Prioridad** | Alta |
| **Estimación** |  |

---

### 3. Tareas

**Tareas de HU-01 — Registro de nuevos usuarios**

| Campo | Descripción |
|------|-------------|
| **ID** | TR-01 |
| **Título** | Diseñar el formulario de registro |
| **ID de la Historia de Usuario asociada** | HU-01 |
| **Descripción** | Diseñar la interfaz gráfica del formulario de registro con los campos de usuario y contraseña, incluyendo validaciones visuales básicas (campos obligatorios, formato). |
| **Tareas requisito** | Ninguna |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-02 |
| **Título** | Implementar el servicio de registro |
| **ID de la Historia de Usuario asociada** | HU-01 |
| **Descripción** | Desarrollar el sistema que reciba usuario y contraseña, y los almacene en el sistema. |
| **Tareas requisito** | TR-01 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-03 |
| **Título** | Validar unicidad y formato de credenciales al registrar |
| **ID de la Historia de Usuario asociada** | HU-01 |
| **Descripción** | Implementar la validación que impide registrar un nombre de usuario ya existente y que exige requisitos mínimos de seguridad en la contraseña. |
| **Tareas requisito** | TR-02 |

**Tareas de HU-02 — Inicio de sesión**

| Campo | Descripción |
|------|-------------|
| **ID** | TR-04 |
| **Título** | Diseñar el formulario de inicio de sesión |
| **ID de la Historia de Usuario asociada** | HU-02 |
| **Descripción** | Diseñar la interfaz gráfica del formulario de login con los campos de usuario y contraseña. |
| **Tareas requisito** | Ninguna |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-05 |
| **Título** | Implementar el servicio de autenticación |
| **ID de la Historia de Usuario asociada** | HU-02 |
| **Descripción** | Desarrollar el sistema que compare las credenciales ingresadas contra las almacenadas y determine si el acceso es válido. |
| **Tareas requisito** | TR-04, TR-02 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-06 |
| **Título** | Implementar manejo de sesión activa |
| **ID de la Historia de Usuario asociada** | HU-02 |
| **Descripción** | Implementar la generación y manejo de la sesión  que se mantiene mientras el usuario navega la plataforma tras iniciar sesión. |
| **Tareas requisito** | TR-05 |

**Tareas de HU-03 — Validación y rechazo de credenciales inválidas**

| Campo | Descripción |
|------|-------------|
| **ID** | TR-07 |
| **Título** | Implementar mensajes de error por credenciales inválidas |
| **ID de la Historia de Usuario asociada** | HU-03 |
| **Descripción** | Mostrar un mensaje claro en el formulario de login cuando el usuario o la contraseña ingresados no coinciden con ningún registro. |
| **Tareas requisito** | TR-05 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-08 |
| **Título** | Registrar intentos de acceso fallidos |
| **ID de la Historia de Usuario asociada** | HU-03 |
| **Descripción** | Implementar un registro de los intentos fallidos de inicio de sesión, como base para futuros controles de seguridad. |
| **Tareas requisito** | TR-05 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-09 |
| **Título** | Pruebas del flujo de validación de credenciales |
| **ID de la Historia de Usuario asociada** | HU-03 |
| **Descripción** | Escribir pruebas unitarias que cubran los casos de credenciales correctas, incorrectas y usuario inexistente. |
| **Tareas requisito** | TR-07 |

**Tareas de HU-04 — Diferenciación de roles al autenticarse**

| Campo | Descripción |
|------|-------------|
| **ID** | TR-10 |
| **Título** | Definir el modelo de datos de roles |
| **ID de la Historia de Usuario asociada** | HU-04 |
| **Descripción** | Diseñar el modelo de datos que asocia a cada usuario uno o más roles (estudiante, capitán, organizador), considerando que un mismo usuario pueda tener más de un rol. |
| **Tareas requisito** | TR-02 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-11 |
| **Título** | Implementar lógica de acceso diferenciado por rol |
| **ID de la Historia de Usuario asociada** | HU-04 |
| **Descripción** | Desarrollar la lógica que, tras un login exitoso, determine el rol del usuario y le presente únicamente el menú y las acciones permitidas para ese rol. |
| **Tareas requisito** | TR-10, TR-05 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-12 |
| **Título** | Pruebas de acceso diferenciado por rol |
| **ID de la Historia de Usuario asociada** | HU-04 |
| **Descripción** | Escribir pruebas de integración que confirmen que cada rol solo puede acceder a las funcionalidades que le corresponden. |
| **Tareas requisito** | TR-11 |


## Video asignacion de puntos

[![Ver Video](https://via.placeholder.com/600x337.png?text=Haz+clic+para+ver+el+video)](https://pruebacorreoescuelaingeduco-my.sharepoint.com/:v:/g/personal/thomas_garcia-g_mail_escuelaing_edu_co/IQAED1O_p7iAT6_6FHt2M9weATUzXODhznvr3qJLSV5Kp1o?e=lagZR2)

Es importante aclarar que este es el link asociado al video, para acceder al video hay que darle en el mismo y sera redirigido hacia la pagina donde se encuentra el video, esto se debe a que los archivos de tipo ".md" no soporta de forma nativa video