# Sistema de Gestión de Alquiler de Habitaciones y Convivencia para Estudiantes (RoomieHub)

## Miembros del grupo L1-DF-AM-4

1. Nolasco Calderón, Ángel
1. Al Khyat, Khaled
1. De la Fuente Hernández, Gonzalo
1. Galocha López, Adrián

## 1. Introducción al problema

- El proyecto "RoomieHub" consiste en el desarrollo de un sistema de información diseñado específicamente para la gestión de alquiler de habitaciones, viviendas completas y la organización de la convivencia para estudiantes. La plataforma busca actuar como intermediario y facilitador entre personas que disponen de inmuebles y estudiantes que necesitan alojamiento durante su curso académico.
- En el sistema tenemos cuatro tipos de usurarios:
    - Inquilino (Estudiantes): Buscan alojamiento. Tienen la flexibilidad de alquilar una habitación en un piso compartido o, si vienen en grupo, una vivienda completa.
    - Propietario: Dueños o gestores de sus inmuebles que publican sus viviendas o habitaciones disponibles.
    - Administrador del sistema: Personal encargado de mantener la plataforma.
    - Avalista: Se encargará de llevar a cabo los avales de dinero para los inquilinos.
- Actualmente, la búsqueda de alojamiento para estudiantes y la posterior gestión se realiza de forma caótica. Se utilizan plataformas genéricas, grupos de redes sociales o el tradicional "boca a boca", lo que genera varios problemas:
    - Falta de confianza y seguridad, ya que abundan las estafas con los pagos de las fianzas y reservas por adelantado.
    - Incompatibilidad de perfiles, ya que al alquilar habitaciones sueltas, los estudiantes suelen acabar viviendo con desconocidos sin saber si sus hábitos de estudio o estilo de vida son compatibles, lo que genera problemas de convivencia.
    - Gestión de pagos desconocida, ya que el pago de alquileres, recibos de luz o agua, y fianzas se suele hacer en efectivo o por transferencias manuales, sin un registro claro que protega ambas partes.
    - Rigidez, ya que las inmobiliarias tradicionales siempre imponen contratos de un año completo, cuando los estudiantes a menudo necesitan contratos de 9 o 10 meses, la duración del curso escolar.
- RoomieHub nace con la expectativa de solucionar estos inconvenientes centralizando todo el proceso. Se espera que el sistema permita:
    - Gestionar contratos flexibles.
    - Integrar una pasarela para los pagos mensuales y el depósito de una fianza, asegurando que el dinero esté protegido.
    - Facilitar información sobre la vivienda para que los estudiantes sepan qué servicios están incluidos, mejorando así la transparencia y la convivencia.

<br><br>

<img src="./Fotos/Foto tablón de anuncios habitaciones.webp" alt="Foto tablón de anuncios" width="500">

<br>

Aquí podemos observar cómo se realizaría la búsqueda de habitaciones o viviendas antes de nuestro sistema de gestión.

<br>
    
<img src="./Fotos/Foto RoomieHub.jpg" alt="Foto RoomieHub" width="500">

<br>

Así quedaría después de implementar nuestro sistema de gestión.

## 2. Glosario de términos

- **Contrato flexible:** Acuerdo de arrendamiento adaptado al calendario académico de los estudiantes (por ejemplo, de 9 o 10 meses), a diferencia de los contratos inmobiliarios tradicionales de un año de duración.  
- **Avalista:** Tercera persona que asume subsidiariamente el pago de las deudas del inquilino.
- **Liquidación:** Cálculo y asignación de la parte proporcional de un gasto común (por ejemplo, un recibo de luz) que debe abonar un inquilino específico.
- **Match Inmobiliario:** Algoritmo o filtro del sistema que cruza las características de un estudiante (género, condición de Erasmus, etc.) con las preferencias y restricciones configuradas en una vivienda para determinar si son compatibles.

