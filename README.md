# Ejercicio — Base de Datos de Gestión Académica Universitaria



Proyecto enfocado en la modelación Entidad-Relación (DER / MER) e implementación de base de datos relacional para un sistema de gestión universitaria, administrando carreras, planes de estudio, asignaturas, docentes, alumnos, comisiones, inscripciones y evaluaciones parciales.

---

## Descripción

El sistema modela una estructura de datos relacional para la administración integral de la actividad académica en un entorno universitario. Permite organizar las carreras universitarias con sus respectivos planes de estudio estructurados por ciclos lectivos, gestionar el plan de correlatividades entre asignaturas, administrar las comisiones de cursado a cargo de docentes, e inscribir alumnos registrando sus condiciones de cursado y las notas obtenidas en los exámenes parciales.

---

## Funcionalidades e Implementación

### Entidades y Atributos

* Carrera:


* id_Cod_Nombre: Clave identificadora única de la carrera.


* Nombre: Denominación formal de la carrera universitaria.




* Plan de Estudio:


* id_Plan de Estudio: Clave primaria identificadora del plan académico.


* Fecha inicio: Fecha de vigencia inicial o aprobación del plan.


* Fecha final: Fecha de término de vigencia del plan.




* Ciclo lectivo:


* id_ciclo lectivo: Clave primaria identificadora del ciclo lectivo.


* Año: Año académico correspondiente.


* Periodo: Período de cursado (ej. 1° cuatrimestre, 2° cuatrimestre, anual).




* Asignatura:


* id_Cod_Asignatura: Clave primaria identificadora de la materia.


* Nombre: Nombre de la asignatura.


* Carga de horario: Carga horaria total asignada a la materia.


* Año curricular: Año del plan de estudios en el que se dicta la asignatura.




* Correlatividades:


* id_Cod_Asignatura: Clave foránea referenciando a la asignatura principal.


* id_Cod_Correlativa: Clave foránea referenciando a la asignatura correlativa requerida.




* Profesor:


* id_profesor: Clave primaria identificadora del docente.


* Nombre: Nombre del profesor.


* Apellido: Apellido del profesor.


* DNI: Documento Nacional de Identidad.




* Comisión:


* id_comision: Clave primaria identificadora de la comisión de cursado.


* nombre_comision: Código o nombre asignado a la comisión (ej. Comisión A, Grupo 1).


* cupo_maximo: Límite máximo de alumnos aceptados.




* Alumno:


* id_Alumno: Clave primaria identificadora del estudiante.


* Nombre: Nombre del estudiante.


* Apellido: Apellido del estudiante.


* DNI: Documento de identidad del estudiante.




* Inscripción:


* id_Inscripción: Clave primaria identificadora del trámite o registro de inscripción.


* Fecha de inscripción: Fecha en que se concreta la inscripción.


* Condición: Estado del alumno en la materia (ej. regular, libre, promocionado).




* Evaluación Parcial:


* id_Evaluacion: Clave primaria identificadora de la instancia evaluativa.


* numero de parcial: Instancia del examen (ej. Parcial 1, Parcial 2, Recuperatorio).


* Nota: Calificación numérica u homologada obtenida.


* Fecha: Fecha de sustanciación del examen.





---

## Relaciones del Modelo

1. Carrera ↔ Plan de Estudio (Relación 1:1):


* Una carrera se vincula directamente a la definición de su respectivo plan de estudios activo.




2. Plan de Estudio ↔ Inscripción (Relación 1:N):


* Un plan de estudios agrupa múltiples inscripciones realizadas por alumnos a lo largo de las cohortes.




3. Ciclo lectivo ↔ Plan de Estudio / Asignatura (Relaciones 1:N):


* Un ciclo lectivo organiza de manera temporal la oferta académica de los planes de estudio y las asignaturas dictadas.




4. Asignatura ↔ Correlatividades (Relaciones 1:N / M:N):


* Las asignaturas establecen dependencias académicas entre sí, definiendo requisitos previas mediante la entidad de correlatividades.




5. Profesor ↔ Comisión (Relación 1:N):


* Un profesor o docente puede tener a su cargo el dictado de múltiples comisiones.




6. Comisión ↔ Inscripción / Evaluación Parcial (Relaciones N:1 / N:M):


* La comisión canaliza a los estudiantes inscriptos en una cursada concreta e intermedia en la administración de sus evaluaciones parciales.




7. Alumno ↔ Inscripción (Relación 1:N):


* Un alumno puede generar múltiples inscripciones a lo largo de su carrera universitaria.




8. Profesor ↔ Inscripción (Relación 1:N):


* El docente queda asociado formalmente a las inscripciones correspondientes a las comisiones bajo su tutoría o cátedra.
