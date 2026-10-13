# Sistema de Gestión de Alquiler de Habitaciones y Convivencia para Estudiantes (RoomieHub)

## Miembros del grupo L1-Grupo 4

1. Nolasco Calderón, Ángel
1. Al Khyat, Khaled
1. De la Fuente Hernández, Gonzalo
1. Galocha López, Adrián

## 1. Introducción al problema

- El proyecto "RoomieHub" consiste en el desarrollo de un sistema de información diseñado específicamente para la gestión de alquiler de habitaciones, viviendas completas y la organización de la convivencia para estudiantes. La plataforma busca actuar como intermediario y facilitador entre personas que disponen de inmuebles y estudiantes que necesitan alojamiento durante su curso académico.
- En el sistema tenemos tres tipos de usurarios:
    - Inquilino (Estudiantes): Buscan alojamiento. Tienen la flexibilidad de alquilar una habitación en un piso compartido o, si vienen en grupo, una vivienda completa.
    - Propietario: Dueños o gestores de sus inmuebles que publican sus viviendas o habitaciones disponibles.
    - Administrador del sistema: Personal encargado de mantener la plataforma.
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

- Términos específicos del dominio del problema, ordenados alfabéticamente. Se valorará la presencia de información multimedia.

-**Contrato flexible:** Acuerdo de arrendamiento adaptado al calendario académico de los estudiantes (por ejemplo, de 9 o 10 meses), a diferencia de los contratos inmobiliarios tradicionales de un año de duración.   

## 3. Visión general del sistema
- Dicho sistema web que diseñaremos permitirá que cada tipo de usuario acceda a las funcionalidades según su rol (adminisrador, propietario o inquilino), lo que asegurara la seguridad de los datos de cada uno de ellos, la eficiencia y la calidad de la información.
### 3.1. Requisitos generales

### 3.2. Usuarios del sistema

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

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


