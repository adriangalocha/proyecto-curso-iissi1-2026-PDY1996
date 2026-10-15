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

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Match Inmobiliario

Como Inquilino (Estudiante),
quiero consultar un listado de viviendas y habitaciones disponibles filtradas automáticamente por su compatibilidad con mi perfil (admisión de Erasmus, parejas y restricciones de género),
para encontrar rápidamente un alojamiento en el que sea aceptado y evitar problemas de convivencia.

**Pruebas de aceptación:**

- Comprobar que el sistema oculta de los resultados las viviendas donde las preferencias del propietario no coincidan con el perfil del estudiante.
- Comprobar que se muestran los resultados ordenados o agrupados según disponibilidad.
- Se debe aplicar la regla de negocio R.N.02 (Filtro de Convivencia) al intentar acceder a la vivienda.

#### R.F.02. Estado de solvencia de la fianza y liquidaciones pendientes
Como Administrador de la plataforma
quiero consultar el estado de solvencia de la fianza y obtener un listado de liquidaciones pendientes (deudas) agrupadas por inquilino
para llevar un control estricto de los impagos y asegurar que las fianzas cubren las posibles deudas.

**Pruebas de aceptación:**

- Verificar que el sistema muestra el importe total depositado como fianza por cada inquilino.
- Verificar que aparece el desglose de todas las liquidaciones en estado "Pendiente de pago" asociadas a ese inquilino.
- Se debe aplicar la regla de negocio R.N.03 (Límite de Reparaciones contra Fianza) para alertar si la deuda por reparaciones supera el saldo mostrado en esta consulta.

#### R.F.03. Auditoría del reparto de gastos comunes
Como Administrador de la plataforma
quiero consultar el reparto matemático exacto de gastos comunes (suministros) entre los contratos activos
para auditar la facturación mensual y garantizar que los cobros a los inquilinos son correctos y justos.

**Pruebas de aceptación:**

- Comprobar que el sistema identifica correctamente qué contratos estaban en estado "ACTIVO" durante el mes del recibo consultado.
- Verificar que se muestra el importe total del recibo y el porcentaje o cuota asignada a cada inquilino de la vivienda.
- Se debe aplicar la regla de negocio R.N.05 (Hermetismo Matemático) para garantizar que la vista de auditoría suma exactamente el 100% de los porcentajes repartidos.

#### R.F.04. Consulta de ocupación y disponibilidad
Como Propietario,
quiero visualizar un listado de mis viviendas con el estado actual de cada una de sus habitaciones (Ocupada, Reservada o Disponible),
para saber qué espacios tengo vacíos y poder ofertarlos a nuevos estudiantes.

**Pruebas de aceptación:**
- Comprobar que el sistema cruza correctamente las habitaciones con los contratos vigentes en la fecha actual.
- Verificar que se muestra la capacidad total de la vivienda frente a las plazas actualmente ocupadas.
- Se debe aplicar la regla de negocio R.N.02 (Solapamiento temporal) para garantizar que el cálculo de disponibilidad es exacto y no hay habitaciones con doble contrato activo.

#### R.F.05. Auditoría de contratos avalados
Como Propietario,
quiero consultar un listado de los contratos activos vinculados a inquilinos sin ingresos propios, mostrando la información de su Avalista correspondiente,
para auditar la seguridad financiera de los alquileres y saber a quién reclamar en caso de impago.

**Pruebas de aceptación:**
- Comprobar que el listado filtra y muestra únicamente a los inquilinos que tienen el atributo requiereAval en verdadero.
- Verificar que aparece el nombre, DNI y contacto del Avalista asociado al contrato de dicho estudiante.
- Se debe aplicar la regla de negocio R.N.09 (Avalista Obligatorio) para asegurar que la información listada es válida y legal.

#### 4.1.1. Requisitos de información

##### R.I.01. Almacenamiento del perfil del Inquilino y su Avalista
Como Administrador de la plataforma,
quiero que el sistema almacene los datos personales detallados de los estudiantes (incluyendo género y si es Erasmus) y los vincule a un Avalista en caso de insolvencia,
para garantizar la seguridad financiera de los alquileres y poder aplicar los filtros de convivencia.

**Pruebas de aceptación:**
- Verificar que la base de datos persiste correctamente los atributos obligatorios del Inquilino esErasmus, genero, requiereAval y su clave foránea al catálogo Pais.
- Comprobar la restricción de unicidad (UNIQUE) para el DNI del Inquilino y el DNI del Avalista.
- Verificar que, si se elimina un Inquilino, no se elimine el Avalista si este sigue respaldando a otros estudiantes (integridad referencial).

##### R.I.02. Catálogo de Viviendas y Restricciones de Convivencia
Como Propietario,
quiero que el sistema guarde la información estructural de mis inmuebles (aforo legal, habitaciones) junto con mis preferencias de admisión (género, Erasmus, parejas),
para que la plataforma pueda filtrar automáticamente a los candidatos incompatibles.

**Pruebas de aceptación:**
- Comprobar que se almacenan correctamente los atributos de control de la entidad Vivienda admiteErasmus, admiteParejas, y el enumerado generoAdmitido.
- Verificar que la dirección de la vivienda está protegida por una restricción de unicidad para evitar duplicados.
- Asegurar la correcta vinculación (Clave Foránea) de la vivienda con el catálogo normalizado de Ciudad (3FN).

##### R.I.03. Historial de Contratos Flexibles y Fianzas
Como Administrador de la plataforma,
quiero que el sistema registre un historial trazable de los contratos de arrendamiento, incluyendo fechas exactas, el importe de la fianza y el estado actual,
para mantener un registro legal inmutable de la ocupación de las habitaciones a lo largo de los cursos académicos.

**Pruebas de aceptación:**
- Comprobar que el contrato persiste los atributos obligatorios: fechaInicio, fechaFin, importeFianza y el estado (ACTIVO, RESERVADO, FINALIZADO).
- Verificar que el diseño soporta de manera eficiente las consultas por rango de fechas para evaluar el solapamiento.
- Asegurar que un contrato queda vinculado correctamente a la Habitacion concreta y al Inquilino titular.

##### R.I.04. Registro Unificado de Gastos y Prorrateos
Como Administrador de la plataforma,
quiero almacenar los recibos y facturas en un registro único categorizado, junto con el desglose exacto (liquidaciones) de lo que debe pagar cada inquilino,
para mantener las cuentas transparentes, auditar los pagos y proteger las fianzas ante reparaciones.

**Pruebas de aceptación:**
- Verificar que la entidad unificada Gasto guarda correctamente el atributo categoria (SUMINISTRO o REPARACION) y su importeTotal.
- Comprobar que la entidad intermedia LiquidacionGasto persiste el porcentajeAsignado, el importeProrrateado y su estado (PENDIENTE, PAGADO).
- Asegurar que la estructura de datos permite recuperar fácilmente el sumatorio de las liquidaciones pendientes de un contrato para calcular posibles bloqueos de morosidad.


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

