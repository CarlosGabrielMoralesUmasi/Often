Sistema de Control Autónomo para Drones
=======================================

Este proyecto propone un sistema avanzado de navegación autónoma para drones que utiliza tecnologías de vanguardia como ORB-SLAM3 para estimación de trayectorias y Filtros de Kalman extendidos para fusión de datos de sensores. El sistema está diseñado para maximizar la precisión y estabilidad en la navegación, utilizando una interfaz intuitiva basada en gestos humanos.

---

1. Introducción
---------------

El proyecto aborda los siguientes desafíos:
- Precisión en la localización en entornos complejos.
- Gestión de incertidumbres en sensores como IMU y GPS.
- Respuesta rápida a cambios en el entorno.

La propuesta incluye:
- **ORB-SLAM3**: Estimación precisa de trayectorias sin reconstrucción 3D en tiempo real para minimizar la carga computacional.
- **Filtros de Kalman Extendidos (EKF)**: Fusión de datos para mejorar la precisión y robustez.
- **Control por Gestos**: Utilizando Kinect para una interacción natural con el sistema.

---

2. Arquitectura y Flujo de Datos
--------------------------------

El sistema se organiza en una estructura modular que incluye los siguientes pasos:

1. **Captura de Gestos**: 
   Los gestos del usuario son detectados con Kinect y procesados en Unity.
   
2. **Análisis y Comandos**:
   Unity analiza los gestos y genera comandos específicos enviados a Firebase para su transmisión.

3. **Navegación Autónoma**:
   ORB-SLAM3 estima la posición del dron en tiempo real, mientras que los Filtros de Kalman refinan estas estimaciones al fusionar datos de sensores como IMU y GPS.

4. **Ejecución de Comandos**:
   El dron sigue los comandos procesados para ajustar su trayectoria con precisión.

---

3. Componentes Clave
---------------------

1. **ORB-SLAM3**:
   - Algoritmo de Localización y Mapeo Simultáneo que estima la trayectoria del dron basándose en datos de la cámara.

2. **Filtros de Kalman**:
   - Proporcionan estimaciones precisas al fusionar datos de múltiples sensores y gestionar incertidumbres.

3. **Control por Gestos**:
   - Kinect detecta y traduce movimientos humanos en comandos dinámicos.

4. **Firebase**:
   - Sirve como intermediario para la comunicación en tiempo real entre el operador y el dron.

---

4. Evaluación
-------------

El sistema se probó en trayectorias geométricas específicas para evaluar su precisión y estabilidad:

1. **Línea Recta**:
   - Baja complejidad para establecer una línea base de evaluación.

2. **Triángulo**:
   - Introduce giros abruptos y evalúa la capacidad del sistema para manejar cambios de dirección.

3. **Octógono**:
   - Trayectoria compleja con múltiples giros para medir la robustez del sistema.

Los resultados muestran:
- Reducción significativa del error cuadrático medio (RMSE).
- Estabilidad en condiciones adversas y entornos con incertidumbres.
- Alta precisión en trayectorias geométricas predefinidas.

---

5. Conclusión
-------------

La integración de ORB-SLAM3 con Filtros de Kalman ofrece una solución robusta para la navegación autónoma de drones, logrando una precisión óptima en la estimación de trayectorias. La interfaz basada en gestos y la fusión eficiente de datos convierten a este sistema en una herramienta innovadora en el campo de la navegación de UAVs.

Este proyecto representa un avance significativo en la interacción humano-máquina para drones y abre nuevas posibilidades para aplicaciones prácticas en entornos dinámicos.

---

Para más detalles, consulta la documentación técnica incluida.