## 3. Visión general del sistema
- Dicho sistema web que diseñaremos permitirá que cada tipo de usuario acceda a las funcionalidades según su rol (adminisrador, propietario o inquilino), lo que asegurara la seguridad de los datos de cada uno de ellos, la eficiencia y la calidad de la información.
### 3.1. Requisitos generales

- El sistema RoomieHub debe proporcionar las siguientes funcionalidades principales para automatizar la gestión de alquileres y convivencia:

    - **Gestión de usuarios:** Permitir el registro, autenticación y edición de perfiles para los tres roles de la plataforma, incluyendo la validación de la condición de estudiante universitario para los inquilinos.

    - **Gestión de inmuebles:** Facilitar a los propietarios la creación, modificación y eliminación de anuncios de viviendas completas o habitaciones individuales, detallando precio, características, disponibilidad y normas básicas.

    - **Búsqueda y filtrado:** Proporcionar a los estudiantes un buscador de alojamientos con filtros por tipo de alquiler (habitación o piso completo), precio máximo y fechas de entrada/salida.

    - **Gestión de reservas y contratos:** Habilitar la solicitud de alquiler y la generación de contratos flexibles adaptados a los meses del curso académico, estableciendo la relación entre los inquilinos y el inmueble.

    - **Gestión económica:** Integrar el procesamiento del cobro de la fianza a prontopago para bloquear la reserva, así como el registro de los pagos mensuales de las rentas.

    - **Administración y control:** Disponer de un panel para que el Administrador supervise las operaciones económicas, valide perfiles y gestione posibles disputas o bloqueos de cuentas.

### 3.2. Usuarios del sistema
- En RoomieHub tendremos los siguientes tipos de usuarios disponibles:En primer lugar, los inquilinos (estudiantes), que cuentan con acceso básico para buscar y reservar habitaciones o viviendas completas, gestionar pagos seguros de fianzas y rentas, y definir sus hábitos de vida y estudio para encontrar compañeros compatibles.
- En segundo lugar, los propietarios, encargados de publicar y gestionar sus inmuebles con contratos adaptados al curso académico, tramitar las solicitudes de reserva y registrar los recibos de suministros a repartir.
- En tercer lugar, los avalistas, usuarios que actúan como garantía de pago vinculados al contrato del inquilino; asumen la obligación económica de responder ante las rentas o suministros pendientes en caso de que el estudiante no pueda afrontarlos. Su vinculación es opcional, ya que no todos los inquilinos requerirán esta figura para formalizar el alquiler.
- Por último, el administrador del sistema, responsable de validar la documentación e inmuebles para prevenir estafas, supervisar la custodia de las fianzas y resolver incidencias o disputas entre las partes.
- Cabe destacar que la condición de estudiante Erasmus no modifica las características ni permisos base del inquilino, salvo por una preferencia opcional: la posibilidad de solicitar ser agrupado prioritariamente, según disponibilidad y estilo de vida, con otros estudiantes de su mismo país de origen.

### 4.1. Catálogo de Requisitos Funcionales

#### R.G.01. Gestión de Usuario
* **R.F.01.01 [CREATE] Alta de Usuario:** Como usuario quiero registrar mis credenciales y datos básicos para acceder a la plataforma.  
  *Prueba de aceptación:* Validar formato de datos y rechazar email/DNI duplicados. Aplica `R.N.01`.
* **R.F.01.02 [READ] Consulta de Usuario:** Como usuario autenticado quiero ver mis datos de perfil para verificar mi información.  
  *Prueba de aceptación:* Mostrar datos personales ocultando contraseñas/datos sensibles. Aplica `R.N.02`.
* **R.F.01.03 [EDIT] Modificación de Usuario:** Como usuario quiero actualizar mi contacto o contraseña para mantener mis credenciales al día.  
  *Prueba de aceptación:* Exigir contraseña actual para cambios y revalidar nuevo email. Aplica `R.N.01`.
* **R.F.01.04 [DELETE] Baja de Usuario:** Como usuario quiero darme de baja para cesar mi cuenta en el sistema.  
  *Prueba de aceptación:* Aplicar baja lógica; bloquearla si existen contratos o pagos pendientes. Aplica `R.N.03`.

