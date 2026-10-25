# Guion de video APE 004 — duración orientativa: 6 minutos

Basado en `reports/ape04_sir.pdf`. Lee las frases entre comillas y realiza las acciones indicadas. El tiempo incluye cambiar de ventana, compilar y ejecutar. Habla a ritmo natural; procura terminar entre 5:40 y 6:30 para cumplir el mínimo de cinco minutos.

## Antes de grabar

- Abre el PDF, el editor con `src/modelo/SimulacionSIR.java`, una terminal en la raíz del proyecto y `netlogo/modelo_sir_netlogo.nlogox` en NetLogo.
- Comprueba la configuración inicial: población 100, infectados iniciales 5, beta 0.30, gamma 0.10, 100 pasos y semilla 42.
- Deja preparado el comando de compilación y ejecución que aparece al final de este guion. Al cambiar `GAMMA`, hay que guardar, compilar y ejecutar otra vez.
- En NetLogo utiliza `PAUSA = 0.05` si quieres que se vea avanzar la simulación durante unos segundos. El botón continuo `go` también sirve para detenerla.
- Ten ubicadas las páginas 1, 3–9, 10 y 11–12 del PDF: identificación, metodología y gráficas, análisis y preguntas, respectivamente.

## 0:00–0:35 — Mostrar el documento y su estructura

**En pantalla:** muestra la primera página y desplázate brevemente por los títulos de las secciones. No leas las trece páginas.

> “Soy Richard Chamba y presento la práctica APE 004, sobre la comparación de un modelo SIR en Java y NetLogo. El documento contiene identificación, objetivos, materiales, metodología, resultados, análisis, preguntas de control, conclusiones y bibliografía. En metodología explicamos el procedimiento que realizamos e incluimos las gráficas. La comparación ejecutada corresponde a Java y NetLogo.”

## 0:35–1:20 — Explicar el código

**En pantalla:** muestra las carpetas `modelo`, `vista` y `controlador`; abre `SimulacionSIR.java` y señala los parámetros, `ejecutar` y `avanzar`. Después muestra brevemente la exportación del controlador.

> “El programa está organizado en modelo, vista y controlador. Persona representa a cada individuo; SimulacionSIR contiene los parámetros y las reglas; el controlador genera los archivos CSV, y la vista imprime los resultados. En cada paso, los infectados eligen un contacto al azar, intentan contagiarlo y pueden recuperarse. Los cambios se aplican juntos para que un nuevo infectado participe desde el siguiente paso. Antes de simular se validan los parámetros, y se registran ciento un tiempos, desde cero hasta cien. El movimiento en NetLogo es ilustrativo: los contactos no dependen de la cercanía.”

## 1:20–2:15 — Ejecutar y explicar el escenario base y las gráficas

**En pantalla:** ejecuta Java con gamma 0.10. Enseña la tabla y los parámetros de la consola. En NetLogo pulsa `ACTUALIZAR JAVA`, cierra la confirmación y pulsa `go`. Señala las dos gráficas SIR y las tres comparaciones.

> “El escenario base tiene cien personas, cinco infectados, beta de cero coma treinta y gamma de cero coma diez. Java genera los resultados y NetLogo carga sus datos y parámetros. Azul representa susceptibles, rojo infectados y verde recuperados. Las otras tres gráficas comparan cada estado: Java en negro y NetLogo en naranja. El pico es de veintinueve infectados en Java y cuarenta y cuatro en NetLogo. Al final quedan trece susceptibles y ochenta y siete recuperados en Java; en NetLogo, ocho susceptibles y noventa y dos recuperados. Los infectados llegan a cero. Las curvas difieren por las secuencias aleatorias, aunque usamos las mismas reglas y parámetros.”

## 2:15–3:20 — Cambiar el escenario y explicar el resultado

**En pantalla:** cambia **solo** `GAMMA = 0.10` por `GAMMA = 0.40`. Guarda, vuelve a compilar y ejecuta Java. En NetLogo pulsa `ACTUALIZAR JAVA`, comprueba que aparece gamma 0.4, cierra la confirmación y pulsa `go`.

> “Ahora cambio únicamente gamma a cero coma cuarenta; los demás valores se conservan. Esto aumenta la probabilidad de recuperación en cada paso. Guardo, compilo y ejecuto nuevamente para regenerar los archivos. Después actualizo NetLogo y compruebo el nuevo valor en pantalla. La simulación se reinicia con el mismo escenario que Java, porque se importan tanto los resultados como los parámetros. No tenemos que editar gamma por separado en NetLogo. Ahora el pico baja a seis infectados en Java y cinco en NetLogo. Ambas corridas terminan con ochenta y nueve susceptibles, cero infectados y once recuperados. En estas ejecuciones, la recuperación más rápida reduce el brote.”

