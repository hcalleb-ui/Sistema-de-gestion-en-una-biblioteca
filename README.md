# 📚 Sistema de Gestión de Biblioteca  


---

## 📝 Descripción del caso
El Sistema de Gestión de Biblioteca es una aplicación informática orientada a bibliotecas pequeñas o medianas.  
Su propósito es **optimizar la administración de recursos bibliográficos**, digitalizando procesos de préstamo y devolución mediante una base de datos estructurada y una interfaz amigable.  

**Problemas detectados:**
- No existe control de disponibilidad de libros (se permiten préstamos duplicados).  
- No hay registro de usuarios ni trazabilidad de préstamos.  
- El módulo de reportes es limitado y no genera estadísticas útiles.  

---

## 🎯 Objetivos
- Corregir errores de validación en préstamos duplicados.  
- Incorporar un módulo de usuarios para mejorar trazabilidad.  
- Optimizar la confiabilidad y escalabilidad del sistema.  
- Generar reportes más completos para la toma de decisiones.  
- Aplicar buenas prácticas de ingeniería de software en mantenimiento y evolución.  

---

## 📌 Requerimientos

### Funcionales (RF)
- **RF01:** Registro de libros con título, autor, ISBN único y cantidad de ejemplares.  
- **RF02:** Búsqueda de libros por título, autor o ISBN con estado y cantidad.  
- **RF03:** Registro de préstamos asociando libro y usuario.  
- **RF04:** Registro de devoluciones actualizando estado y fecha real.  
- **RF05:** Generación de lista de préstamos activos con fechas límite.  

### No Funcionales (RNF)
- **RNF01:** Tiempo de respuesta en búsquedas ≤ 2 segundos (hasta 5,000 registros).  
- **RNF02:** Interfaz intuitiva, máximo 3 pasos para registrar un préstamo.  
- **RNF03:** Autenticación obligatoria para bibliotecarios en funciones críticas.  

---

## 🧪 Tabla de Pruebas

| ID Caso | Tipo de Prueba | Requerimiento Asociado | Datos de Entrada | Resultado Esperado | Resultado Obtenido |
|---------|----------------|-------------------------|------------------|-------------------|-------------------|
| CPU-01  | Unitaria       | RF01 (Registro)         | Libro: *Análisis*, Autor: Pressman, ISBN: 978..., Ejemplares: 5 | Registro exitoso con stock = 5 | ✅ Éxito |
| CPU-02  | Unitaria       | RF03 (Préstamo)         | ISBN: 978..., Usuario: 101 | Stock disminuye a 4 | ✅ Éxito |
| CPU-03  | Unitaria       | RF04 (Devolución)       | ID Préstamo: P-001 | Stock aumenta a 5 | ✅ Éxito |
| CPV-01  | Validación     | RF02 + RNF01            | Búsqueda por Autor: Pressman | Respuesta < 2s | ✅ 0.8s |
| CPV-02  | Validación     | RF03 + RNF03            | Préstamo sin login | Operación rechazada | ✅ Bloqueado |

---

## 🔧 Tipo de mantenimiento propuesto
- **Correctivo:** Resolver defectos como préstamos duplicados.  
- **Perfectivo:** Añadir módulo de usuarios y control de disponibilidad, mejorando trazabilidad y escalabilidad.  

**Impacto esperado:**
- Mayor confiabilidad de datos.  
- Transparencia en la gestión de préstamos.  
- Escalabilidad y mantenibilidad del sistema.  

---

## 🔄 Reflexión sobre el control de versiones
El control de versiones es esencial para proyectos de software, especialmente en entornos académicos y colaborativos:  
- Permite **registrar cambios** y mantener un historial claro de modificaciones.  
- Facilita la **colaboración en equipo**, evitando conflictos en el código.  
- Asegura la **trazabilidad de requerimientos y pruebas**, vinculando cada cambio con su justificación.  
- Favorece la **mejora continua**, ya que cada iteración queda documentada y puede revertirse si es necesario.  

En este caso, aplicar control de versiones (ej. Git/GitHub) garantiza que las mejoras propuestas (módulo de usuarios, validaciones, reportes) se integren de manera ordenada y verificable, fortaleciendo la calidad del sistema y la experiencia del equipo desarrollador.  
