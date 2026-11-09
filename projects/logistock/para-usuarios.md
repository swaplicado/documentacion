# Para usuarios

Logistock reúne aplicaciones para usuarios de inventario, personal de logística
y administración. Las opciones disponibles dependen de los grupos que el
administrador haya asignado a cada cuenta.

## Primeros pasos

1. Abre la aplicación web o móvil que te proporcionó tu organización.
2. Inicia sesión con el usuario y la contraseña asignados.
3. En el inicio verás los módulos habilitados para tus grupos.

Si no aparece un módulo que necesitas, contacta al administrador para revisar
los grupos y almacenes asignados a tu usuario.

## Flujos habituales

### Registrar una captura de inventario

1. En la aplicación móvil, abre **Captura de inventario**.
2. Selecciona el almacén que corresponda.
3. Confirma la fecha de trabajo y completa los renglones solicitados.
4. Revisa los datos y envía la captura.
5. Si la aplicación indica que quedan capturas pendientes, registra las
   restantes para completar el trabajo del día.

La aplicación puede mostrar una captura que ya existe para el mismo almacén y
fecha. Las fechas permitidas y los renglones editables dependen de las reglas
configuradas por la organización. Si no puedes capturar una fecha anterior,
consulta con un supervisor.

### Consultar inventario

Los módulos **Supervisión de inventario** y **Existencias generales** permiten
consultar información según los permisos de la cuenta. Usa la fecha y el
almacén disponibles en cada pantalla para encontrar los datos que necesitas.

### Administrar usuarios y logística

En la aplicación web, según los permisos asignados, están disponibles las
pantallas para administrar:

- Usuarios, grupos, restablecimientos de contraseña y sesiones.
- Almacenes, zonas y asignaciones de almacenes a usuarios.
- Choferes y transportistas.
- Puntos de control, acciones y asignaciones. Cada checkpoint puede marcarse
  como **Permitir escaneo sin conexión** si está en un sitio con señal inestable.
- Configuración de la aplicación.

### Monitorear eventos

Administración y Supervisor Logística pueden consultar el tablero de eventos
en la aplicación web y móvil. Cada fila o tarjeta representa un chofer y muestra
su evento más reciente, su estatus, checkpoint, ubicación, unidad y usuario que
lo registró. La unidad se muestra únicamente cuando está asociada al evento.
Usa el buscador y los filtros para encontrar registros; al seleccionar un
chofer con eventos puedes consultar su historial.

El estatus se deriva del último evento: **Libre** cuando la acción terminó el
flujo, y si no **En tránsito** o **En sitio** según la acción del último evento (la acción marcada como **Es un punto de tránsito** en Administración → Checkpoints → Acciones). Los usuarios de Punto de control solo ven eventos de sus
checkpoints asignados. El tablero se actualiza periódicamente y también permite
refrescar manualmente.

### Consultar los tiempos entre escaneos

En **Eventos**, la pestaña **Tiempos** muestra una fila (web) o tarjeta (móvil) por
viaje, con el tiempo transcurrido desde el escaneo anterior en cada acción y el
total del viaje.

1. Elige el periodo (día, semana, mes, año o, en web, un rango de fechas) y usa las
   flechas para moverte entre periodos.
2. Filtra por chofer o transportista y por estatus (terminado o en curso).
3. En web, **Exportar a Excel** descarga el reporte con los mismos filtros.

Un viaje cuenta en el periodo de su primer escaneo. Si una acción no se escaneó,
su celda queda vacía. Las acciones que se repiten en el viaje (por ejemplo, pesada
o salida de planta) tienen una columna por ocurrencia: "Pesada (1)" y "Pesada (2)".
Las columnas siguen el orden habitual del flujo. Para elegir qué acciones aparecen, el administrador marca
**Mostrar en reporte de tiempos** en cada acción (Administración → Checkpoints).

### Registrar un evento desde un punto de control

En la aplicación móvil, abre **Escanear QR**, selecciona el checkpoint y la
acción cuando se soliciten, y escanea el QR temporal que muestra el chofer.
Revisa el resultado para confirmar el chofer, transportista, checkpoint y
acción. Si el QR ya no es válido, pide al chofer que muestre el código vigente.

El mismo módulo lee las invitaciones de visitantes (ver más abajo). Elige
**Entrada** o **Salida** cuando aparezca "Visitante detectado".

