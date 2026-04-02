# Documentación Frontend

- Frontend (FE): "`optima.com`"
- API (BE): "`api.optima.com`"

## Definición de los flujos de la aplicación
### 1. Formulario Registro de Organización y Usuario

El formulario captura los siguientes datos:
- **Datos Personales:** Nombre, Email, Password y Confirmación.
- **Datos Organización:** Nombre de la organización.

Validaciones en tiempo real (FE):
Al escribir el email y el nombre de la organización, el FE consulta al BE para verificar disponibilidad.
- GET: api.optima.com/auth/validation/email/`{email}`
- GET: api.optima.com/auth/validation/organization/`{organization_name}`

Match de Password: Validación visual de que ambos campos de contraseña coinciden.

Al validar los campos se enviarán los datos al backend.

`POST: api.optima.com/auth/register`

Si la respuesta del backend en correcta se recibirá la informacion de la organización, con el slug recibido se hara una redirección al login de la oprganización: optima.com/{`organization-slug`}.

Si la respuesta del BE es errónea se mostrará un modal con el mensaje de error.

---