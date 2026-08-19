---
tags: [projects, portfolio, github]
---

# 3. Proyectos para el portafolio

← [[README|Volver al índice]]

Cada proyecto = **un repo GitHub independiente**, con su propio README (contexto, arquitectura, diagrama, cómo correrlo, resultados). Aquí solo se resume el objetivo, stack y qué demuestra a un reclutador.

## Proyecto 1 — Home-lab de red multi-sitio simulada

- **Objetivo**: diseñar y simular una WAN de 3-4 sitios con routing dinámico (OSPF/BGP), VLANs, y políticas de QoS.
- **Stack**: GNS3 o Containerlab, FRRouting/Cisco CML, Wireshark para análisis de tráfico.
- **Entregable clave**: diagrama de arquitectura + documento de "diseño de solución" (como si fuera para un cliente) + capturas de tráfico comentadas.
- **Demuestra**: dominio de fundamentos de networking + capacidad de documentar como un Solution Architect, no solo de configurar.
- **Curso relacionado**: `CSC_4CS01 Réseaux IP`.

## Proyecto 2 — Mini-CDN con caching multi-región

- **Objetivo**: replicar (a escala reducida) lo que hiciste en tu experiencia de soporte CDN/IPTV, pero como proyecto propio, documentado y con métricas.
- **Stack**: Docker Compose, Nginx + Varnish (o Redis) como capa de caché, servidores "edge" simulados en distintas regiones (contenedores con latencia artificial vía `tc netem`).
- **Entregable clave**: benchmark de hit-ratio de caché y latencia antes/después, diagrama de arquitectura CDN.
- **Demuestra**: puedes ir de "soporté un sistema CDN" a "diseñé y medí uno" — salto importante para pre-sales/solution architecture.
- **Curso relacionado**: `CSC_4GI03 Distribution de contenus`.

## Proyecto 3 — Laboratorio de core 5G / IoT

- **Objetivo**: desplegar un core de red móvil open-source y conectar dispositivos IoT simulados.
- **Stack**: Open5GS o srsRAN (core 5G), UERANSIM (gNB/UE simulados), MQTT para telemetría IoT.
- **Entregable clave**: diagrama de arquitectura del core 5G + demo de onboarding de un "dispositivo" + análisis de casos de uso (network slicing explicado a nivel de negocio, ideal para MODS).
- **Demuestra**: comprensión de redes móviles de nueva generación, tema donde pocos candidatos junior tienen algo tangible que mostrar.
- **Curso relacionado**: `CSC_4GI06 Réseaux mobiles et IoT`.

## Proyecto 4 — Plataforma de videoconferencia/streaming con métricas QoS

- **Objetivo**: construir una app de videollamada/streaming básica (WebRTC) e instrumentarla con métricas de calidad (jitter, packet loss, bitrate adaptativo).
- **Stack**: WebRTC (mediasoup o Janus como SFU), Node.js/Python backend, Grafana para visualizar métricas en tiempo real.
- **Entregable clave**: dashboard de QoS en vivo + informe de "troubleshooting" simulando un problema real de calidad de llamada.
- **Demuestra**: conecta directamente con tu experiencia real en preventa de videoconferencia Huawei — de "vendí/soporté esto" a "lo construí y lo entiendo a fondo".
- **Curso relacionado**: `CSC_4GI07 Applications et services multimédias`.

## Proyecto 5 — Infraestructura como código para los proyectos previos

- **Objetivo**: tomar 2-3 de los labs anteriores y reescribir su despliegue en Terraform + Ansible, con pipeline CI/CD.
- **Stack**: Terraform, Ansible, GitHub Actions o GitLab CI, un proveedor cloud real (AWS/Azure/OVHcloud) para al menos una parte desplegada de verdad (no solo local).
- **Entregable clave**: repo con módulos Terraform reutilizables + pipeline que despliega/destruye el entorno automáticamente + documentación de costos estimados.
- **Demuestra**: la habilidad núcleo de Platform Engineering — reproducibilidad e infraestructura versionada, no solo "lo hice funcionar una vez".
- **Curso relacionado**: `CSC_4GI08 Virtualisation et automatisation des réseaux`.

## Proyecto 6 (Capstone, 3A) — Plataforma cloud-native completa

- **Objetivo**: sistema de microservicios en Kubernetes con GitOps, observabilidad y seguridad Zero Trust — el proyecto "bandera" del portafolio.
- **Stack**: Kubernetes (kind/k3d local o cluster cloud real), Helm, ArgoCD (GitOps), Prometheus + Grafana (observabilidad), mTLS/Service Mesh (Istio o Linkerd) para Zero Trust, Terraform para provisionar el cluster.
- **Entregable clave**: arquitectura completa documentada + demo en video corto + informe de "post-mortem" simulando un incidente y cómo se detectó/resolvió con las herramientas de observabilidad.
- **Demuestra**: cierra el círculo Networking → Cloud → Seguridad → Automatización, cubriendo simultáneamente Platform Engineering (operación) y Solution Architecture (diseño).
- **Curso relacionado**: opción 3A GIN-RIO (Cloud Native Infrastructure with Kubernetes, SecDevOps with Kubernetes).

## Proyecto transversal — "Solution Proposal Kit" (pre-sales real)

Este no es un proyecto técnico sino el que más pesa para **Pre-Sales Engineer** específicamente:

- **Objetivo**: crear una plantilla reutilizable de propuesta técnico-comercial (arquitectura + TCO + riesgos + cronograma) y aplicarla a 2-3 de los proyectos anteriores como si fueran pitches a un cliente ficticio.
- **Stack**: diagrams.py o draw.io para arquitecturas, hoja de cálculo para TCO/comparación de proveedores, documento tipo RFP response.
- **Entregable clave**: 2-3 "solution proposals" completas en PDF, en inglés y francés (practica idioma + tema profesional a la vez).
- **Demuestra**: es literalmente el artefacto de trabajo diario de un Pre-Sales/Solution Architect — pocos candidatos técnicos lo tienen en su portafolio.

---

## Cómo estructurar el repo hub en GitHub

```text
telecom-portfolio/
├── README.md              ← este roadmap (o versión resumida con links)
├── 01-network-multisite-lab/    (submódulo o link a repo aparte)
├── 02-mini-cdn/
├── 03-5g-iot-lab/
├── 04-webrtc-qos-platform/
├── 05-iac-refactor/
├── 06-cloudnative-capstone/
└── solution-proposals/     ← PDFs/casos de negocio
```

Cada carpeta puede ser un **git submodule** apuntando a su propio repo, o simplemente un link en el README si prefieres mantener cada proyecto totalmente independiente (recomendado para mostrar repos individuales bien cuidados en tu perfil de GitHub).