---

#### R.G.02. Gestión de Propietario
* **R.F.02.01 [CREATE] Alta de Propietario:** Como propietario quiero registrar mi IBAN y acreditación para habilitar cobros e inmuebles.  
  *Prueba de aceptación:* Validar formato bancario y dejar estado en `PENDIENTE`. Aplica `R.N.04`.
* **R.F.02.02 [READ] Consulta de Propietario:** Como propietario quiero consultar el estado de mi validación para saber si puedo operar.  
  *Prueba de aceptación:* Visualizar estado de acreditación e IBAN enmascarado. Aplica `R.N.05`.
* **R.F.02.03 [EDIT] Modificación de Propietario:** Como propietario quiero cambiar mi IBAN o teléfono para actualizar mis vías de cobro.  
  *Prueba de aceptación:* Revalidar titularidad ante cambios; impedir IBAN vacío con contratos vigentes. Aplica `R.N.04`.
* **R.F.02.04 [DELETE] Baja de Propietario:** Como propietario quiero revocar mi rol para dejar de ofertar inmuebles.  
  *Prueba de aceptación:* Bloquear baja si hay anuncios activos o contratos vigentes; desactivar inmuebles libres. Aplica `R.N.03`.

---

#### R.G.03. Gestión de Inquilino
* **R.F.03.01 [CREATE] Alta de Inquilino:** Como estudiante quiero registrar mi matrícula, hábitos y opción Erasmus para optar a alquileres.  
  *Prueba de aceptación:* Exigir matrícula; si `esErasmus = True`, requerir país y preferencia de compatibilidad. Aplica `R.N.06` y `R.N.07`.
* **R.F.03.02 [READ] Consulta de Inquilino:** Como inquilino quiero ver mis hábitos y validación académica para revisar mi perfil público.  
  *Prueba de aceptación:* Comprobar visibilidad de hábitos ante propietarios sin exponer documentos privados. Aplica `R.N.08`.
* **R.F.03.03 [EDIT] Modificación de Inquilino:** Como inquilino quiero modificar mis preferencias de convivencia o Erasmus para ajustar afinidades.  
  *Prueba de aceptación:* Actualizar criterios de convivencia; al desmarcar Erasmus, limpiar país y prioridad. Aplica `R.N.07`.
* **R.F.03.04 [DELETE] Baja de Inquilino:** Como inquilino quiero eliminar mi perfil para cesar la búsqueda de alojamiento.  
  *Prueba de aceptación:* Impedir baja si existe contrato activo; cancelar solicitudes de reserva pendientes. Aplica `R.N.03`.

---

#### R.G.04. Gestión de País
* **R.F.04.01 [CREATE] Alta de País:** Como administrador quiero registrar un país con código ISO para estandarizar el catálogo.  
  *Prueba de aceptación:* Validar código ISO único y campos no vacíos. Aplica `R.N.09`.
* **R.F.04.02 [READ] Consulta de Países:** Como usuario quiero listar países para indicar mi procedencia o nacionalidad.  
  *Prueba de aceptación:* Mostrar catálogo ordenado alfabéticamente con filtro por código o nombre. Aplica `R.N.09`.
* **R.F.04.03 [EDIT] Modificación de País:** Como administrador quiero corregir el nombre de un país para subsanar erratas.  
  *Prueba de aceptación:* Actualizar texto manteniendo invariable el código ISO y las relaciones existentes. Aplica `R.N.09`.
* **R.F.04.04 [DELETE] Baja de País:** Como administrador quiero eliminar un país obsoleto para depurar el catálogo.  
  *Prueba de aceptación:* Bloquear borrado si existen usuarios, avalistas o universidades asociadas. Aplica `R.N.10`.

---

#### R.G.05. Gestión de Universidad
* **R.F.05.01 [CREATE] Alta de Universidad:** Como administrador quiero añadir una universidad con nombre, siglas y ciudad para asociarla a estudiantes.  
  *Prueba de aceptación:* Validar nombre único por ciudad y existencia de la ciudad vinculada. Aplica `R.N.11`.
