# Sistema de Lógica Difusa: Evaluación de Satisfacción

El código implementa un sistema de control difuso para predecir la satisfacción de un usuario en base a dos factores: la calidad de un servicio o producto y el tiempo de espera.

## Requisitos

Para ejecutar este código es necesario tener instalado tanto Python como las siguientes dependencias:

*   `numpy`
*   `scikit-fuzzy`

## Estructura del Código

El código está dividido en cuatro bloques:

*   **Definición de Variables y Funciones de Pertenencia:** Se configuran los universos de discurso para las entradas (calidad del 0 al 10, espera del 0 al 30) y la salida (satisfacción del 0 al 10). Para representar la incertidumbre, se utilizan diferentes tipos de funciones matemáticas: triangulares para la calidad, trapezoidales para los tiempos de espera y gaussianas para la satisfacción final.

*   **Fuzzificación Manual:** El código incluye un breve paso demostrativo donde se calcula el grado de pertenencia exacto de valores arbitrarios (calidad 3, espera 25) dentro de sus respectivos conjuntos difusos utilizando interpolación.

*   **Reglas Difusas:** Se establecen las relaciones lógicas (el "cerebro" del sistema) que conectan las entradas con la salida a través de operadores AND (&) y OR (|). Se definen tres reglas fundamentales:
    *   Si la calidad es alta y la espera es corta, la satisfacción es alta.
    *   Si la calidad es baja o la espera es larga, la satisfacción es baja.
    *   Si ambas variables son medias, la satisfacción es media.

*   **Simulación y Casos de Prueba:** Se empaquetan las reglas en el sistema de `ControlSystemSimulation`. Posteriormente, se itera sobre una lista de casos de prueba reales `[(3, 25), (9, 2), (6, 12)]` para calcular (defuzzificar) el valor final de la satisfacción e imprimirlo.

## Uso y Resultados

Al ejecutar el script en Python, el sistema procesará los casos de prueba definidos en el código y mostrará el cálculo de la satisfacción final para cada escenario de prueba propuesto.