# EncuestIA

El informe de la encuesta de vuestra asociación, con cifras y gráficos calculados por código. Aplicación web de un solo fichero, del curso «IA para asociaciones de pacientes» del Instituto ProPatiens y la Cátedra del Paciente de la Universidad Miguel Hernández de Elche.

**Usar la app:** https://fborrasumh.github.io/encuestia/ · **Portal del curso:** https://fborrasumh.github.io/propatiens/

**Idiomas:** castellano (por defecto), català, euskara, galego, English y português (selector en la barra superior o `?lang=` en la URL).

## Qué hace

1. **La encuesta.** Se sube el archivo de respuestas (CSV o Excel, por ejemplo la exportación de Google Forms o Microsoft Forms) y, si se quiere, el perfil común de la asociación.
2. **Las preguntas.** El código reconoce el tipo de cada columna (escala, número, categoría, respuesta múltiple, respuesta abierta, identificador o dato personal) y se puede corregir a mano. Se puede elegir una columna de grupo (paciente, familiar…) y una de momento (antes/después).
3. **El informe.** Para cada pregunta: tabla de frecuencias y gráfico de barras; en escalas, media y porcentaje de 4 o más; comparación antes/después y por grupos. La IA agrupa las respuestas abiertas en temas con citas literales y redacta un resumen y unas conclusiones a partir de las tablas.
4. **Descarga:** el informe en Word, con los gráficos dentro.

## Qué comprueba el código (la IA propone, el código comprueba)

- **Todas las cifras y gráficos los calcula el código**, no la IA.
- **Temas de las respuestas abiertas:** la IA asigna cada respuesta a un tema; el código cuenta cuántas hay en cada uno y comprueba que cada cita existe literalmente en las respuestas. Las citas que no están se descartan.
- **Resumen y conclusiones:** el código comprueba que cada cifra del texto está en las tablas. Si no está, se marca «Revisar: cifras que no están en las tablas».
- **Limitaciones:** las escribe el código según los datos (tamaño de la muestra, si antes y después son las mismas personas, grupos ocultos).

## Privacidad

- El archivo se lee y se analiza en el navegador; nada se guarda fuera de él.
- **Datos personales:** las columnas con nombres, correos, teléfonos o DNI (por la cabecera o porque las celdas lo son) se excluyen del análisis y no salen del navegador.
- **Grupos de menos de 5 personas** no se muestran en ninguna tabla ni gráfico, para que nadie sea identificable.
- Hacia la IA solo salen tablas agregadas y las respuestas abiertas con correos, DNI/NIE, teléfonos e IBAN enmascarados. Antes del primer envío se muestra lo que sale. Las preguntas numéricas (como la edad) se envían solo resumidas (media, mediana), nunca valor a valor.

## Límites

- Describe a las personas que respondieron, no a todo el colectivo. No hace contraste estadístico.
- El antes/después compara grupos de respuestas; no sabe si son las mismas personas.
- La detección de tipos de columna puede equivocarse: revisadla en el paso 2.
- La agrupación en temas es una propuesta de la IA: los recuentos son exactos, pero qué respuesta va en qué tema conviene revisarlo.
- Probada con IA simulada de los tres proveedores; no con una clave real.

## Perfil común de la asociación

El mismo JSON (`perfil-asociacion-pacientes`) que en DifundIA, SubvencIA y las demás apps del curso: se sube, se rellena aquí si hace falta y se descarga para la siguiente. El logo del kit de marca va en la portada del informe y no se envía a la IA.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude, guardada solo en el navegador. Sin clave, la app calcula todas las tablas y gráficos; la IA solo hace falta para los temas y la redacción.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) · ORCID [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

Licencia MIT.
