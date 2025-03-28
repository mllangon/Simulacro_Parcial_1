# **Simulacro Examen de Redes y Comunicaciones**

---

## **Parte I: Conceptos y Teoría**

---

### **Pregunta 1: Modelos OSI y TCP/IP**

#### **a) Principales diferencias entre modelo OSI y TCP/IP**

- **Número de Capas**  
  - El modelo **OSI** está compuesto por **7 capas** (Física, Enlace de Datos, Red, Transporte, Sesión, Presentación y Aplicación).  
  - El modelo **TCP/IP** agrupa las funciones en **4 capas** (Acceso a Red, Internet, Transporte y Aplicación).
- **Enfoque**  
  - **OSI** tiene un enfoque más **teórico** y pedagógico.  
  - **TCP/IP** surgió de la práctica y se orienta a la **implementación real** en redes.
- **Distribución de Funciones**  
  - **OSI** separa los servicios de presentación y sesión de la capa de aplicación.  
  - **TCP/IP** combina presentación y sesión dentro de la **capa de Aplicación**.

#### **b) Ventajas y limitaciones**

## **Ventajas y Limitaciones de los Modelos OSI y TCP/IP**

### **Modelo OSI**

#### **Ventajas**
1. **Estructura clara**  
   Permite organizar los servicios de red en siete capas específicas, lo que facilita la enseñanza y la comprensión de cada función.

2. **Modularidad**  
   Cada capa se comunica sólo con la capa superior e inferior, resultando más sencillo el diseño, depuración y mantenimiento de redes.

3. **Estándar de referencia**  
   Aunque no se emplee en su totalidad, sirvió de base para desarrollar y estandarizar diversos protocolos, influyendo en la forma en que hoy se conciben las redes.

#### **Limitaciones**
1. **Teórico y complejo**  
   No ha sido adoptado en su totalidad debido a que muchas de sus capas y funciones no son necesarias o se implementan de forma distinta en la práctica.

2. **Escasa adopción total**  
   Las implementaciones completas de OSI no prosperaron comercialmente frente a soluciones más sencillas como TCP/IP.

3. **Más costoso de implementar**  
   Tanto en recursos de software como en hardware, su adopción íntegra demandaba esfuerzos considerables, lo que limitó su popularidad.

---

### **Modelo TCP/IP**

#### **Ventajas**
1. **Práctico y probado**  
   Se ha convertido en el pilar fundamental de Internet, con una adopción masiva y un historial de fiabilidad.

2. **Menos complejo**  
   Agrupa varias funciones (Sesión, Presentación y Aplicación) en una sola capa, simplificando la arquitectura en tan solo cuatro capas.

3. **Robustez y escalabilidad**  
   Demuestra que puede adaptarse al creciente tráfico de la red, integrando nuevas tecnologías y protocolos de manera efectiva.

#### **Limitaciones**
1. **Menor detalle en la división de capas**  
   Al combinar varias funciones en la capa de Aplicación, no existe una separación clara como en OSI.

2. **Carencia de capas intermedias**  
   No posee capas específicas para Presentación o Sesión, dejando estos aspectos a criterio de las aplicaciones.

3. **No fue diseñado con seguridad integrada**  
   En su origen, no contemplaba mecanismos de seguridad avanzados, que se han ido añadiendo con extensiones y protocolos adicionales.


---

### **Pregunta 2: Capa de Transporte**

**Papel de la capa de transporte:**
- Proporciona **entrega confiable extremo a extremo** (end-to-end) entre procesos en diferentes dispositivos.
- Se encarga de la **segmentación** de datos, control de flujo y control de congestión.
- Principales protocolos:  
  - **TCP (Transmission Control Protocol)** para conexión confiable y con control de errores.  
  - **UDP (User Datagram Protocol)** para transmisión rápida sin control de errores.

---

### **Pregunta 3: TCP vs UDP**

#### **TCP**
- **Orientado a conexión** (requiere establecimiento de sesión mediante handshake).  
- **Confiable**, con control de errores y retransmisión de datos perdidos.  
- **Más lento** debido al overhead de confirmación (ACK) y al reordenamiento de segmentos, pero garantiza el orden de llegada.  
- **Ejemplos de uso**: navegación web (HTTP/HTTPS), correo electrónico (SMTP/POP3), transferencia de archivos (FTP).