**Mientras hablas:** señala los nuevos picos y los conteos finales. Puedes mostrar la Figura 6 del informe para comparar ambos escenarios. La curva Java aparece completa al importar; la curva propia de NetLogo se construye al ejecutar `go`.

## 3:20–5:55 — Leer las diez preguntas individualmente y responder

**En pantalla:** vuelve a las páginas 11 y 12 del PDF. Lee cada pregunta completa y da la respuesta breve. No leas todo el párrafo del documento.

1. **Pregunta y respuesta:**

> “¿Qué representa el modelo SIR? Representa cómo una infección evoluciona en una población, pasando de susceptibles a infectados y después a recuperados.”

2. **Pregunta y respuesta:**

> “¿Qué representan los estados S, I y R? S son los susceptibles; I, los infectados que pueden transmitir; y R, los recuperados, que no vuelven a infectarse en este modelo.”

3. **Pregunta y respuesta:**

> “¿Qué función cumplen los parámetros beta y gamma? Beta controla la probabilidad de contagio por contacto y gamma la probabilidad de recuperación por paso.”

4. **Pregunta y respuesta:**

> “¿Por qué es importante utilizar los mismos parámetros en las tres herramientas? Para comparar el mismo escenario y evitar que las diferencias se deban a configuraciones distintas.”

5. **Pregunta y respuesta:**

> “¿Por qué Python, Java y NetLogo pueden producir resultados diferentes utilizando el mismo modelo? Porque pueden utilizar secuencias aleatorias distintas. La misma semilla permite repetir cada implementación, pero no hace idénticos los sorteos entre herramientas.”

6. **Pregunta y respuesta:**

> “¿Qué ventajas ofrece NetLogo para representar sistemas basados en agentes? Permite mostrar cada persona y observar sus estados, junto con los conteos y las gráficas.”

7. **Pregunta y respuesta:**

> “¿Qué ventajas ofrece SimPy para desarrollar simulaciones basadas en eventos? Permite organizar procesos, eventos y recursos compartidos. Esta respuesta es conceptual: en nuestro proyecto no implementamos SimPy.”

8. **Pregunta y respuesta:**

> “¿Qué ventajas ofrece Java para implementar modelos de simulación? Permite organizar el código en clases, controlar las reglas, validar los parámetros y exportar los resultados.”

9. **Pregunta y respuesta:**

> “¿Qué función cumple el archivo CSV en la integración Python/Java hacia NetLogo? Transporta los resultados para graficarlos. En nuestro proyecto también se exportan los parámetros para sincronizar Java y NetLogo.”

10. **Pregunta y respuesta:**

> “¿Qué ventajas presenta separar la generación de datos de la visualización? Permite comprobar y reutilizar los resultados, o cambiar las gráficas sin modificar las reglas de la simulación.”

## 5:55–6:15 — Cierre

**En pantalla:** muestra las conclusiones del documento y el enlace del repositorio.

> “Con esta práctica integramos Java y NetLogo mediante CSV, observamos la evolución SIR y comprobamos el efecto de cambiar gamma. Las diferencias entre corridas muestran la importancia del azar y de comparar los mismos parámetros. Gracias.”

## Comando preparado para la demostración

Ejecuta este comando tanto para el escenario base como después de guardar el cambio de gamma:

```bash
javac -encoding UTF-8 --release 11 -d build \
  src/Main.java src/modelo/*.java \
  src/vista/*.java src/controlador/*.java && java -cp build Main
```

Después: `ACTUALIZAR JAVA` → comprobar gamma → cerrar confirmación → `go`.

Si al terminar quieres dejar el proyecto en la configuración de la ficha, devuelve `GAMMA` a `0.10`, guarda y ejecuta de nuevo el mismo comando; después actualiza NetLogo.

## Valores de apoyo para señalar en pantalla

| Escenario | Pico Java | Pico NetLogo | Final Java (S, I, R) | Final NetLogo (S, I, R) |
|---|---:|---:|---|---|
| Gamma 0.10, semilla 42 | 29 en t=31 | 44 en t=11 | (13, 0, 87) | (8, 0, 92) |
| Gamma 0.40, semilla 42 | 6 en t=1 | 5 en t=0 | (89, 0, 11) | (89, 0, 11) |

Estos valores corresponden a las corridas del documento con sus parámetros y semilla 42. Las pausas visuales no cambian los resultados.
