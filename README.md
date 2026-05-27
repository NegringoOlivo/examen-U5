🏆 Evaluación: Sistema Integral de Cosecha 🥑📊

Objetivo: 🎯 Integrar todos los conocimientos adquiridos manejando vectores (1D) y matrices (2D) como parámetros de funciones, fomentando la reutilización de código y la lógica avanzada.

Contexto: 🚜 Gestión agrícola y Agroexportación.

Una importante huerta empacadora necesita automatizar el pago y la evaluación de sus cuadrillas (equipos) de recolección. Actualmente, llevan el registro de cuántas cajas recolecta cada cuadrilla de lunes a viernes en una hoja de cálculo, pero quieren un sistema en Java que analice estos datos y genere el reporte de nómina automáticamente.

📝 Descripción del Problema

El programa contará con dos estructuras de datos principales inicializadas en memoria:

Un vector de texto (String[]) con los nombres de las 3 cuadrillas (Ej. ["Los Halcones", "Cuadrilla Norte", "Fuerza Verde"]).

Una matriz numérica (int[][]) de 3 filas x 5 columnas, donde cada fila corresponde a una cuadrilla y cada columna a los días de la semana (Lunes a Viernes). El contenido serán las cajas recolectadas.

Requerimientos de Arquitectura (Reglas Estrictas) 🚧:

Para que el código sea válido, no puedes hacer todo en el main. Debes diseñar el sistema utilizando exactamente los siguientes dos submódulos independientes:

🧩 Módulo 1: calcularTotalSemana

¿Qué recibe? Un arreglo unidimensional de números enteros (int[]). Este arreglo representará la semana de trabajo de una sola cuadrilla.

¿Qué hace? Recorre ese arreglo sumando todas las cajas.

¿Qué devuelve? El total de la suma (int).

🧩 Módulo 2: generarReporteGeneral

¿Qué recibe? ¡Ambas estructuras! Recibe el vector de nombres (String[]) y la matriz de cosechas (int[][]).

¿Qué hace? 1. Recorre a las cuadrillas mediante un ciclo.
2. Por cada cuadrilla, extrae su fila correspondiente de la matriz y se la envía al Módulo 1 (calcularTotalSemana) para descubrir cuánto recolectaron en total.
3. Imprime en pantalla el nombre de la cuadrilla y su total de cajas.
4. Reto extra: Durante el recorrido, debe ir comparando los totales para descubrir qué cuadrilla fue la más productiva y coronarla como la "Campeona de la Semana".

¿Qué devuelve? Nada (void), su trabajo es procesar e imprimir.

📋 El Programa Principal (main)

El main será extremadamente limpio. Su única responsabilidad será declarar los datos crudos y llamar al Módulo 2 para que haga toda la magia.

// Datos base sugeridos para el alumno en el main:
String[] nombresCuadrillas = {"Los Halcones", "Cuadrilla Norte", "Fuerza Verde"};
int[][] cosechasSemana = {
    {120, 135, 110, 140, 150}, // Cosecha de Los Halcones
    {90,  105, 100, 115, 120}, // Cosecha de Cuadrilla Norte
    {150, 160, 155, 170, 165}  // Cosecha de Fuerza Verde
};



📤 Salida Esperada ✨

Una vez que las funciones se comuniquen correctamente entre sí, la consola deberá mostrar exactamente lo siguiente:

=================================================
 🚜 REPORTE SEMANAL DE COSECHA DE AGUACATE 🚜
=================================================

📋 Analizando rendimiento de las cuadrillas...

➡️ Cuadrilla: Los Halcones
   Total de cajas recolectadas: 655
➡️ Cuadrilla: Cuadrilla Norte
   Total de cajas recolectadas: 530
➡️ Cuadrilla: Fuerza Verde
   Total de cajas recolectadas: 800

-------------------------------------------------
🏆 ¡CUADRILLA CAMPEONA DE LA SEMANA! 🏆
>> Fuerza Verde con un récord de 800 cajas.
=================================================