#### **UDP**
- **Sin conexión** (no requiere handshake previo).  
- **No confiable**, no garantiza la entrega ni el orden de los paquetes.  
- **Rápido** y ligero, ya que no utiliza confirmaciones ni retransmisiones.  
- **Ejemplos de uso**: streaming de video/audio, juegos en línea, VoIP (voz sobre IP).

---

### **Pregunta 4: Protocolos de Transferencia**

1. **Protocolo tradicional:**  
   - **FTP (File Transfer Protocol)**: se utiliza para transferir archivos entre sistemas de manera estándar pero sin cifrado por defecto.

2. **Alternativas:**
   - **SFTP (SSH File Transfer Protocol)**: Proporciona cifrado mediante el protocolo SSH.  
   - **FTPS (FTP Secure)**: Añade cifrado SSL/TLS sobre FTP, ofreciendo seguridad en la transferencia.

---

### **Pregunta 5: DNS**

**Proceso de resolución de nombres:**
1. El cliente (navegador) consulta primero su **caché DNS local** para ver si conoce la IP del dominio.
2. Si no está en caché, la consulta se envía al **servidor DNS configurado** (generalmente del ISP).
3. En caso de que el servidor DNS no tenga la información:  
   1. Se pregunta a uno de los **servidores raíz**.  
   2. El servidor raíz responde con la ubicación del **servidor TLD** (p.ej. `.com`, `.org`).  
   3. Se consulta el **servidor TLD**, que indicará el **servidor autoritativo** del dominio solicitado.
4. El **servidor autoritativo** proporciona la IP del dominio.
5. Se **almacena la respuesta en caché** para futuras consultas.
6. Finalmente, se usa la dirección IP para establecer la conexión con el servidor web.

---

### **Pregunta 6: Comunicación TCP/IP**

**Proceso de comunicación entre dos dispositivos:**
1. **Aplicación**: Se generan los datos a enviar (p.ej. HTTP para solicitar una página web).  
2. **Transporte**: Los datos son segmentados y se añaden los puertos (TCP o UDP).  
3. **Internet**: Se añade la dirección IP de origen y destino para el enrutamiento.  
4. **Acceso a Red**: Se encapsula en tramas (con dirección MAC) y se transmite por el medio físico (cable, Wi-Fi, etc.).

---

# **Parte II: Capa Física y Ejercicios Prácticos**

En este apartado se incluyen ejercicios de cálculo teórico y consideraciones prácticas acerca de la Capa Física, la ubicación de portadoras, la elección de modulación y la eficiencia de un sistema de encapsulamiento.  
Además, se describe **cómo podríamos aproximar y observar** estos fenómenos en **Packet Tracer** (aunque, en varios casos, Packet Tracer no ofrece una simulación a tan bajo nivel como la Capa Física o la modulación, podremos ver la lógica de encapsulación y algunos parámetros de rendimiento con técnicas de simulación de red).

---

## **Pregunta 7: Cálculo de Tasa de Transmisión Máxima (Fórmula de Shannon)**

**Enunciado**  
> Utiliza la fórmula de Shannon,  
> \[
> C = B \times \log_2(1 + \text{SNR})
> \]  
> para un canal con:  
> - Ancho de banda: 500 MHz  
> - SNR: 20 dB  
> Muestra el proceso de conversión del SNR a escala lineal y el cálculo final de \( C \).

### **Explicación Teórica y Resolución Paso a Paso**

1. **Datos iniciales**  
   - Ancho de banda:  
     \[
     B = 500\,\text{MHz} = 500 \times 10^6\,\text{Hz}
     \]
   - Relación señal a ruido (SNR) en dB:  
     \[
     \text{SNR (dB)} = 20\,\text{dB}
     \]

2. **Conversión de SNR (dB) a escala lineal**  
   \[
   \text{SNR}_{\text{lineal}} = 10^{\frac{\text{SNR (dB)}}{10}}
                               = 10^{\frac{20}{10}}
                               = 10^2
                               = 100
   \]

3. **Fórmula de Shannon**  
   \[
   C = B \times \log_2(1 + \text{SNR}_{\text{lineal}})
   \]