* **R.F.05.02 [READ] Consulta de Universidades:** Como estudiante quiero buscar universidades para vincular mi centro al perfil.  
  *Prueba de aceptación:* Permitir filtrado por ciudad o siglas con datos completos de adscripción. Aplica `R.N.11`.
* **R.F.05.03 [EDIT] Modificación de Universidad:** Como administrador quiero actualizar datos de una universidad para mantener exactitud.  
  *Prueba de aceptación:* Reflejar cambios en perfiles asociados verificando la validez de la nueva ciudad. Aplica `R.N.11`.
* **R.F.05.04 [DELETE] Baja de Universidad:** Como administrador quiero retirar una universidad para eliminar entidades inactivas.  
  *Prueba de aceptación:* Denegar eliminación si tiene inquilinos vinculados; permitir solo con cero referencias. Aplica `R.N.10`.

---

#### R.G.06. Gestión de Avalista
* **R.F.06.01 [CREATE] Alta de Avalista:** Como inquilino quiero vincular un avalista para satisfacer requisitos de solvencia.  
  *Prueba de aceptación:* Comprobar DNI distinto al inquilino y dejarlo en `PENDIENTE_CONFIRMACION`. Aplica `R.N.12`.
* **R.F.06.02 [READ] Consulta de Avalista:** Como parte contractual quiero consultar datos del avalista para constatar el respaldo económico.  
  *Prueba de aceptación:* Restringir acceso solo a propietarios vinculados y mostrar estado de ratificación. Aplica `R.N.12`.
* **R.F.06.03 [EDIT] Modificación de Avalista:** Como avalista quiero actualizar mis datos de contacto para recibir notificaciones y cobros.  
  *Prueba de aceptación:* Validar nuevos datos; bloquear cambio de documento de identidad en contratos vigentes. Aplica `R.N.01`.
* **R.F.06.04 [DELETE] Baja de Avalista:** Como inquilino quiero desvincular un avalista para sustituirlo o retirarlo tras finalizar contrato.  
  *Prueba de aceptación:* Impedir baja si respalda un contrato en vigor que exige aval; permitir solo si hay sustituto o contrato extinto. Aplica `R.N.13`.

---

#### R.G.07. Gestión de Contrato
* **R.F.07.01 [CREATE] Alta de Contrato:** Como propietario quiero registrar un acuerdo de alquiler para formalizar la estancia.  
  *Prueba de aceptación:* Validar `fechaFin > fechaInicio` y exigir firma del avalista si es requerido antes de pasar a `ACTIVO`. Aplica `R.N.14` y `R.N.15`.
* **R.F.07.02 [READ] Consulta de Contrato:** Como parte involucrada quiero revisar cláusulas, importes y estado del contrato para verificar condiciones.  
  *Prueba de aceptación:* Limitar lectura a inquilino, propietario y avalista asignados. Aplica `R.N.16`.
* **R.F.07.03 [EDIT] Modificación de Contrato:** Como propietario quiero prorrogar fechas o ajustar condiciones con acuerdo de partes.  
  *Prueba de aceptación:* Verificar ausencia de solapamiento en prórrogas y requerir aceptación de inquilino/aval. Aplica `R.N.14`.
* **R.F.07.04 [DELETE] Rescisión de Contrato:** Como propietario o administrador quiero cancelar un contrato para registrar su extinción formal.  
  *Prueba de aceptación:* Cambiar estado a `RESCINDIDO` manteniendo registro histórico sin borrado físico. Aplica `R.N.17`.

---

#### R.G.08. Gestión de Habitación
* **R.F.08.01 [CREATE] Alta de Habitación:** Como propietario quiero registrar una habitación para ofrecerla individualmente.  
  *Prueba de aceptación:* Validar identificador único dentro de la vivienda y precio mensual $> 0$. Aplica `R.N.18`.
