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
## 🧮 Desglose de Escenarios, Decisiones de Desarrollo y Fórmulas Matemáticas

### 1. Escenario B: Simulador de Precios de Alimentos (`index_abas`)

#### 🔹 Qué se realizó en este escenario:
Se desarrolló una interfaz web interactiva que permite registrar alimentos, capturando su precio anterior, su precio actual, la cantidad que consume una familia a la semana y el número de semanas en análisis. El sistema procesa los datos y genera de forma dinámica filas en una tabla con los resultados financieros calculados en tiempo real.

#### 🔹 Por qué se hizo así:
* **Separación de Archivos:** Se vinculó la vista `index_abas` con su propia hoja de estilos `css/estilos1` y su lógica en `js/script.js`. Se decidió estructurarlo así para mantener un código limpio y modular, evitando que las reglas de diseño o las funciones lógicas interfieran con los demás escenarios del proyecto.
* **Uso de Tablas Dinámicas:** Se optó por mostrar los resultados dentro de una tabla estructurada en lugar de simples textos sueltos. Esto permite al usuario comparar visualmente varios productos uno tras otro y comprender el impacto acumulativo de la inflación en la canasta básica.
* **Validación de Datos:** En el script se programó un control estricto que rechaza campos vacíos o números negativos antes de hacer cualquier cálculo, garantizando que el simulador sea estable y no muestre errores matemáticos en pantalla.

#### 🔹 Fórmulas matemáticas aplicadas:

* **Título de la Fórmula: Porcentaje de Aumento de Precios**
  * **Uso en el sistema:** Programada dentro de `js/script.js` para calcular la tasa de variación relativa que sufrió el costo del producto, mostrando el porcentaje exacto de inflación que afectó a ese alimento.
  * **Expresión matemática:**
    $$\text{Porcentaje de Aumento} = \left( \frac{\text{Precio Actual} - \text{Precio Anterior}}{\text{Precio Anterior}} \right) \times 100$$

* **Título de la Fórmula: Gasto Mensual Estimado Actual**
  * **Uso en el sistema:** Implementada en `js/script.js` para proyectar el costo operativo monetario total que demanda la compra de ese insumo básico bajo los nuevos precios vigentes del mercado.
  * **Expresión matemática:**
    $$\text{Gasto Mensual Actual} = \text{Precio Actual} \times \text{Cantidad Consumida Semanal} \times \text{Número de Semanas}$$

* **Título de la Fórmula: Diferencia de Gasto (Impacto Financiero)**
  * **Uso en el sistema:** Utilizada en `js/script.js` para cuantificar la pérdida real del poder de compra del hogar, reflejando el monto neto adicional en bolivianos que se debe pagar para adquirir exactamente las mismas unidades.
  * **Expresión matemática:**
    $$\text{Diferencia de Gasto} = (\text{Precio Actual} - \text{Precio Anterior}) \times \text{Cantidad Consumida Semanal} \times \text{Número de Semanas}$$

---

### 2. Escenario C: Simulador de Costo de Transporte (`indexfami`)

#### 🔹 Qué se realizó en este escenario:
Se construyó una calculadora de gastos de movilidad donde el usuario introduce la distancia de su ruta normal en kilómetros, la distancia de la ruta con desvío o desvío vial, el costo cobrado por kilómetro y la cantidad de viajes que realiza semanalmente. La aplicación calcula inmediatamente la diferencia económica del traslado.

#### 🔹 Por qué se hizo así:
* **Independencia Estilística y Lógica:** Se asignó de manera exclusiva el archivo `css/estilos2` y el archivo `js/script2.js` a esta sección. Se hizo así porque el transporte maneja variables operativas distintas a la compra de víveres (kilómetros y frecuencias de viaje), requiriendo un diseño visual enfocado en formularios de transporte y tarjetas de alerta logística.
* **Enfoque de Planificación Familiar:** Se diseñó con el propósito de servir como una herramienta de simulación preventiva. Al mostrar el gasto adicional proyectado, permite a un ciudadano o estudiante prever de cuánto debe ser su fondo de emergencia para transportarse en situaciones de conflicto vial o bloqueos.

#### 🔹 Fórmulas matemáticas aplicadas:

* **Título de la Fórmula: Costo de Viaje en Ruta Normal**
  * **Uso en el sistema:** Ejecutada en `js/script2.js` para establecer la línea base financiera del usuario, determinando el costo regular del transporte en condiciones óptimas de circulación.
  * **Expresión matemática:**
    $$\text{Costo Normal Semanal} = \text{Distancia Normal} \times \text{Costo por Kilómetro} \times \text{Viajes por Semana}$$

* **Título de la Fórmula: Costo de Viaje con Ruta de Desvío**
  * **Uso en el sistema:** Utilizada en `js/script2.js` para calcular el incremento del costo operativo provocado por el aumento de kilometraje al tomar rutas alternas o desvíos de emergencia.
  * **Expresión matemática:**
    $$\text{Costo con Desvío Semanal} = \text{Distancia con Desvío} \times \text{Costo por Kilómetro} \times \text{Viajes por Semana}$$

