# Sistema de Gestión de Alquiler de Habitaciones y Convivencia para Estudiantes (RoomieHub)

## Miembros del grupo L1-DF-AM-4

1. Nolasco Calderón, Ángel
1. Al Khyat, Khaled
1. De la Fuente Hernández, Gonzalo
1. Galocha López, Adrián

## 1. Introducción al problema

- El proyecto "RoomieHub" consiste en el desarrollo de un sistema de información diseñado específicamente para la gestión de alquiler de habitaciones, viviendas completas y la organización de la convivencia para estudiantes. La plataforma busca actuar como intermediario y facilitador entre personas que disponen de inmuebles y estudiantes que necesitan alojamiento durante su curso académico.
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

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### R.G.01. Gestión de Usuario

El sistema debe permitir registrar, modificar, consultar y eliminar la información básica y credenciales de acceso de cualquier usuario de la plataforma, actuando como base común para los distintos roles.

#### R.G.02. Gestión de Propietario

El sistema debe permitir gestionar la información específica de los usuarios con rol de propietario, incluyendo sus datos de contacto adicionales, cuenta bancaria para ingresos y el estado de validación de su identidad.

#### R.G.03. Gestión de Inquilino

El sistema debe permitir gestionar la información específica de los estudiantes (inquilinos), incluyendo su perfil personal, preferencias de convivencia, estado de solvencia y la verificación de su matrícula académica.

#### R.G.04. Gestión de País

El sistema debe permitir mantener un catálogo con la información de los distintos países (nombre y código) para identificar la nacionalidad u origen de los estudiantes y avalistas.

#### R.G.05. Gestión de Universidad

El sistema debe permitir registrar y consultar la información de las instituciones académicas (nombre, siglas y ubicación) a las que pertenecen los inquilinos.

#### R.G.06. Gestión de Avalista

El sistema debe permitir el registro, modificación y consulta de los datos personales y de contacto de los avalistas, así como la información necesaria para respaldar financieramente a un inquilino.

#### R.G.07. Gestión de Contrato

El sistema debe permitir registrar, consultar, actualizar y cancelar la información relativa a los acuerdos de alquiler, almacenando las fechas de inicio y fin, la fianza depositada, el estado actual y las partes vinculadas.

#### R.G.08. Gestión de Habitación

El sistema debe permitir gestionar la información detallada de cada habitación individual dentro de un inmueble, incluyendo su identificador, precio mensual, disponibilidad, dimensiones y características.

#### R.G.09. Gestión de Vivienda

El sistema debe permitir registrar y administrar los datos generales de los inmuebles completos, tales como su dirección postal, aforo máximo, normas de convivencia y las preferencias sobre el perfil de los inquilinos.

#### R.G.10. Gestión de Ciudad

El sistema debe permitir mantener un catálogo de ciudades (nombre y código postal) para estructurar correctamente la ubicación geográfica de las viviendas y las universidades.

#### R.G.11. Gestión de Gasto

El sistema debe permitir registrar, consultar y modificar la información de las facturas o recibos comunes de una vivienda (tipo de suministro como luz o agua, importe total, fecha de emisión y estado).

#### R.G.12. Gestión de Liquidación

El sistema debe permitir generar y gestionar la información de la deuda individual asignada a un inquilino, registrando el importe exacto o porcentaje que le corresponde pagar derivado de un gasto común, así como su estado de pago.

### 3.2. Usuarios del sistema
- Inquilinos (estudiantes), que cuentan con acceso básico para buscar y reservar habitaciones o viviendas completas, gestionar pagos seguros de fianzas y rentas, y definir sus hábitos de vida y estudio para encontrar compañeros compatibles.
- Propietarios, encargados de publicar y gestionar sus inmuebles con contratos adaptados al curso académico, tramitar las solicitudes de reserva y registrar los recibos de suministros a repartir.
- Avalistas, usuarios que actúan como garantía de pago vinculados al contrato del inquilino; asumen la obligación económica de responder ante las rentas o suministros pendientes en caso de que el estudiante no pueda afrontarlos. Su vinculación es opcional, ya que no todos los inquilinos requerirán esta figura para formalizar el alquiler.
- Administrador, responsable de validar la documentación e inmuebles para prevenir estafas, supervisar la custodia de las fianzas y resolver incidencias o disputas entre las partes.

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

#### R.N.01. Solapamiento temporal

Una misma habitación no puede tener más de un contrato en estado ACTIVO o RESERVADO para un mismo rango de fechas.

#### R.N.02. Aforo físico exacto

La capacidadTotal (aforo) de una Vivienda debe ser siempre exactamente igual a la suma de las plazas de todas las habitaciones que la componen.

#### R.N.03. Filtro ERASMUS y género

El sistema admite ERASMUS. El sistema admite HOMBRE. El sistema admite MUJER.

#### R.N.04. Avalista obligatorio

El sistema impide crear el contrato si la suma de los ingresos y los avales no supera lo establecido en el contrato.

#### R.N.05. Preveción de Auto-Aval

El DNI del Avalista no puede coincidir bajo ninguna circunstancia, con el DNI del Inquilino titular del contrato.

#### R.N.06. Solvencia mínima aval

Los ingresos mensuales declarados por el Avalista deben ser, como mínimo, el triple del precio base mensual de la habitación alquilada.

#### R.N.07. Límite de contratos por Avalista

Un mismo Avalista no puede respaldar simultáneamente a más de tres contratos activos en la plataforma.

#### R.N.08. Límites legales de fianza

El importe de la fianza exigida en un contrato no puede ser inferior a una mensualidad ni superior a tres.

#### R.N.9. Hermetistmo Matemático en prorrateos

La suma de los porcentajes asignados en todas las liquidaciones (deudas individuales) derivadas de un mismo recibo general debe sumar matemáticamente y de forma exacta el 100%.

#### R.N.10. Bloqueo de finalización por morosidad

El sistema no permitirá cambiar el estado de un contrato a "FINALIZADO" si el inquilino posee alguna liquidación de gasto pendiente de pago.

#### R.N.11. Cronología de Gastos

La fecha de vencimiento y/o fecha de pago de un Gasto no puede ser nunca anterior a su fecha de emisión.

#### R.N.12. Coherencia espacial para parejas

Si un contrato se formaliza bajo la modalidad de pareja, la Habitación vinculada debe tener obligatoriamente el atributo plazas con valor igual a 2.

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

