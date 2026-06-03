# Simulador Web de Abastecimiento, Precios y Consumo Familiar en Contextos de Crisis

[cite_start]Este proyecto consiste en una aplicación web interactiva de carácter educativo e informático diseñada para representar, calcular y visualizar el impacto de variables socioeconómicas y logísticas críticas del contexto nacional actual mediante modelos matemáticos sencillos[cite: 5, 22]. [cite_start]La herramienta tiene la finalidad de servir como un recurso de concientización y análisis para la toma de decisiones financieras en el hogar y la comunidad, manteniendo un enfoque neutral y fundamentado en datos cuantitativos[cite: 6].

## 📁 Organización de la Estructura de Carpetas
[cite_start]El árbol de directorios ha sido estructurado respetando fielmente la distribución física de los archivos del proyecto, organizando los archivos HTML principales en la raíz y agrupando ordenadamente los recursos de estilos, scripts e imágenes[cite: 16, 162, 164]:

```text
proyecto-web-crisis/
│
├── index.html          # Portal de acceso central y enrutamiento (Dashboard general)
├── index_abas.html     # Módulo interactivo: Simulador de Precios de Alimentos (Escenario B)
├── indexfami.html      # Módulo interactivo: Simulador de Costo de Transporte (Escenario C)
├── indexsum.html       # Módulo interactivo: Simulador de Compras Familiares (Escenario D)
│
├── css/                # Directorio de Hojas de Estilo Externas
│   ├── estilos.css     # Estilos base del portal de acceso principal
│   ├── estilos1.css    # Diseño y paleta de colores para el Escenario B
│   ├── estilos2.css    # Diseño y paleta de colores para el Escenario C
│   └── estilos3.css    # Diseño y paleta de colores para el Escenario D
│
├── js/                 # Directorio de Lógica de JavaScript Externo
│   ├── script.js       # Captura de datos, validación y cálculos del Escenario B
│   ├── script2.js      # Captura de datos, validación y cálculos del Escenario C
│   └── script3.js      # Captura de datos, validación y cálculos del Escenario D
│
├── img/                # Directorio de Recursos Gráficos e Ilustraciones
│   ├── alimentos.png   # Imagen descriptiva para el simulador de precios
│   ├── transporte.png  # Imagen descriptiva para el simulador de logística
│   └── presupuesto.png # Imagen descriptiva para el simulador familiar
│
└── README.md           # Documentación técnica e institucional del proyecto
#<span style="color: #0056b3;">Simulador Web de Impacto Económico en Contexto de Crisis</span>

## <span style="color: #0056b3;">📝 Descripción General del Proyecto</span>
[cite_start]Este simulador interactivo ha sido desarrollado como parte del Desafío Final de Programación Web I[cite: 1]. [cite_start]Su propósito principal es aplicar modelos matemáticos sencillos para calcular y visualizar cómo diversos factores de la coyuntura actual afectan directamente la economía de los hogares bolivianos[cite: 5, 8]. 

[cite_start]El proyecto se enfoca en analizar tres problemáticas clave mediante herramientas digitales interactivas: la subida en el precio de los alimentos de la canasta familiar, el incremento en los costos de traslado debido a desvíos viales y la gestión de un presupuesto familiar limitado frente a la inflación.

---

## <span style="color: #0056b3;">🥑 Escenario B: Simulador de Precios de Alimentos</span>

### <span style="color: #0056b3;">1. ¿Cómo Funciona?</span>
1. [cite_start]**Captura de Datos:** A través de un formulario con estructura HTML5, el usuario introduce el nombre de un alimento básico (ej. Arroz, Papa, Aceite), su precio anterior, su precio actual, la cantidad que consume semanalmente y el número de semanas a evaluar[cite: 17, 59, 60, 61, 62, 63].
2. [cite_start]**Validación:** El código JavaScript verifica que no existan campos vacíos y que los precios introducidos sean valores numéricos reales mayores a cero[cite: 191].
3. [cite_start]**Cálculo de Variables:** Al presionar el botón de calcular, el script procesa de forma interna la tasa porcentual del incremento y el impacto acumulado[cite: 14, 192].
4. [cite_start]**Muestra Dinámica:** Utilizando la manipulación del DOM, la sección de resultados despliega de manera inmediata (sin recargar la página) tarjetas de datos que le revelan al usuario exactamente cuánto dinero extra está gastando la familia por el encarecimiento de ese producto[cite: 15, 18, 71].

### <span style="color: #0056b3;">2. Fórmulas Matemáticas del Escenario B</span>

* [cite_start]**Incremento Neto del Precio:** [cite: 65, 196]
  $$\text{Incremento} = \text{Precio Actual} - \text{Precio Anterior}$$

* [cite_start]**Porcentaje de Aumento de Costo:** [cite: 66, 196]
  $$\text{Porcentaje de Aumento} = \left( \frac{\text{Precio Actual} - \text{Precio Anterior}}{\text{Precio Anterior}} \right) \times 100$$

* [cite_start]**Gasto Semanal Anterior y Actual:** [cite: 67]
  $$\text{Gasto Semanal Anterior} = \text{Precio Anterior} \times \text{Cantidad Semanal}$$
  $$\text{Gasto Semanal Actual} = \text{Precio Actual} \times \text{Cantidad Semanal}$$

* [cite_start]**Gasto Total Adicional en el Periodo:** [cite: 68, 69]
  $$\text{Diferencia Total Cobrada} = (\text{Gasto Semanal Actual} - \text{Gasto Semanal Anterior}) \times \text{Semanas Evaluadas}$$

### <span style="color: #0056b3;">3. Caso de Estudio para Pruebas (Alimentos)</span>
[cite_start]Para comprobar que los algoritmos de JavaScript funcionen según lo requerido, se puede ingresar este lote de prueba en el simulador[cite: 135, 144]:

| Producto | Precio Anterior | Precio Actual | Cantidad Mensual | Resultado Esperado |
| :--- | :---: | :---: | :---: | :--- |
| **Arroz** | 8 Bs. | 11 Bs. | 10 unidades | Gasto Anterior: 80 Bs. / Gasto Actual: 110 Bs. [cite_start]/ **Diferencia: +30 Bs.** [cite: 144, 146] |
| **Papa** | 7 Bs. | 10 Bs. | 8 unidades | Gasto Anterior: 56 Bs. / Gasto Actual: 80 Bs. [cite_start]/ **Diferencia: +24 Bs.** [cite: 144, 146] |
| **Aceite** | 12 Bs. | 18 Bs. | 4 unidades | Gasto Anterior: 48 Bs. / Gasto Actual: 72 Bs. [cite_start]/ **Diferencia: +24 Bs.** [cite: 144, 146] |

---

## <span style="color: #0056b3;">🚌 Escenario C: Simulador de Costo de Transporte</span>

### <span style="color: #0056b3;">1. ¿Cómo Funciona?</span>
1. [cite_start]**Captura de Datos:** El usuario ingresa la distancia normal de su ruta diaria, la nueva distancia recorrida obligatoriamente tras un desvío o bloqueo, el costo operativo por kilómetro y el número total de viajes que realiza en la semana[cite: 77, 78, 79, 80].
2. [cite_start]**Validación:** JavaScript comprueba de forma lógica que la distancia alternativa con desvío sea mayor a la distancia original de la ruta limpia[cite: 191].
3. [cite_start]**Cálculo de Variables:** El motor JavaScript efectúa las restas y multiplicaciones correspondientes para determinar la fuga financiera por viaje, por semana y por mes[cite: 81, 192].
4. [cite_start]**Muestra Dinámica:** Se ayuda del DOM de la aplicación para mostrar los resultados en pantalla[cite: 15]. [cite_start]Si el gasto adicional acumulado sobrepasa los límites razonables, los estilos de las tarjetas cambian de color dinámicamente a un tono de alerta crítico[cite: 195].

### <span style="color: #0056b3;">2. Fórmulas Matemáticas del Escenario C</span>

* [cite_start]**Costo Financiero de la Ruta Normal:** [cite: 82]
  $$\text{Costo Normal} = \text{Distancia Normal} \times \text{Costo por Kilómetro}$$

* [cite_start]**Costo Financiero con Ruta Desviada:** [cite: 83]
  $$\text{Costo con Desvío} = \text{Distancia con Desvío} \times \text{Costo por Kilómetro}$$

* [cite_start]**Gasto Adicional Neto por Viaje:** [cite: 84, 196]
  $$\text{Costo Adicional por Viaje} = (\text{Distancia con Desvío} - \text{Distancia Normal}) \times \text{Costo por Kilómetro}$$

* [cite_start]**Impacto Financiero Semanal:** [cite: 85]
  $$\text{Gasto Adicional Semanal} = \text{Costo Adicional por Viaje} \times \text{Viajes por Semana}$$

* [cite_start]**Impacto Financiero Mensual Proyectado:** [cite: 85]
  $$\text{Gasto Adicional Mensual} = \text{Gasto Adicional Semanal} \times 4 \text{ semanas}$$

### <span style="color: #0056b3;">3. Caso de Estudio para Pruebas (Transporte)</span>
[cite_start]Para verificar las operaciones matemáticas exactas del archivo de control `script.js`, ingresa los siguientes datos oficiales[cite: 147, 148]:

* [cite_start]**Distancia normal:** 10 km [cite: 148]
* [cite_start]**Distancia con desvío:** 16 km [cite: 148]
* [cite_start]**Costo por km:** 2 Bs. [cite: 148]
* [cite_start]**Viajes por semana:** 5 viajes [cite: 148]

[cite_start]**Resultado en pantalla esperado:** El sistema debe desplegar de manera interactiva un gasto adicional acumulado de exactamente **`60 Bs.`** a la semana[cite: 150].

---

## <span style="color: #0056b3;">💰 Escenario D: Simulador de Compras Familiares</span>

### <span style="color: #0056b3;">1. ¿Cómo Funciona?</span>
1. [cite_start]**Captura de Datos:** El usuario interactúa con un formulario interactivo donde introduce el presupuesto total disponible de la familia, el precio de los productos de su lista básica y la cantidad de unidades que planea adquirir[cite: 17, 93, 94, 95].
2. [cite_start]**Validación:** El sistema evalúa mediante JavaScript que todos los inputs contengan números válidos y que el presupuesto no sea un valor negativo[cite: 191].
3. [cite_start]**Cálculo de Variables:** La aplicación calcula el total de la compra planificada, resta este valor del dinero disponible para hallar el saldo restante y, en caso negativo, calcula la cantidad exacta de dinero faltante[cite: 96, 97, 98, 99].
4. [cite_start]**Muestra Dinámica y Clasificación:** A través del DOM, la página muestra inmediatamente un mensaje claro indicando si el dinero alcanza o no alcanza para cubrir los alimentos básicos[cite: 15, 102]. [cite_start]Adicionalmente, el sistema clasifica automáticamente el nivel del gasto (bajo, medio o alto) y cambia el color del contenedor de resultados para reflejar este estado financiero[cite: 100, 195].

### <span style="color: #0056b3;">2. Fórmulas Matemáticas del Escenario D</span>

* [cite_start]**Total de la Compra:** [cite: 97, 196]
  $$\text{Total Compra} = \text{Precio de Producto} \times \text{Cantidad a Comprar}$$

* [cite_start]**Cálculo de Saldo Disponible (Si el presupuesto es mayor o igual al total):** [cite: 98]
  $$\text{Saldo Restante} = \text{Presupuesto Familiar} - \text{Total Compra}$$

* [cite_start]**Cálculo de Monto Faltante (Si el presupuesto es menor al total):** [cite: 99]
  $$\text{Monto Faltante} = \text{Total Compra} - \text{Presupuesto Familiar}$$

### <span style="color: #0056b3;">3. Caso de Estudio para Pruebas (Presupuesto)</span>
[cite_start]Para verificar que las condicionales lógicas de JavaScript funcionen correctamente al evaluar si el dinero es suficiente, utiliza los siguientes parámetros[cite: 151, 152]:

* [cite_start]**Presupuesto disponible:** 500 Bs. [cite: 152]
* [cite_start]**Total de la compra realizada:** 580 Bs. [cite: 152]

[cite_start]**Resultado en pantalla esperado:** El simulador debe arrojar un mensaje dinámico indicando que el presupuesto **no alcanza** y reflejar un monto faltante de exactamente **`80 Bs.`**[cite: 154].

---

## <span style="color: #0056b3;">🛠️ Requisitos Técnicos e Implementación</span>
* [cite_start]**Estructura Semántica:** Marcación pura HTML5 (`<header>`, `<main>`, `<section>`, `<article>`, `<footer_>`)[cite: 161].
* [cite_start]**Estilos Externos:** Archivo `estilos.css` enlazado de manera externa con diseño fluido y responsivo adaptado mediante Media Queries para Smartphones, Tablets y Computadoras de escritorio[cite: 161, 162].
* [cite_start]**Lógica en JavaScript:** Archivo `script.js` independiente que procesa la lógica matemática de las variables capturadas desde los inputs y muta los resultados en el DOM sin recargas de pantalla[cite: 161].
* [cite_start]**Control de Versiones:** Repositorio estructurado ordenadamente en carpetas y subido a GitHub, publicado mediante GitHub Pages para su visualización y evaluación libre en internet[cite: 162].
# <p align="center" style="color: #1e3a8a; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; font-size: 2.2em; font-weight: bold; margin-bottom: 5px;">Simulador Web de Impacto Económico en Contexto de Crisis</p>

---

## <span style="color: #1e3a8a; font-family: sans-serif; border-bottom: 2px solid #2563eb; padding-bottom: 5px; display: block;">🥑 3. Escenario B: Simulador de Precios de Alimentos</span>

### <span style="color: #2563eb;">3.1 Flujo Operacional</span>
* **Entrada de Datos:** El usuario declara las especificaciones del alimento básico mediante el formulario nativo (nombre, costo histórico, costo vigente, tasa de consumo y semanas de proyección).
* **Control de Calidad (Validación):** El motor JS intercepta el evento de cálculo para bloquear campos vacíos o valores incoherentes ($\leq 0$).
* **Procesamiento de Datos:** El sistema calcula el incremento aritmético absoluto y el comportamiento porcentual indexado de la inflación del artículo.
* **Renderizado Dinámico:** La interfaz altera las propiedades de los nodos del DOM para pintar las tarjetas con el balance totalizado de pérdida financiera familiar sin recargar el navegador.

### <span style="color: #2563eb;">3.2 Modelos Matemáticos Utilizados</span>
* **Incremento Absoluto del Costo ($I$):**
  $$I = \text{Precio Actual} - \text{Precio Anterior}$$
* **Porcentaje de Variación de Costo ($\Delta\%$):**
  $$\Delta\% = \left( \frac{\text{Precio Actual} - \text{Precio Anterior}}{\text{Precio Anterior}} \right) \times 100$$
* **Gasto Total Extraordinario del Periodo ($G_{EA}$):**
  $$G_{EA} = \Big[ (\text{Precio Actual} \times \text{Cant. Semanal}) - (\text{Precio Anterior} \times \text{Cant. Semanal}) \Big] \times \text{Semanas}$$

### <span style="color: #2563eb;">3.3 Dataset de Validación (Caso de Estudio)</span>

| Alimento Evaluado | Precio Anterior | Precio Actual | Consumo Mensual | Impacto Monetario Esperado |
| :--- | :---: | :---: | :---: | :--- |
| **Arroz** | 8 Bs. | 11 Bs. | 10 u. | Gasto Anterior: 80 Bs. / Actual: 110 Bs. / Diferencia: +30 Bs. |
| **Papa** | 7 Bs. | 10 Bs. | 8 u. | Gasto Anterior: 56 Bs. / Actual: 80 Bs. / Diferencia: +24 Bs. |
| **Aceite** | 12 Bs. | 18 Bs. | 4 u. | Gasto Anterior: 48 Bs. / Actual: 72 Bs. / Diferencia: +24 Bs. |

---

## <span style="color: #1e3a8a; font-family: sans-serif; border-bottom: 2px solid #2563eb; padding-bottom: 5px; display: block;">🚌 4. Escenario C: Simulador de Costo de Transporte</span>

### <span style="color: #2563eb;">4.1 Flujo Operacional</span>
* **Entrada de Datos:** Captura interactiva del kilometraje óptimo (ruta normal), el kilometraje forzado (desvíos o rutas de contingencia), el costo de operación directa por km y la frecuencia semanal de viajes.
* **Validación:** El sistema restringe el cálculo si la distancia con desvío es menor o igual al trayecto estándar, previniendo falsos positivos.
* **Cálculo de Variables:** JavaScript procesa el impacto financiero marginal multiplicando las diferencias de kilometraje por los factores económicos.
* **Manejo del DOM y Alertas:** Actualiza el layout y cambia las clases de CSS dinámicamente si el nuevo gasto altera críticamente el presupuesto de transporte (alertas condicionales en color rojo).

### <span style="color: #2563eb;">4.2 Modelos Matemáticos Utilizados</span>
* **Costo Adicional Neto por Trayecto ($C_{AT}$):**
  $$C_{AT} = (\text{Distancia con Desvío} - \text{Distancia Normal}) \times \text{Costo por Kilómetro}$$
* **Gasto Adicional Semanal Acumulado ($G_{AS}$):**
  $$G_{AS} = C_{AT} \times \text{Viajes por Semana}$$
* **Proyección de Desfase Financiero Mensual ($P_M$):**
  $$P_M = G_{AS} \times 4$$

### <span style="color: #2563eb;">4.3 Dataset de Validación (Caso de Estudio)</span>
* **Ruta Normal / Desvío:** 10 km / 16 km
* **Costo Base por Km / Viajes Semanales:** 2 Bs. / 5 viajes
* **Resultado Esperado:** Visualización interactiva en pantalla de un incremento de coste semanal de exactamente `60 Bs.`.

---

## <span style="color: #1e3a8a; font-family: sans-serif; border-bottom: 2px solid #2563eb; padding-bottom: 5px; display: block;">💰 5. Escenario D: Simulador de Compras Familiares</span>

### <span style="color: #2563eb;">5.1 Flujo Operacional</span>
* **Entrada de Datos:** El usuario suministra el monto del presupuesto de contingencia disponible del núcleo familiar, el precio unitario del catálogo de productos y el volumen de adquisición proyectado.
* **Procesamiento de Balance:** JavaScript calcula el valor bruto totalizado de la canasta planificada y lo contrasta mediante sentencias lógicas condicionales (`if/else`) frente al presupuesto disponible.
* **Clasificación Inteligente:** El sistema evalúa el estado presupuestario final:
  * **Superávit:** Muestra el dinero remanente (Saldo Restante).
  * **Déficit:** Calcula con precisión el capital que falta para completar la compra (Monto Faltante).
* **Feedback de Estilo:** El sistema utiliza manipuladores de nodos del DOM (`classList`) para pintar el contenedor de resultados de color verde (Gasto Bajo/Medio) o rojo crítico (Presupuesto Insuficiente/Gasto Alto).

### <span style="color: #2563eb;">5.2 Modelos Matemáticos Utilizados</span>
* **Costo de Compra Planificada ($C_C$):**
  $$C_C = \text{Precio de Producto} \times \text{Cantidad a Comprar}$$
* **Ecuación de Saldo Restante ($S$):** *(Ejecutada si $Presupuesto \geq C_C$)*
  $$S = \text{Presupuesto Familiar} - C_C$$
* **Ecuación de Capital Faltante ($F$):** *(Ejecutada si $Presupuesto < C_C$)*
  $$F = C_C - \text{Presupuesto Familiar}$$

### <span style="color: #2563eb;">5.3 Dataset de Validación (Caso de Estudio)</span>
* **Presupuesto Declarado:** 500 Bs.
* **Monto Bruto de Compra:** 580 Bs.
* **Resultado Esperado:** Alerta interactiva de presupuesto insuficiente e indicador dinámico de capital faltante igual a `80 Bs.`.

---

## <span style="color: #1e3a8a; font-family: sans-serif; border-bottom: 2px solid #2563eb; padding-bottom: 5px; display: block;">🛠️ 6. Ficha Técnica de Tecnologías Utilizadas</span>

* **Markup & Estructura:** HTML5 semántico puro empleando etiquetas de organización nativa (`<header>`, `<main>`, `<section>`, `<article>`, `<footer_>`) para garantizar accesibilidad e indexación óptima.
* **Diseño e Identidad Visual:** CSS3 modular implementando sistemas de diseño responsivo mediante **Media Queries**, asegurando adaptabilidad total en smartphones, tablets y pantallas de escritorio.
* **Lógica del Lado del Cliente:** JavaScript estructurado (ES6+) que maneja eventos asíncronos en los formularios, realiza los procesos de cálculo de los modelos y muta el DOM en tiempo real.
* **Despliegue Continuo:** Gestión del código fuente mediante Git y publicación mediante servidores estáticos de GitHub Pages.