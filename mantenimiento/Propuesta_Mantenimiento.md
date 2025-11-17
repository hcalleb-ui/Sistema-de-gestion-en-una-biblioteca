# FACULTAD DE CIENCIAS E INGENIERÍA  
## CARRERA DE INGENIERÍA DE SOFTWARE  

# **Trabajo Práctico Experimental N.3:  
Informe Técnico – Sistema de Gestión de Biblioteca**

### **Grupo:**  
N.-4

### **Autores:**  
Henry Fernando Calle Bonilla  
Jesus Alejandro Azú Estrada  
Jhon Jairo Gualpa Gonzalez  
Jared Ismael Semper Ordóñez  
Pablo Cesar Moreno Llaguno

### **Asignatura:**  
Introducción a la Ingeniería de Software

### **Docente:**  
Ing. Guevara Serrano Jorge Dumar

### **Fecha de entrega:**  
Viernes, 31 de octubre de 2025, 23:59

### **Período:**  
Agosto - Diciembre 2025

### **Milagro - Ecuador**

---

# 1. Descripción del sistema

El Sistema de Gestión de Biblioteca es una aplicación informática desarrollada con el propósito de optimizar la administración de los recursos bibliográficos en una institución. Su función principal es registrar los libros disponibles, gestionar los préstamos a los usuarios y controlar las devoluciones en tiempo y forma. El sistema busca digitalizar los procesos tradicionales de préstamo, sustituyendo los registros manuales por una base de datos estructurada y un entorno de interfaz amigable.

El sistema se basa en una arquitectura cliente-servidor con almacenamiento local, e incluye tres módulos principales:

### **Módulo de Libros**
Encargado de registrar nuevos ejemplares, títulos, autores, categorías y su estado de disponibilidad.

### **Módulo de Préstamos**
Permite asignar libros a usuarios y llevar el control de fechas de entrega y devolución.

### **Módulo de Reportes**
Genera listados de préstamos activos, devoluciones pendientes y estadísticas de uso.

El sistema está orientado a bibliotecas pequeñas o medianas, ubicadas principalmente en instituciones educativas o centros culturales. Los administradores o bibliotecarios serán los usuarios finales, encargados de gestionar los préstamos y actualizar los registros.

A futuro, se contempla implementar acceso en línea para consulta de disponibilidad y generación de reservas.

---

# 2. Análisis del problema

Durante el proceso de revisión del sistema se identificaron varias limitaciones que afectan su eficiencia:

### **1. Ausencia de control de disponibilidad de libros**
No se valida si un libro está ya prestado al intentar asignarlo nuevamente, lo que genera duplicaciones y pérdida de control del inventario.

### **2. Falta de registro de usuarios**
El sistema no identifica prestatarios, impidiendo conocer quién tiene un libro, el historial de uso o la trazabilidad del material.

### **3. Reportes limitados**
No existen reportes avanzados que permitan identificar préstamos vencidos o estadísticas que apoyen decisiones administrativas.

### **Consecuencias**
Las deficiencias mencionadas generan:
- Uso ineficiente del sistema  
- Disminución de la calidad del servicio  
- Confusión en la disponibilidad de ejemplares  
- Posibles pérdidas de material  

Por lo tanto, es prioritario aplicar procesos de mantenimiento correctivo y perfectivo.

---

# 3. Tipos de mantenimiento aplicables

Según Sommerville (2011) y Pressman (2014), los mantenimientos adecuados son:

---

## **Mantenimiento Correctivo**
Corrige defectos detectados durante el uso del sistema.

### **Justificación teórica**
Busca restablecer el funcionamiento normal, asegurando integridad de datos.

### **Justificación técnica**
Se necesita corregir la lógica que permita validar disponibilidad del libro, evitando préstamos duplicados.

---

## **Mantenimiento Perfectivo**
Incorpora mejoras que aumentan funcionalidad y rendimiento.

### **Justificación teórica**
Amplía capacidades del software sin modificar su estructura principal.

### **Justificación técnica**
Añadir un módulo de usuarios y control de disponibilidad mejora trazabilidad y eficiencia.

---

# 4. Justificación

Los mantenimientos propuestos optimizan el control de recursos, mejoran calidad de datos y reducen errores humanos.  
A nivel organizativo, permiten transparencia total en la gestión de préstamos.

Desde un enfoque pedagógico, aplicar estos principios fortalece competencias profesionales y conecta la teoría de ingeniería de software con problemas reales.

---

# 5. Cambio funcional propuesto

## **Nombre del cambio:**  
Módulo de control de usuarios y disponibilidad de libros.

## **Descripción:**  
Se propone desarrollar un módulo que permita gestionar información de usuarios y verifique la disponibilidad de libros antes de autorizar un préstamo.

### **Este módulo incluirá:**  
- Registro, modificación y eliminación de usuarios  
- Asociación de usuarios a préstamos  
- Validación automática del estado del libro  

---

## **Mejoras que aporta**
- Mayor trazabilidad de préstamos  
- Evita registros duplicados  
- Datos más confiables  
- Reportes más completos  
- Mejor experiencia del usuario  

---

## **Cómo se implementaría**

1. Crear tabla **Usuarios** en la base de datos  
2. Modificar tabla **Libros** agregando el campo **Estado** (Disponible/Prestado)  
3. Relacionar **Usuarios ↔ Préstamos** mediante identificador único  
4. Añadir formularios GUI de gestión  
5. Implementar validaciones automáticas antes de confirmar un préstamo  

---

## **Impacto esperado**

| Criterio               | Antes del cambio | Después del cambio |
|-----------------------|------------------|--------------------|
| Control de disponibilidad | No | Sí |
| Registro de usuarios | No | Sí |
| Confiabilidad de datos | Media | Alta |
| Trazabilidad | Limitada | Completa |
| Mantenibilidad | Media | Alta |
| Escalabilidad | Baja | Alta |

---

# 6. Implementación técnica y evaluación del impacto

### **Lenguaje sugerido:**  
Python, Java o C#

### **Base de datos:**  
MySQL o SQLite

### **Arquitectura:**  
Cliente-servidor local con posible evolución a entorno web

### **Interfaz:**  
Formularios gráficos (GUI)

---

# 7. Reflexión final

El mantenimiento del software es una etapa esencial del ciclo de vida.  
Este análisis permitió evidenciar cómo la ingeniería de software asegura la calidad y sostenibilidad del sistema.

El cambio propuesto corrige errores y amplía la utilidad del sistema, integrando buenas prácticas como documentación adecuada y normalización de bases de datos.

La mejora continua es indispensable, incluso para sistemas pequeños, y garantiza evolución y estabilidad a largo plazo.
