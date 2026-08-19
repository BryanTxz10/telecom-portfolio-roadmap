---
tags: [skills, telecom]
---
# 1. Skills necesarias

← [[README|Volver al índice]]

Organizadas por eje. Cada skill indica **por qué importa para Pre-Sales / Solution Architect / Platform Engineer**, y a qué curso de GIN/MODS o certificación se conecta ([[04_Certificaciones|ver certificaciones]]).

## 1.1 Networking (base de todo)

- [ ] **Fundamentos IP**: direccionamiento, routing (OSPF/BGP), subnetting, QoS — refuerza `CSC_4CS01 Réseaux IP`.
- [ ] **Diseño de arquitecturas de red a gran escala** (WAN, datacenter, edge) — la competencia transversal #1 de GIN.
- [ ] **Redes móviles 4G/5G y arquitectura core** (EPC, 5GC, network slicing) — `CSC_4GI06`.
- [ ] **SD-WAN y virtualización de red (SDN/NFV)** — `CSC_4GI08`, clave para hablar con clientes sobre automatización de red.

*Por qué importa*: en pre-sales/solution architecture necesitas poder dibujar y defender una arquitectura de red frente a un cliente técnico, no solo operarla.

## 1.2 Cloud & Virtualización

- [ ] **Modelos IaaS/PaaS/SaaS y multi-cloud** (AWS, Azure, GCP, OVHcloud) — `CSC_4GI04 Systèmes cloudifiés`.
- [ ] **Contenedores y orquestación** (Docker, Kubernetes) — base de Platform Engineering.
- [ ] **Infraestructura como código (IaC)**: Terraform, Ansible.
- [ ] **FinOps básico**: comparar costos entre proveedores/arquitecturas — habilidad diferenciadora en pre-sales.

*Por qué importa*: un Solution Architect diseña, un Platform Engineer opera y automatiza, y un Pre-Sales necesita comparar y justificar costos — las tres cosas se apoyan en el mismo stack cloud.

## 1.3 Distribución de contenido y multimedia

- [ ] **Arquitecturas CDN** (caching, edge, anycast) — `CSC_4GI03`, y ya tienes experiencia real (IPTV) que puedes formalizar.
- [ ] **Streaming y QoS de voz/video en tiempo real** (WebRTC, RTP/RTSP) — `CSC_4GI07`, conecta con tu experiencia en videoconferencia Huawei.

## 1.4 Seguridad (transversal, no un módulo aparte)

- [ ] **Criptografía aplicada, autenticación, PKI** — `CSC_4CS02`.
- [ ] **Arquitecturas de seguridad end-to-end, defensa en profundidad, Zero Trust** — `CSC_4CS05`.
- [ ] **Seguridad en cloud e IAM**.

*Por qué importa*: GIN explícitamente enseña seguridad "como componente transversal, no adicional" — un Solution Architect que no puede responder preguntas de seguridad pierde la propuesta.

## 1.5 DevOps / Platform Engineering

- [ ] **CI/CD** (GitLab CI, GitHub Actions).
- [ ] **GitOps** (ArgoCD/FluxCD).
- [ ] **Observabilidad**: Prometheus, Grafana, logging centralizado.
- [ ] **SecDevOps con Kubernetes** — disponible como curso de 3A (GIN-RIO).

## 1.6 Skills de negocio / MODS (el diferenciador de tu perfil)

- [ ] **Lectura técnico-económica de infraestructuras digitales** (costo, valor, competidores) — eje central de MODS.
- [ ] **Construcción y defensa de propuestas de negocio/estrategia**.
- [ ] **Gestión de proyectos con stakeholders reales** (referencia: proyecto MODS con Air France sobre 5G en CDG).
- [ ] **Comunicación técnica a audiencias no técnicas** — la habilidad #1 real de un pre-sales engineer.

## 1.7 Soft skills / idiomas

- [ ] Francés B1 → **objetivo B2 antes de 3A** (necesario para stages y roles en Francia).
- [ ] Inglés C1 → mantener con documentación técnica y certificaciones (todas en inglés).
- [ ] Presentación de arquitecturas ante clientes ficticios (practicar con los propios proyectos del portafolio).

---
**Resumen de prioridad** (para no dispersarte): Networking + Cloud son la base innegociable del año 1. Seguridad y Kubernetes/DevOps se vuelven prioritarios en año 2 (3A), en paralelo con la especialización GIN-RIO. MODS corre en paralelo todo el tiempo — es el que te distingue de un ingeniero puramente técnico.
