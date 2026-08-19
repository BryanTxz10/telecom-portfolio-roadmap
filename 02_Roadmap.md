---
tags: [roadmap, timeline]
---

# 2. Roadmap progresivo (2026–2028)

← [[README|Volver al índice]]

Alineado a los periodos académicos de Télécom Paris (P1→P4 por año) para que estudies lo mismo dos veces: en clase (teoría) y en tu portafolio (práctica). Cada fase termina en un **proyecto** ([[03_Proyectos_Portafolio]]) y/o una **certificación** ([[04_Certificaciones]]).

## Fase 0 — Ahora - Septiembre 2026 (previo al inicio de clases)

- [ ] Crear el repo "hub" de GitHub (`telecom-portfolio` o similar) con este roadmap como README.
- [ ] Setup de entorno: Git, Docker, VS Code, cuenta AWS/Azure free tier, cuenta OVHcloud (partner de la escuela).
- [ ] Certificación rápida de entrada: **AWS Cloud Practitioner** o **Azure Fundamentals (AZ-900)** — 2-3 semanas de estudio, construye vocabulario cloud antes de que arranque `CSC_4GI04`.
- [ ] Repaso de networking base (subnetting, routing) si hace tiempo que no lo tocas — prepara `CSC_4CS01`.

## Fase 1 — P1 (Sept–Oct 2026): Redes IP + Seguridad cripto

Cursos en paralelo: `CSC_4CS01 Réseaux IP`, `CSC_4CS02 Services de sécurité`.