#### Checkpoints sin conexión

Si el administrador activó el modo sin conexión en tu checkpoint y el teléfono
no tiene señal, el escaneo del chofer se guarda en el teléfono y aparece
**Guardado sin conexión**. Se envía solo al recuperar la conexión, al abrir la
app o al pulsar **Enviar ahora** en la tarjeta de escaneos pendientes. Ten en
cuenta que:

- La validez del QR se confirma hasta que el escaneo se envía; el servidor puede
  rechazarlo, por ejemplo si pasaron más de 48 horas (configurable) o si el QR
  no era válido. Los rechazados quedan visibles con su motivo y puedes
  descartarlos.
- La hora del evento es la del escaneo, no la del envío. Mantén bien la fecha y
  hora del teléfono.
- No cierres sesión ni borres los datos de la app con escaneos pendientes.
- Las invitaciones de visitantes siempre requieren conexión.

### Invitar visitantes

Los roles **Anfitrión** y **Administrador de accesos** (asignado solo por un
superusuario) usan el módulo **Invitaciones**, en web y móvil:

1. Crea una invitación con nombre del visitante, motivo, número de
   acompañantes y vigencia (1, 2, 4, 8 horas u otro número de horas). Empieza a
   valer de inmediato.
2. Comparte o guarda la imagen del QR (por ejemplo, por WhatsApp). El QR
   representa al grupo completo y puede escanearse varias veces mientras esté
   vigente.
3. Busca y filtra tus invitaciones por estado (vigente, pendiente, vencida o
   cancelada) y cancela las que ya no se necesiten. El Administrador de accesos
   ve y cancela las de todos.
4. En la pestaña **Escaneos** consulta las entradas y salidas por periodo,
   movimiento y resultado (autorizado o rechazado).

El personal de Punto de control o el Administrador de accesos escanea el QR en
**Escanear QR** y elige entrada o salida.

### Activar la aplicación de choferes

1. Solicita al administrador un código de activación.
2. Abre **Logistock Chofer** e ingresa el código de un solo uso.
3. Una vez activada la cuenta, muestra el QR temporal al personal que lo
   verifique.
4. El QR y el código numérico cambian cada 30 segundos. Mantén abierta la
   aplicación mientras se realiza la verificación.

El código de activación no debe compartirse con otras personas. Si caduca, ya
fue utilizado o no funciona, pide al administrador que emita uno nuevo.

### Perfil y cierre de sesión

En **Perfil** puedes consultar la información de la cuenta y cerrar sesión.
Cuando el dispositivo lo admite, la aplicación móvil puede ofrecer acceso
biométrico después de un inicio de sesión normal. Al cerrar sesión, se eliminan
las credenciales biométricas guardadas por la aplicación.

## Preguntas frecuentes

### ¿Por qué no veo un módulo?

Los módulos dependen de tus grupos y permisos. Pide al administrador que
confirme la configuración de tu cuenta.

### ¿Por qué no puedo registrar una fecha anterior?

La organización controla si se permiten capturas históricas para ciertos
usuarios. Confirma la fecha de trabajo y consulta al supervisor.

### ¿Por qué no aparecen almacenes?

Tu cuenta necesita tener almacenes asignados. Contacta al administrador.

### ¿El QR del chofer es permanente?

No. El QR y su código numérico rotan cada 30 segundos. Usa el código que se
muestra en ese momento.

## Solución de problemas

| Situación | Qué hacer |
|---|---|
| No puedo iniciar sesión | Verifica tus credenciales y conexión. Si el problema continúa, contacta al administrador. |
| No aparece un módulo | Solicita revisar tus grupos y permisos. |
| No puedo elegir una fecha de captura | Confirma la fecha de trabajo y consulta al supervisor sobre la política de capturas históricas. |
| No aparecen almacenes | Solicita revisar la asignación de almacenes de tu cuenta. |
| El QR no se verifica | Comprueba que el código esté vigente y vuelve a mostrar el QR actual. |
| Un escaneo sin conexión aparece rechazado | Lee el motivo en la tarjeta de pendientes. Si es antiguo o inválido, descártalo y pide al chofer escanear de nuevo con conexión. |
| La aplicación no conecta | Comprueba la conexión a internet e informa al soporte si el problema persiste. |

No envíes contraseñas, códigos de activación ni capturas que revelen
credenciales al solicitar soporte.