* **Título de la Fórmula: Gasto Adicional por Contingencia Vial**
  * **Uso en el sistema:** Aplicada en `js/script2.js` para restar ambos costos y aislar monetariamente la brecha o pérdida económica neta causada por las alteraciones del entorno logístico.
  * **Expresión matemática:**
    $$\text{Gasto Adicional} = \text{Costo con Desvío Semanal} - \text{Costo Normal Semanal}$$

---

### 3. Escenario D: Simulador de Compras Familiares (`indexsum`)

#### 🔹 Qué se realizó en este escenario:
Se diseñó un simulador financiero de control presupuestario. El usuario ingresa el dinero total disponible en su presupuesto familiar, el precio unitario de un artículo y la cantidad de unidades que necesita adquirir. El sistema evalúa la viabilidad de la compra y emite un diagnóstico con alertas visuales.

#### 🔹 Por qué se hizo así:
* **Semaforización Dinámica del DOM:** Se enlazó a `css/estilos3` y `js/script3.js`. Se programó de esta manera para modificar las clases CSS del contenedor de resultados en tiempo real mediante JavaScript. Si el dinero es suficiente, la pantalla se ilumina en verde; si está en niveles críticos, cambia a amarillo; y si hay déficit, se inyecta una alerta en color rojo. Se hizo así para proporcionar una experiencia de usuario sumamente intuitiva y clara.
* **Control de Saldos Negativos:** En lugar de bloquear la operación o lanzar un aviso genérico de error cuando el dinero no alcanza, se programó el sistema para que realice una resta inversa. De este modo, se le muestra de manera exacta al usuario la cantidad de dinero faltante, ayudándole a reorganizar su presupuesto.

#### 🔹 Fórmulas matemáticas aplicadas:

* **Título de la Fórmula: Costo Total de Adquisición**
  * **Uso en el sistema:** Procesada en `js/script3.js` para consolidar el valor monetario de facturación total que demanda el volumen de insumos solicitados antes de comprobar la caja de fondos.
  * **Expresión matemática:**
    $$\text{Total de la Compra} = \text{Precio Unitario del Producto} \times \text{Cantidad de Unidades}$$

* **Título de la Fórmula: Saldo Remanente o Déficit Financiero**
  * **Uso en el sistema:** Operada en `js/script3.js` para calcular el balance final. Un resultado positivo indica capacidad de ahorro, mientras que un resultado negativo determina matemáticamente el dinero faltante para cubrir la necesidad.
  * **Expresión matemática:**
    $$\text{Balance de Dinero} = \text{Presupuesto Familiar} - \text{Total de la Compra}$$

* **Título de la Fórmula: Proporción e Impacto Presupuestario**
  * **Uso en el sistema:** Empleada en `js/script3.js` para obtener el porcentaje del salario o fondo consumido por la compra, sirviendo como parámetro para activar los estilos CSS de alerta (Bajo $\le 30\%$, Medio $> 30\%$ y $\le 75\%$, Alto $> 75\%$).
  * **Expresión matemática:**
    $$\text{Porcentaje de Consumo} = \left( \frac{\text{Total de la Compra}}{\text{Presupuesto Familiar}} \right) \times 100$$
## 🧮 Desglose de Escenarios, Decisiones de Desarrollo y Fórmulas Matemáticas

---

### 🛒 Escenario B: Simulador de Precios de Alimentos (`index_abas.html`)

> **Propósito del Módulo:** Cuantificar el incremento porcentual y monetario en los productos esenciales de la canasta familiar, determinando cuánto dinero extra gasta un hogar debido a la inflación semanal y mensual.

#### 🛠️ Desarrollo Realizado y Justificación Técnica

* **Estructura Modular:** Se enlazó de forma exclusiva a `css/estilos1.css` y `js/script.js`. Se diseñó así para aislar las variables de la canasta básica y evitar que los estilos de visualización colisionen con los demás módulos de la aplicación.
* **Inyección de Tablas Dinámicas:** En lugar de mostrar resultados en textos planos, cada cálculo genera una fila dentro de una tabla organizada. Esto permite al usuario registrar múltiples alimentos de manera consecutiva y comparar visualmente el impacto acumulado en su economía familiar.
* **Control de Excepciones:** Se programó una validación previa al cálculo que detiene el envío del formulario si existen campos vacíos o valores menores o iguales a cero, asegurando la consistencia matemática de los datos expuestos.

#### 📈 Fórmulas Matemáticas Utilizadas