* **R.F.08.02 [READ] Consulta de Habitaciones:** Como inquilino quiero ver detalles, fotos y disponibilidad de habitaciones para elegir estancia.  
  *Prueba de aceptación:* Mostrar estado de ocupación según calendario y características detalladas. Aplica `R.N.18`.
* **R.F.08.03 [EDIT] Modificación de Habitación:** Como propietario quiero cambiar equipamiento o precio para actualizar la oferta.  
  *Prueba de aceptación:* Aplicar nuevo precio solo a contrataciones futuras sin alterar contratos vigentes. Aplica `R.N.19`.
* **R.F.08.04 [DELETE] Baja de Habitación:** Como propietario quiero eliminar una habitación para retirarla de comercialización.  
  *Prueba de aceptación:* Denegar baja si tiene contratos activos o reservas; actualizar cómputo de plazas. Aplica `R.N.20`.

---

#### R.G.09. Gestión de Vivienda
* **R.F.09.01 [CREATE] Alta de Vivienda:** Como propietario quiero registrar un inmueble completo para su oferta integral o compartida.  
  *Prueba de aceptación:* Validar aforo $\ge 1$ y dirección vinculada a ciudad existente. Aplica `R.N.21`.
* **R.F.09.02 [READ] Consulta de Viviendas:** Como inquilino quiero buscar viviendas por filtros de ubicación, aforo y normas para hallar opciones.  
  *Prueba de aceptación:* Mostrar resultados coincidentes solo para inmuebles con titularidad validada. Aplica `R.N.05`.
* **R.F.09.03 [EDIT] Modificación de Vivienda:** Como propietario quiero ajustar normas o descripción para mantener actualizado el anuncio.  
  *Prueba de aceptación:* Impedir fijar un aforo inferior al número de inquilinos actuales. Aplica `R.N.21`.
* **R.F.09.04 [DELETE] Baja de Vivienda:** Como propietario quiero retirar un inmueble para cesar su arrendamiento.  
  *Prueba de aceptación:* Bloquear si cuenta con contratos o habitaciones vigentes; ejecutar baja lógica. Aplica `R.N.20`.

---

#### R.G.10. Gestión de Ciudad
* **R.F.10.01 [CREATE] Alta de Ciudad:** Como administrador quiero añadir una ciudad y código postal para ampliar áreas operativas.  
  *Prueba de aceptación:* Validar formato de CP según país y unicidad de la tupla (nombre, CP). Aplica `R.N.22`.
* **R.F.10.02 [READ] Consulta de Ciudades:** Como usuario quiero buscar ciudades para ubicar inmuebles o universidades.  
  *Prueba de aceptación:* Permitir búsqueda predictiva y desplegar listado vinculado a país. Aplica `R.N.09`.
* **R.F.10.03 [EDIT] Modificación de Ciudad:** Como administrador quiero corregir nombre o formato postal para subsanar errores.  
  *Prueba de aceptación:* Preservar relaciones con viviendas y universidades tras la actualización. Aplica `R.N.22`.
* **R.F.10.04 [DELETE] Baja de Ciudad:** Como administrador quiero eliminar una ciudad registrada por error para depurar datos.  
  *Prueba de aceptación:* Bloquear borrado si existen viviendas o universidades vinculadas. Aplica `R.N.10`.

---

#### R.G.11. Gestión de Gasto
* **R.F.11.01 [CREATE] Alta de Gasto:** Como propietario quiero registrar facturas de suministros para repercutirlas a los inquilinos.  
  *Prueba de aceptación:* Validar importe $> 0$ y vigencia de contratos en la vivienda durante el periodo. Aplica `R.N.23`.
* **R.F.11.02 [READ] Consulta de Gastos:** Como usuario vinculado quiero revisar


#### 4.1.2. Reglas de negocio

##### R.N.01. Lógica temporal del contrato

La fecha de inicio de un contrato debe ser estrictamente anterior a la fecha de fin.

#### R.N.02. Solapamiento temporal

Una misma habitación no puede tener más de un contrato en estado ACTIVO o RESERVADO para un mismo rango de fechas.

#### R.N.03. Aforo físico exacto

