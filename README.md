# Torneos-de-futbol-por-edad
# ⚽ Automatización: Sistema de Registro para Torneo de Fútbol

Este workflow de **n8n** gestiona de punta a punta la inscripción de jugadores para un torneo. No solo recibe los datos, sino que los filtra por edad, los clasifica en categorías y los organiza automáticamente en diferentes hojas de cálculo.

## 📋 ¿Qué hace este flujo?

1.  **Captura de Datos:** Mediante un **n8n Form Trigger**, el usuario completa su nombre, email, edad y mensaje.
2.  **Validación de Edad (Filtro):** El sistema verifica que el usuario sea mayor de 18 años. Si es menor, el flujo se detiene por seguridad y cumplimiento de reglas del torneo.
3.  **Clasificación Automática (IF):** * **Categoría Junior:** Si tiene entre 18 y 39 años.
    * **Categoría Senior:** Si tiene 40 años o más.
4.  **Notificación Personalizada:** Envía un correo vía **Gmail** al administrador informando en qué categoría se inscribió el interesado.
5.  **Persistencia en Base de Datos:** Los datos se guardan automáticamente en un **Google Sheets**, separando a los jugadores en la pestaña correspondiente (Junior o Senior).

## 🛠️ Nodos Utilizados

* **Form Trigger:** Interfaz de entrada para el usuario.
* **Edit Fields (Set):** Para normalizar los nombres de las variables y asegurar que la "Edad" sea tratada como número.
* **Filter:** Regla de exclusión para menores de edad.
* **IF Node:** Lógica de bifurcación por rango de edad.
* **Google Sheets:** Conector para el guardado organizado de la base de datos.
* **Gmail:** Notificaciones dinámicas en tiempo real.

## 🚀 Ventajas de esta Automatización
* **Cero trabajo manual:** El organizador solo tiene que mirar la planilla final.
* **Segmentación inmediata:** No hay errores al clasificar a los jugadores.
* **Escalabilidad:** Se pueden agregar más categorías (ej. +50) muy fácilmente.

---
> *Proyecto de automatización desarrollado para la gestión eficiente de eventos deportivos.*
