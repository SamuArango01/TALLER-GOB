# 🎙️ Guion de Exposición: Taller Rastro (Monastery.com.co)
**Curso:** ST1630 - Ciberseguridad y Gobernanza de Datos  
**Equipo (4 Integrantes):** Emily Cardona, Alyson Henao Fernández, Samuel Arango, Mateo Sanz  
**Tiempo estimado:** 5 a 7 minutos

---

## 📄 Diapositiva 1: Portada y Contexto del Caso
**🗣️ Presenta:** **Emily Cardona**

* **Qué decir:**
  > "Buenas tardes a todos y profesor. Hoy nuestro equipo, conformado por Alyson, Samuel, Mateo y mi persona Emily, presenta los resultados del **Taller Rastro** sobre la organización colombiana de moda **Monastery Clothing (`monastery.com.co`)**.
  >
  > El objetivo de este trabajo fue aplicar la función **'Identificar' del marco NIST CSF** utilizando únicamente técnicas de **reconocimiento pasivo (OSINT)**. Es decir, bajo la regla de oro: *se mira pero no se toca*, evaluando lo que la organización dejó expuesto al público sin realizar escaneos ni interactuar directamente con sus servidores."

---

## 📄 Diapositiva 2: Inventario de Hallazgos Expuestos
**🗣️ Presenta:** **Alyson Henao Fernández**

* **Qué decir:**
  > "Pasando a nuestros hallazgos, realizamos un inventario estructurado dividiendo lo encontrado en 4 puntos clave:
  >
  > 1. **Google Dorking:** Ejecutamos búsquedas avanzadas sobre el dominio con palabras clave como `contraseña`, `secret` o `filetype:pdf`. El resultado fue **completamente limpio**, lo que demuestra un buen control primario de indexación.
  > 2. **Endpoint `/cart.js`:** Identificamos la respuesta pública del carrito de Shopify. Es un comportamiento por diseño que nos permitió confirmar la plataforma tecnológica subyacente.
  > 3. **Hallazgo Clave (Riesgo Operacional):** En la memoria histórica de **Wayback Machine**, encontramos un archivo CSS de pruebas archivado que exponía el **nombre completo de un desarrollador del proyecto**.
  > 4. **Repositorio GitHub:** Verificamos un repositorio de práctica llamado *hamburguers*. Al inspeccionarlo pasivamente, confirmamos que eran animaciones CSS sin relación con producción, descartándolo por rigurosidad metodológica."

---

## 📄 Diapositiva 3: Lectura Técnica & Causa Raíz
**🗣️ Presenta:** **Samuel Arango**

* **Qué decir:**
  > "Analicemos técnicamente la causa raíz de nuestro hallazgo principal:
  >
  > * **¿Por qué ocurrió?** Durante el desarrollo del sitio, se subieron archivos CSS con comentarios de autoría. Los rastreadores de archivos web como Wayback Machine indexaron y respaldaron estos recursos antes de que fueran eliminados del servidor activo.
  > * **¿Cuál es el riesgo real?** Esto no es una vulnerabilidad técnica directamente explotable, sino un vector de **Developer Profiling**. Conocer el nombre exacto del desarrollador permite a un atacante construir campañas de **Spear Phishing o Ingeniería Social** altamente dirigidas para intentar secuestrar credenciales administrativas de Shopify o de la pasarela de pagos.
  > * **Ciclo de vida del dato:** Evidencia la falta de desaprovisionamiento de activos de prueba. Aunque el archivo se elimine del servidor vivo, la memoria histórica web preserva la fuga."

---

## 📄 Diapositiva 4: Lectura de Gobernanza de Datos (DMBOK)
**🗣️ Presenta:** **Mateo Sanz**

* **Qué decir:**
  > "Aquí es donde conectamos la ciberseguridad con la **Gobernanza de Datos bajo el marco DMBOK**. ¿Cómo un Comité de Gobernanza habría prevenido esta exposición?
  >
  > 1. **Data Owner (Dueño del Dato):** Falta asignar una custodia clara (*Head of E-commerce / IT Lead*) que autorice formalmente cada activo que se despliega en producción.
  > 2. **Clasificación de la Información:** Los datos personales e identidades del equipo técnico no debieron tratarse como públicos, sino clasificarse como **Información Interna o Restringida**.
  > 3. **Política de Sanitización (Build Sanitization):** Faltó una regla mandatoria que ejecute la limpieza automática de comentarios y nombres de autores en los archivos antes de compilarlos para producción.
  > 4. **Rol del Comité:** El Comité debe exigir auditorías OSINT periódicas antes de aprobar nuevos lanzamientos."

---

## 📄 Diapositiva 5: Propuesta Comercial de Subsanación
**🗣️ Presenta:** **Emily Cardona** *(o en conjunto con Samuel)*

* **Qué decir:**
  > "Como valor agregado, diseñamos una **Propuesta Comercial de Consultoría** para subsanar estos hallazgos:
  >
  > * **Costo de Inacción (El Riesgo):** Estimamos que un ataque exitoso de Spear Phishing o fraude en Shopify le costaría a la entidad entre **$80 y $150 millones de COP**, sin contar eventuales sanciones de la SIC por la Ley 1581.
  > * **Nuestra Solución:** Proponemos un proyecto de **4 semanas** estructurado en 3 fases:
  >   * **Fase 1 (Táctica - $4.5M COP):** Sanitización de metadatos y takedown en Wayback Machine.
  >   * **Fase 2 (Gobernanza DMBOK - $8.5M COP):** Matriz RACI de Data Owners y Política de Publicación Web.
  >   * **Fase 3 (Capacitación - $3.5M COP):** Taller anti-phishing al equipo de desarrollo y auditoría final.
  > * **Inversión Total:** **$16.500.000 COP**, garantizando un alto retorno de inversión frente al costo del riesgo."

---

## 📄 Diapositiva 6: Cierre y Conclusión Executiva
**🗣️ Presenta:** **Alyson Henao Fernández**

* **Qué decir:**
  > "Para cerrar nuestra presentación, queremos dejarles la recomendación principal en una sola frase:
  >
  > *'La ciberseguridad en el e-commerce no comienza bloqueando ataques a la plataforma, sino **gobernando que la información de quienes la construyen** nunca quede expuesta al público.'*
  >
  > Muchas gracias por su atención. Quedamos atentos a sus preguntas."