La capacidadTotal (aforo) de una Vivienda debe ser siempre exactamente igual a la suma de las plazas de todas las habitaciones que la componen.

#### R.N.04. Roles mutuamente excluyentes

Un usuario no puede ser Propietario e Inquilino simultáneamente en la plataforma.

#### R.N.05. Mayoría de edad legal

Todo inquilino debe ser mayor de 18 años en el momento del registro del sistema.

#### R.N.06. Filtro ERASMUS

El sistema bloqueará la activación de un contrato si el Inquilino es Erasmus y la Vivienda tiene explícitamente denegada la admisión de estudiantes de intercambio.

#### R.N.07. Filtro género

No se podrá activar un contrato si el género del Inquilino es incompatible con la restricción de convivencia (generoAdmitido) configurada en la Vivienda.

#### R.N.08. Coherencia de origen Erasmus

Si un Inquilino indica marca que es estudiando Erasmus, su Pais de origen asociado no puede ser el país local donde opera la plataforma (ej: España).

#### R.N.09. Avalista obligatorio

Si un Inquilino indica que requiere aval (sin ingresos), el sistema exige registrar y vincular la figura de un Avalista para activar el contrato.

#### R.N.10. Preveción de Auto-Aval

El DNI del Avalista no puede coincidir bajo ninguna circunstancia, con el DNI del Inquilino titular del contrato.

#### R.N.11. Solvencia mínima aval

Los ingresos mensuales declarados por el Avalista deben ser, como mínimo, el triple del precio base mensual de la habitación alquilada.

#### R.N.12. Límite de contratos por Avalista

Un mismo Avalista no puede respaldar simultáneamente a más de tres contratos activos en la plataforma.

#### R.N.13. Límites legales de fianza

El importe de la fianza exigida en un contrato no puede ser inferior a una mensualidad ni superior a tres.

#### R.N.14. Protección de Fianza ante daños

El importe de un gasto categorizado como "REPARACIÓN" asignado individualmente a un inquilino no podrá superar nunca el saldo de la fianza depositada.

#### R.N.15. Importes de gasto positivo

El importe total de cualquier gasto registrado en el sistema debe ser estrictamente mayor que cero.

#### R.N.16. Hermetistmo Matemático en prorrateos

La suma de los porcentajes asignados en todas las liquidaciones (deudas individuales) derivadas de un mismo recibo general debe sumar matemáticamente y de forma exacta el 100%.

#### R.N.17. Lógica de fracción

El porcentaje asignado a un inquilino en un recibo compartido debe estar siempre comprendido entre 0 y 100.

#### R.N.18. Distribuición temporal de facturas

Solo se generarán liquidaciones de suministros a aquellos inquilinos cuyo contrato vigente abarque la fecha de emisión del gasto facturado.

#### R.N.19. Bloqueo de finalización por morosidad

El sistema no permitirá cambiar el estado de un contrato a "FINALIZADO" si el inquilino posee alguna liquidación de gasto pendiente de pago.

#### R.N.20. Cronología de Gastos

La fecha de vencimiento y/o fecha de pago de un Gasto no puede ser nunca anterior a su fecha de emisión.

#### R.N.21. Precios estrictamente positivos

El precioBaseMensual de cualquier Habitacion y el precioAlquilerCompleto de la Vivienda deben ser valores numéricos estrictamente mayores que cero.

#### R.N.22. Coherencia espacial para parejas

Si un contrato se formaliza bajo la modalidad de pareja, la Habitación vinculada debe tener obligatoriamente el atributo plazas con valor igual a 2.

#### R.N.23. Requisito aval/nomina
Un inquilino puede tener una nomina, en el caso de no tenerla se requerira aval.

#### R.N.24. Aval obligatorio
El propietario puede indicar que una vivienda requiere aval obligatorio (independientemente de la nomina).

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias

Hemos llevado a cabo búsqueda de información en los siguientes sitios web:

https://www.laopiniondezamora.es/zamora/2026/08/03/carrera-estudiantes-encontrar-alojamiento-zamora-133040075.html