| Título de la Fórmula | Archivo donde se usa | Uso en el Sistema | Expresión Matemática |
| :--- | :---: | :--- | :--- |
| **Porcentaje de Aumento de Precios** | `js/script.js` | Mide el porcentaje de inflación real que ha sufrido el costo unitario de un alimento básico desde su precio anterior hasta el actual. | $$\text{Porcentaje de Aumento} = \left( \frac{\text{Precio Actual} - \text{Precio Anterior}}{\text{Precio Anterior}} \right) \times 100$$ |
| **Gasto Mensual Estimado Actual** | `js/script.js` | Proyecta el costo financiero total que demanda la adquisición de un insumo según los nuevos precios del mercado vigentes. | $$\text{Gasto Mensual Actual} = \text{Precio Actual} \times \text{Cantidad Semanal} \times \text{Semanas}$$ |
| **Diferencia de Gasto (Impacto Financiero)** | `js/script.js` | Cuantifica la pérdida del poder adquisitivo, reflejando el monto neto extra en bolivianos que la familia debe pagar por las mismas unidades. | $$\text{Diferencia de Gasto} = (\text{Precio Actual} - \text{Precio Anterior}) \times \text{Cantidad Semanal} \times \text{Semanas}$$ |

---

### 🚌 Escenario C: Simulador de Costo de Transporte (`indexfami.html`)

> **Propósito del Módulo:** Estimar el impacto económico y el gasto logístico adicional provocado por la alteración de rutas tradicionales ante bloqueos, desvíos o contingencias en las vías de tránsito habituales.

#### 🛠️ Desarrollo Realizado y Justificación Técnica

* **Especialización Logística:** Se asignaron los archivos `css/estilos2.css` y `js/script2.js` de forma independiente. Debido a que el transporte no evalúa productos sino distancias, tramos y frecuencias de viaje, requería un entorno lógico aislado del comercio de víveres.
* **Simulación Preventiva:** El entorno gráfico se estructuró con tarjetas de información rápidas para que usuarios de transporte público o privado midan pérdidas kilométricas. Al reflejar el "gasto adicional", la herramienta ayuda a prever presupuestos de emergencia vial en situaciones de conflicto o desvíos.

#### 🛣️ Fórmulas Matemáticas Utilizadas

| Título de la Fórmula | Archivo donde se usa | Uso en el Sistema | Expresión Matemática |
| :--- | :---: | :--- | :--- |
| **Costo de Viaje en Ruta Normal** | `js/script2.js` | Establece la línea base financiera del usuario, determinando el costo regular del transporte en condiciones óptimas de circulación. | $$\text{Costo Normal Semanal} = \text{Distancia Normal} \times \text{Costo por Kilómetro} \times \text{Viajes por Semana}$$ |
| **Costo de Viaje con Ruta de Desvío** | `js/script2.js` | Calcula el incremento del costo operativo provocado por el aumento de kilometraje al tomar rutas alternas o desvíos de emergencia. | $$\text{Costo con Desvío Semanal} = \text{Distancia con Desvío} \times \text{Costo por Kilómetro} \times \text{Viajes por Semana}$$ |
| **Gasto Adicional por Contingencia Vial** | `js/script2.js` | Resta ambos costos para aislar monetariamente la brecha o pérdida económica neta causada por las alteraciones del entorno logístico. | $$\text{Gasto Adicional} = \text{Costo con Desvío Semanal} - \text{Costo Normal Semanal}$$ |

---

### 💰 Escenario D: Simulador de Compras Familiares (`indexsum.html`)

> **Propósito del Módulo:** Evaluar la viabilidad financiera de la canasta básica familiar contrastando un presupuesto límite contra el costo real de adquisición, emitiendo diagnósticos dinámicos del estado del capital.

# 🛠️ Desarrollo Realizado y Justificación Técnica

* **Semaforización Dinámica del DOM:** Vinculado con `css/estilos3.css` y `js/script3.js`. Se programó el script para alterar en tiempo real las clases CSS del contenedor de resultados. Dependiendo del porcentaje del presupuesto consumido, la pantalla cambia visualmente (Verde = Seguro, Amarillo = Crítico, Rojo = Fondos Insuficientes).
* **Análisis de Balance Inverso:** Cuando el dinero disponible es menor al costo de la compra, el sistema no se bloquea; ejecuta una operación matemática inversa para mostrar en pantalla la cifra exacta de dinero faltante, facilitando la reorganización del gasto doméstico.

# 📊 Fórmulas Matemáticas Utilizadas

| Título de la Fórmula | Archivo donde se usa | Uso en el Sistema | Expresión Matemática |
| :--- | :---: | :--- | :--- |
| **Costo Total de Adquisición** | `js/script3.js` | Consolida el valor total de la transacción que demanda el volumen de insumos solicitados antes de verificar la disponibilidad de fondos en caja. | $$\text{Total de la Compra} = \text{Precio Unitario del Producto} \times \text{Cantidad de Unidades}$$ |
| **Saldo Remanente o Déficit Financiero** | `js/script3.js` | Determina el balance final de la caja familiar. Un resultado positivo indica capacidad de ahorro; un resultado negativo calcula con precisión el dinero faltante. | $$\text{Balance de Dinero} = \text{Presupuesto Familiar} - \text{Total de la Compra}$$ |
| **Proporción e Impacto Presupuestario** | `js/script3.js` | Obtiene el ratio de consumo financiero del hogar, sirviendo como parámetro lógico para activar los colores de alerta visual en el CSS. | $$\text{Porcentaje de Consumo} = \left( \frac{\text{Total de la Compra}}{\text{Presupuesto Familiar}} \right) \times 100$$ |