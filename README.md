# Simulacro Examen de Redes y Comunicaciones

## Parte I: Conceptos y Teoría

### Pregunta 1: Modelos OSI y TCP/IP

#### a) Principales diferencias entre modelo OSI y TCP/IP:
- OSI tiene 7 capas vs 4 capas de TCP/IP
- OSI es más teórico, TCP/IP más práctico
- OSI separa servicios, presentación y aplicación, TCP/IP los combina

#### b) Ventajas y limitaciones:
**OSI:**
- ✓ Modelo detallado y estructurado
- ✗ Complejo de implementar

**TCP/IP:**
- ✓ Probado y funcional
- ✗ Menos detallado que OSI

### Pregunta 2: Capa de Transporte
**Papel de la capa de transporte:**
- Garantiza entrega confiable extremo a extremo
- Principales protocolos: TCP y UDP
- Control de flujo y congestión

### Pregunta 3: TCP vs UDP

#### TCP:
- Orientado a conexión
- Confiable, control de errores
- Más lento pero ordenado
- Ejemplo: Web, email

#### UDP:
- Sin conexión
- No confiable
- Rápido, sin orden
- Ejemplo: Streaming, juegos

### Pregunta 4: Protocolos de Transferencia
a) Protocolo tradicional: FTP

b) Alternativas:
- SFTP: FTP con cifrado SSH
- FTPS: FTP con SSL/TLS

### Pregunta 5: DNS
**Proceso DNS:**
1. Cliente consulta DNS local
2. Si no está en caché, consulta servidor raíz
3. Servidor raíz indica TLD
4. TLD indica servidor autoritativo
5. Se obtiene IP final

### Pregunta 6: Comunicación TCP/IP
**Proceso de comunicación:**
1. Aplicación: genera datos
2. Transporte: segmentación
3. Internet: enrutamiento
4. Acceso a Red: transmisión física

## Parte II: Cálculos

### Pregunta 7: Fórmula Shannon