4. **Sustitución de valores**  
   \[
   C = 500 \times 10^6 \,\text{Hz} \times \log_2(1 + 100)
   \]
   \[
   1 + 100 = 101 \quad \Rightarrow \quad \log_2(101) \approx 6.6582
   \]
   \[
   C \approx 500 \times 10^6 \times 6.6582
     = 3.3291 \times 10^9 \,\text{bps}
   \]

5. **Resultado**  
   \[
   \boxed{ C \approx 3.33 \,\text{Gbps} }
   \]

### **Cómo observarlo o aproximarlo en Packet Tracer**

- **Limitaciones**: Packet Tracer no simula parámetros de la Capa Física de forma realista (no ofrece ajustes directos de SNR ni ancho de banda en MHz).
- **Posible Aproximación**:
  1. Crear un **escenario simple** con dos PCs conectados por un enlace (por ejemplo, un switch o un router).
  2. Configurar la interfaz con una velocidad fija (ej.: 1 Gbps o 10 Gbps).  
  3. **Simulación de rendimiento**: 
     - Usar la **pestaña de “Simulation”** para observar cómo fluyen los paquetes.  
     - Medir tiempos de envío y recepción de paquetes (aunque esto no refleja directamente la SNR).
  4. **Análisis teórico**: La **velocidad configurada** en la interfaz puede tomarse como \( C \) (velocidad máxima teórica). De esta forma, se puede discutir cómo la SNR y el ancho de banda en el mundo real influyen para que esa velocidad sea posible o no.

En definitiva, en Packet Tracer **no veremos** la conversión de dB a escala lineal o la fórmula de Shannon. Sin embargo, podemos **relacionar** un canal de 1 Gbps con una SNR suficiente para sostener esa tasa de bits en un contexto teórico.

---

## **Pregunta 8: Ubicación de Portadoras para Eficiencia Espectral**

**Enunciado**  
> Un sistema tiene la primera portadora en 1.2 GHz y cada canal tiene un ancho de banda en banda base de 300 MHz. Se pide:  
> a) Frecuencia de la portadora anterior  
> b) Frecuencia de la portadora posterior  
> Justificar los cálculos y explicar la importancia de la ubicación de las portadoras para la eficiencia espectral.

### **Explicación Teórica y Resolución Paso a Paso**

1. **Primera portadora conocida**: 1.2 GHz (1200 MHz).  
2. **Ancho de banda de cada canal**: 300 MHz.

- **Portadora anterior**  
  \[
    1.2\,\text{GHz} - 300\,\text{MHz} = 0.9\,\text{GHz} = 900\,\text{MHz}
  \]

- **Portadora posterior**  
  \[
    1.2\,\text{GHz} + 300\,\text{MHz} = 1.5\,\text{GHz} = 1500\,\text{MHz}
  \]

### **Importancia de la ubicación de las portadoras**

- **Evitar interferencia entre canales**: Al separar cada portadora por su ancho de banda más un margen de protección, reducimos solapamientos que afecten la calidad del servicio.  
- **Eficiencia espectral**: Se trata de aprovechar el espectro disponible de la manera más productiva posible, colocando cada canal de forma que maximice la cantidad de datos transmitidos sin generar interferencias notables.

### **Cómo aproximarlo en Packet Tracer**

- **Limitaciones**: Packet Tracer no permite configurar portadoras a nivel de GHz o canales de 300 MHz como tal; está enfocado en redes de computadoras, no en diseño de radiofrecuencia.  
- **Posible Aproximación**: 
  - En **redes inalámbricas** (Wi-Fi) dentro de Packet Tracer, puedes ver canales (2.4 GHz, 5 GHz).  
  - Ajustar “Channel” en un **router inalámbrico** y observar cómo cada canal se ubica en un rango de frecuencia diferente, evitando solapamientos.  
  - Aunque no podamos definir 1.2 GHz o 300 MHz de forma manual, verás un concepto similar: distintos canales para no interferir.

---

## **Pregunta 9: Identificación de Modulación en Función del BER**

**Enunciado**  
> Dadas las modulaciones BPSK, QPSK, 16-QAM, 64-QAM y 256-QAM, ordénalas de mayor a menor robustez para la misma SNR, justificando con el número de símbolos y sensibilidad al ruido.

