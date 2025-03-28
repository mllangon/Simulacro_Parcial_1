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

**OSI**  
- **Ventajas**  
  - ✓ Modelo detallado y muy estructurado.  
  - ✓ Facilita la enseñanza y el estudio de las redes.  
- **Limitaciones**  
  - ✗ Demasiado complejo de implementar totalmente.  
  - ✗ Nunca se adoptó por completo de forma comercial.

**TCP/IP**  
- **Ventajas**  
  - ✓ Estandarizado en la práctica y base de Internet.  
  - ✓ Robustez y sencillez en entornos reales.  
- **Limitaciones**  
  - ✗ Menos detallado que OSI en cuanto a capas específicas.  
  - ✗ Algunas funcionalidades (p.ej. presentación y sesión) no están claramente definidas.

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

## **Parte II: Cálculos**

---

### **Pregunta 7: Fórmula Shannon**

La **Fórmula de Shannon** establece la capacidad teórica máxima de un canal con un determinado ancho de banda y una relación señal a ruido dada:

\[
C = B \times \log_2(1 + \text{SNR})
\]

- \(C\): Capacidad del canal (bps)  
- \(B\): Ancho de banda (Hz)  
- \(\text{SNR}\): Relación señal/ruido en escala lineal

```plaintext
[Desarrollo de la pregunta, valores y conversiones numéricas, etc.]
