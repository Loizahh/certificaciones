# Módulo 1 — Introducción a la Piratería Ética y las Pruebas de Penetración

**Curso:** Ethical Hacker — Cisco Networking Academy  
**Estado:** Completado ✓  
**Puntuación:** 72%  

---

## 1.1 Piratería ética y pruebas de penetración

- **Hacker ético vs no ético:** la diferencia es la intención y el permiso. Sin permiso escrito, es delito.
- **Alcance (scope):** define qué sistemas se pueden probar y cuáles no. Protege legalmente al evaluador.
- **Por qué hacer pentesting:** implementar defensas no es suficiente, hay que verificar que funcionan. Las pruebas deben repetirse porque las redes cambian.

### Actores de amenazas

| Actor | Motivación | Técnica típica |
|-------|-----------|----------------|
| Crimen organizado | Dinero | Ransomware, robo de datos |
| Hacktivistas | Ideología | Filtración de datos públicos |
| Patrocinados por estado | Espionaje / guerra | APTs, sabotaje de infraestructura |
| Amenaza interna | Engaño, venganza o dinero | Phishing involuntario o sabotaje |

> La amenaza interna puede ser **involuntaria** (empleado engañado) o **maliciosa** (motivada por venganza/dinero).

### Tipos de prueba según el entorno

| Tipo clásico | Nombre moderno | Info proporcionada | Perspectiva |
|---|---|---|---|
| Caja negra | Entorno desconocido | Mínima (IPs/dominios) | Atacante externo |
| Caja blanca | Entorno conocido | Completa (diagramas, credenciales) | Auditoría interna |
| Caja gris | Entorno parcialmente conocido | Parcial | Enfoque híbrido |

### Otros tipos por área técnica

| Área | Qué se prueba |
|------|--------------|
| Infraestructura de red | Switches, routers, firewalls, IPS, servidores AAA |
| Aplicaciones web | SQL injection, XSS, CSRF (ref: OWASP) |
| Nube | Modelo de responsabilidad compartida CSP/cliente |
| Física | Perímetro, accesos, cerraduras, cámaras |
| Ingeniería social | Correos, llamadas, SMS — factor humano |

---

## 1.2 Metodologías de pruebas de penetración

| Metodología | Enfoque principal |
|-------------|-----------------|
| MITRE ATT&CK | TTPs de adversarios reales. Matrices: Enterprise, Cloud, Mobile, ICS |
| OWASP WSTG | Aplicaciones web: XSS, XXE, CSRF, SQL injection |
| NIST SP 800-115 | Estándar general del Dept. de Comercio de EE.UU. |
| OSSTMM | Pruebas repetibles: humana, física, inalámbrica, redes |
| PTES | 7 fases completas |
| ISSAF | Similar a PTES + mantener acceso y cubrir huellas |

**7 fases de PTES (muy preguntadas en examen):**
1. Pre-compromiso
2. Inteligencia
3. Modelado de amenazas
4. Análisis de vulnerabilidades
5. Explotación
6. Post-explotación
7. Informes

---

## 1.3 Construyendo tu propio laboratorio

### Buenas prácticas

| Práctica | Por qué |
|----------|---------|
| Red cerrada | Sin acceso a Internet. Evita afectar sistemas reales |
| Entorno virtualizado | Permite snapshots y restauración rápida |
| Hardware suficiente | Resultados inválidos si el equipo no tiene recursos |
| Plan de recuperación | Siempre snapshot ANTES de iniciar una prueba |

### Kali Linux

- Distribución más usada en pentesting
- Se implementa como VM en VirtualBox (Intel/AMD) o UTM (Mac M1/M2)
- Contiene cientos de herramientas organizadas por categoría
- Al abrir terminal y escribir `pwd` → respuesta: `/home/kali`

---