### **Explicación Teórica y Resolución**

1. **Relación símbolos y robustez**  
   - **Mayor cantidad de símbolos** → mayor velocidad de datos (eficiencia espectral) pero **menor robustez** ante el ruido.  
   - **Menor cantidad de símbolos** → más distancia entre símbolos en el diagrama de constelación → **mayor robustez**.

2. **Orden de mayor a menor robustez**  
   \[
     \text{BPSK} > \text{QPSK} > \text{16-QAM} > \text{64-QAM} > \text{256-QAM}
   \]

3. **Justificación**  
   - **BPSK** (2 símbolos) es la más robusta, pues la probabilidad de error es menor con la misma SNR.  
   - **QPSK** (4 símbolos) duplica la eficiencia de BPSK pero es algo menos inmune al ruido.  
   - **16-QAM**, **64-QAM** y **256-QAM** incrementan el número de niveles de amplitud y fase, aumentando la velocidad de datos pero reduciendo la distancia entre símbolos.

### **Cómo aproximarlo en Packet Tracer**

- **Packet Tracer no muestra** la modulación a nivel físico (BPSK, QPSK, etc.).  
- Sin embargo, en configuraciones **Wi-Fi** (802.11), internamente se utilizan **modulaciones QAM** de diferente orden según la calidad de la señal.  
  - Por ejemplo, 802.11n o 802.11ac pueden usar 64-QAM o 256-QAM.  
  - Podrías observar que, si la señal es débil, la **velocidad negociada** baja, indicando que, en la vida real, la modulación cambiaría a una más robusta (ej.: 16-QAM) para no perder paquetes.  
- **No hay una opción** directa en Packet Tracer para elegir "BPSK" o "QPSK" en un router Wi-Fi, pero sí puedes monitorear la velocidad y la calidad de la señal en “Simulation” para ver cuándo se producen reenvíos y ajustes automáticos de la PHY.

---

## **Pregunta 10: Eficiencia del Sistema de Encapsulamiento**

**Enunciado**  
> Tenemos un bloque de datos de 1.5 Kbytes en Capa 5. Las capas 4 y 3 añaden cada una 40 bytes de cabecera. La Capa 2 permite tramas de 400 bytes. La Capa 1 añade 1 byte de inicio, 1 byte de parada y 1 byte de CRC por cada 2 bytes de datos. Se pide:  
> a) Tamaño del mensaje tras cabeceras 4 y 3.  
> b) Número de tramas de 400 bytes.  
> c) Sobrecarga de la capa 1 por trama.  
> d) Eficiencia del sistema (datos útiles vs total transmitido).

### **Explicación Teórica y Resolución Paso a Paso**

1. **Tamaño del bloque de datos en Capa 5**  
   \[
   1.5\,\text{Kbytes} = 1.5 \times 1024 = 1536\,\text{bytes}
   \]

2. **Suma de cabeceras Capa 4 y Capa 3**  
   - Cada una añade 40 bytes. Total = 80 bytes adicionales.  
   \[
   \text{Mensaje resultante} = 1536 + 80 = 1616\,\text{bytes}
   \]

3. **Fragmentación en tramas de 400 bytes (Capa 2)**  
   - Se dividen los 1616 bytes en trozos de 400 bytes.  
   \[
   \#\text{tramas} = \left\lceil \frac{1616}{400} \right\rceil = 5\,\text{tramas}
   \]

4. **Sobrecarga Capa 1**  
   - Por cada 2 bytes → se añaden 3 bytes (1 de inicio + 1 de parada + 1 de CRC).  
   - Para **1 trama de 400 bytes**:  
     \[
       \frac{400}{2} = 200\,\text{segmentos}
       \quad \Rightarrow \quad
       200 \times 3 = 600\,\text{bytes de sobrecarga}
     \]
   - Cada trama de 400 bytes se convierte efectivamente en 400 + 600 = 1000 bytes a transmitir en Capa 1.

5. **Eficiencia del sistema**  
   - **Datos útiles totales**: 1536 bytes (el bloque original).  
   - **Total de datos transmitidos**:  
     \[
       5\,\text{tramas} \times 1000\,\text{bytes por trama} = 5000\,\text{bytes}
     \]
   \[
     \text{