- [ ] **Proyecto 1**: Home-lab de red simulada (GNS3/EVE-NG o Containerlab) con BGP/OSPF + captura y análisis de tráfico. → [[03_Proyectos_Portafolio#Proyecto 1]]
- [ ] Iniciar preparación **CCNA** (Cisco) — puede tomar 2-3 meses en paralelo con clases; certificar en Fase 2 o 3.
- [ ] Practicar cripto aplicada (TLS, PKI) con un mini-proyecto de configuración de HTTPS/mTLS entre servicios propios.

## Fase 2 — P2 (Nov–Dic 2026): CDN + Cloud nativo

Cursos: `CSC_4GI03 Distribution de contenus`, `CSC_4GI04 Systèmes cloudifiés`.

- [ ] **Proyecto 2**: Mini-CDN con caching multi-región (Docker Compose + Nginx/Varnish) — conecta directo con tu experiencia previa en CDN/IPTV. → [[03_Proyectos_Portafolio#Proyecto 2]]
- [ ] Certificar **AWS Solutions Architect Associate** *o* **Azure AZ-104/AZ-305** (elige uno como tu "cloud principal"; recomendado AWS SAA por reconocimiento internacional, o Azure si apuntas al mercado francés donde Azure/OVHcloud son fuertes).
- [ ] Publicar el primer artefacto "estilo pre-sales": diagrama de arquitectura + comparación de costos (TCO) de 2 proveedores cloud para un caso de uso ficticio.

## Fase 3 — P3 (Ene–Feb 2027): Seguridad avanzada + Redes móviles/IoT

Cursos: `CSC_4CS05 Solutions de sécurité`, `CSC_4GI06 Réseaux mobiles et IoT`.

- [ ] **Proyecto 3**: Laboratorio de red móvil abierta (Open5GS o srsRAN) simulando un core 5G básico + IoT device onboarding. → [[03_Proyectos_Portafolio#Proyecto 3]]
- [ ] Rendir **CCNA** (si no lo hiciste en Fase 1-2).
- [ ] Iniciar **CompTIA Security+** (o (ISC)² SSCP) — cubre lo transversal de seguridad que GIN pide.

## Fase 4 — P4 (Mar–Abr 2027): Multimedia/QoS + cierre 2A

Curso: `CSC_4GI07 Applications et services multimédias`. Automatización de red: `CSC_4GI08`.

- [ ] **Proyecto 4**: Plataforma de videoconferencia/streaming WebRTC con métricas de QoS en tiempo real. → [[03_Proyectos_Portafolio#Proyecto 4]] (vínculo directo con tu experiencia Huawei en videoconferencia).
- [ ] Certificar **Security+** o **SSCP**.
- [ ] Empezar **HashiCorp Terraform Associate** (IaC) — se usará intensivamente en Fase 5-6.

## Fase 5 — Verano 2027 (stage / proyecto de verano)

- [ ] Buscar stage/proyecto aplicado en preventa, arquitectura de soluciones o platform engineering (aprovechar partners de Télécom Paris: OVHcloud, Datadog, STMicroelectronics).
- [ ] **Proyecto 5**: Refactorizar 2-3 proyectos previos usando Terraform (IaC) + CI/CD — convierte "labs" en "infraestructura reproducible", lo que buscan reclutadores de Platform Engineering. → [[03_Proyectos_Portafolio#Proyecto 5]]
- [ ] Certificar **Terraform Associate**.

## Fase 6 — 3A 2027–2028: Especialización GIN-RIO + MODS avanzado

Opción interna GIN-RIO disponible (requiere GIN o RIO): cursos electivos como *Cloud Native Infrastructure with Kubernetes*, *SecDevOps with Kubernetes*, *Network Automation*.

- [ ] **Proyecto 6 (capstone)**: Plataforma cloud-native completa — microservicios + Kubernetes + GitOps (ArgoCD) + observabilidad (Prometheus/Grafana) + seguridad (Zero Trust/mTLS) desplegada con Terraform. → [[03_Proyectos_Portafolio#Proyecto 6]]
- [ ] Certificar **CKA** (Certified Kubernetes Administrator) — el estándar de facto para Platform Engineer.
- [ ] Certificar **CKAD** si el rol se orienta más a desarrollo de plataformas que administración pura.
- [ ] Proyecto de "Projets appliqués" MODS con empresa real → documentarlo como caso de estudio de pre-sales en el portafolio (propuesta técnico-comercial real).
- [ ] Evaluar **TOGAF Foundation** solo si el objetivo se inclina fuerte hacia Solution/Enterprise Architect (no es prioritario antes del final de 3A).

## Fase 7 — Fin de 3A / previo a primer empleo (2028)

- [ ] Consolidar portafolio: 6 proyectos, 6+ certificaciones activas, 1 caso de estudio real (proyecto aplicado con empresa).
- [ ] Preparar 2-3 "solution proposals" completas (arquitectura + costo + pitch) como muestra directa de trabajo de pre-sales/solution architect.
- [ ] Actualizar LinkedIn y GitHub README con métricas concretas de cada proyecto (no solo "hice X", sino "reduje latencia en Y%", "diseñé arquitectura para Z usuarios").

---

## Vista rápida (tabla de seguimiento)

| Fase | Periodo | Curso GIN/MODS | Proyecto | Certificación objetivo |
|---|---|---|---|---|
| 0 | Ago-Sep 2026 | — | Setup + repo | AWS Cloud Practitioner / AZ-900 |
| 1 | P1 2026 | Réseaux IP, Sécurité crypto | Home-lab de red | CCNA (inicio) |
| 2 | P2 2026 | CDN, Cloud nativo | Mini-CDN | AWS SAA / AZ-305 |
| 3 | P3 2027 | Seguridad avanzada, Móvil/IoT | Core 5G lab | CCNA (cierre), Security+ (inicio) |
| 4 | P4 2027 | Multimedia/QoS, Automatización | Plataforma WebRTC | Security+ (cierre) |
| 5 | Verano 2027 | Stage | IaC refactor | Terraform Associate |
| 6 | 3A 2027-28 | GIN-RIO (K8s, SecDevOps) | Capstone cloud-native | CKA (+ CKAD opcional) |
| 7 | Fin 3A 2028 | — | Portafolio consolidado | TOGAF Foundation (opcional) |
