---
tags: [projects, portfolio, gin, mods, rms]
---

# 5. Proyectos GIN × MODS respaldados por el equipo RMS

← [[README|Volver al índice]] · Complementa [[03_Proyectos_Portafolio|3. Proyectos para el portafolio]]

Este documento recoge el trabajo en tres fases pedido en septiembre de 2026: (1) leer la colección RMS de Télécom Paris en HAL, investigar el mercado y proponer 10 proyectos que combinen GIN y MODS; (2) revisarlos con criterios explícitos; (3) elegir 3 y dejarlos listos para empezar en repos propios.

Supuestos de trabajo: una sola persona que **recién empieza** en IA y DevOps, ≈10–12 h por semana, portátil normal (sin GPU ni hardware especial), solo datos públicos y gratuitos. La experiencia previa (redes, cloud, NOC de streaming, base 5G) sirve de apoyo, no como tema.

## Fase 1.1 — Qué dice el Excel RMS (813 trabajos)

Fuente: API pública de HAL, colección `collCode_s:RMS`, consultada el 13/09/2026. El Excel trae un tema principal por trabajo y un puntaje de "afinidad".

**Advertencia sobre el Excel.** El puntaje de afinidad premia Zero Trust, core 5G, slicing, NFV y edge, es decir, tu experiencia previa. Para no sesgar los temas hacia ella, reclasifiqué los 813 registros con cuatro lentes (infraestructura, datos, economía, estrategia) más sostenibilidad, buscando palabras clave en título, keywords y resumen. Es una clasificación orientativa: un trabajo puede caer en varias lentes.

| Lente | Trabajos | De ellos 2018+ | Líneas representativas |
| --- | --- | --- | --- |
| Infraestructura | 293 | 109 | NFV y software switches, orquestación de VNF, testbeds Kubernetes (Arena, 2026), Segment Routing y service chaining, BGP/LISP, caching CDN/ICN, redes ópticas (antiguas) |
| Datos | 147 | 59 | Telemetría con ML en routers (ADT 2023, DESTIN 2021), anomalías BGP (2018), predicción de tráfico (2021, 2025), benchmarks de flexibilidad eléctrica para ML (2020) |
| Economía | 106 | 39 | Co-inversión en edge computing con juegos coalicionales (2023–2026), subastas de espectro con MCTS (2022–2025), mercados locales de energía (2017–2020), pricing y reparto de ingresos en cloud (2010–2014), cost-aware caching (2014–2015) |
| Estrategia y regulación | 152 | 54 | Débitos 5G para ARCEP (2020), efectos ambientales de la 5G (2024), resiliencia y semiconductores (2024), gobernanza digital (2010–2011), constelaciones de satélites (2024), IA en la UE (2024) |
| Sostenibilidad | 116 | 54 | Consumo energético 5G en Francia con datos reales (2023–2026), green networking en backbone IP (2010–2014), demand response y smart grids |

Cruces útiles: infraestructura ∧ economía = 46 trabajos; infraestructura ∧ datos = 56; y solo **14** combinan infraestructura (o sostenibilidad) + economía (o estrategia) + datos.

Lectura:

1. **El corpus es mayormente histórico.** 650 de 813 trabajos son anteriores a 2020. Las líneas vivas (2024+) son energía y sostenibilidad, co-inversión en edge, testbeds cloud-native, IA para predicción de tráfico, NTN/UAV y probabilidad teórica.
2. **La economía del equipo es teoría de juegos, no ingeniería con datos públicos.** Co-inversión, subastas y mercados de energía están escritos como modelos, no como herramientas. Ese hueco (14 trabajos puente) es justo el espacio de un portafolio GIN + MODS de ingeniería.
3. **Los temas más grandes (radio móvil, 235; geometría estocástica, 45) son de investigación** y cercanos a tu base 5G. Los uso poco a propósito.
4. **Lo que sí se transfiere bien a proyectos de ingeniería**: el pricing y la colocación en cloud (2010–2014), el cost-aware caching, las mediciones de energía con datos reales, la telemetría con ML y los testbeds Kubernetes.

## Fase 1.2 — Qué piden las empresas (Francia y Europa, 2026)

Señales principales (fuentes al pie de la sección):

- **Volumen.** Apec prevé 61 160 contrataciones de *cadres informaticiens* en 2026 (+4 % frente a 2025), el perfil más buscado del sector privado, empujado por transformación digital, ciberseguridad e IA. La mitad de los cadres ya usa herramientas de IA cada semana.
- **Stack DevOps/Cloud recurrente en ofertas francesas**: Kubernetes, Docker, GitLab CI o GitHub Actions, Terraform/Ansible, Python, Linux, AWS/Azure, Prometheus/Grafana y seguridad DevOps. A un junior se le pide sobre todo Docker, Kubernetes, Terraform y pipelines CI.
- **Costos de cloud e IA (FinOps).** Según el State of FinOps 2026, el 98 % de los equipos ya gestiona costos de IA (63 % en 2025, 31 % en 2024). Reducir desperdicio sigue siendo la prioridad actual n.º 1. La sostenibilidad crece pero sigue siendo baja prioridad; donde más pesa es en Europa.
- **IA aplicada: el cuello de botella está en desplegar y operar.** Las ofertas de AI engineering en Europa suben con fuerza y la escasez más aguda es de MLOps: pipelines fiables, calidad de datos y endpoints seguros, más que modelos nuevos (fuente secundaria: PredictLeads, Tribe).
- **La regulación genera trabajo de ingeniería**:
  - *EU Data Act*: desde el 12/01/2027 los proveedores cloud ya no pueden cobrar cargos por cambio de proveedor (*switching*). La portabilidad pasa a ser un requisito de arquitectura.
  - *NIS2*: en Francia la ley de transposición sigue en trámite (Assemblée nationale, otoño 2026), pero la ANSSI publicó el referencial ReCyF el 17/03/2026; se estiman unas 15 000 entidades afectadas.
  - *Cyber Resilience Act*: desde el 11/09/2026 los fabricantes deben notificar vulnerabilidades explotadas activamente. El SBOM legible por máquina es obligatorio desde diciembre de 2027.
  - *Soberanía*: la oferta cualificada SecNumCloud crece (por ejemplo S3NS, cualificada en diciembre de 2025).
- **Sostenibilidad digital con datos oficiales**: el RGESN (Arcep/Arcom, 2024) tiene 78 criterios de ecodiseño, obligatorios para servicios públicos. La encuesta anual de la Arcep a operadores de data centers muestra que su consumo eléctrico sube.

**Consecuencia para el portafolio.** Un reclutador de ingeniería en Francia busca pruebas de cuatro cosas: (1) que despliegas y automatizas (contenedores, CI/CD, IaC, Kubernetes); (2) que conviertes datos en una decisión con números (costo, riesgo, carbono); (3) que entiendes el contexto regulatorio europeo; (4) que sabes operar IA, no solo entrenarla. Los proyectos de abajo buscan cubrir esas cuatro cosas a la vez.

Fuentes: [Apec — cadres más reclutados en 2026](https://www.apec.fr/tendances-emploi-cadre/recrutement-et-pratiques-rh/quels-sont-les-cadres-qui-seront-les-plus-recrutes-en-2026-.html) · [Apec — Les cadres et l'IA 2026](https://corporate.apec.fr/home/nos-etudes/toutes-nos-etudes/les-cadres-et-l-ia-2026.html) · [Indeed — ofertas DevOps Kubernetes Île-de-France](https://fr.indeed.com/q-ing%C3%A9nieur-devops-kubernetes-l-%C3%8Ele-de-france-emplois.html) · [FinOps Foundation — State of FinOps 2026](https://data.finops.org/) · [Linux Foundation — nota de prensa State of FinOps](https://www.linuxfoundation.org/press/state-of-finops-survey-ai-value-and-skills-top-priorities-as-finops-matures-across-technology-value-98-manage-ai-90-saas-64-licensing-48-data-center) · [PredictLeads — AI engineering jobs Europe 2026](https://predictleads.com/blog/ai-engineering-jobs-in-europe-2026-hiring-report/) · [Alston & Bird — Data Act switching](https://www.alston.com/en/insights/publications/2025/09/eu-data-act-switching-requirements-cloud-services) · [Legiscope — transposición NIS2 en Francia](https://www.legiscope.com/blog/transposition-nis2-france.html) · [Comisión Europea — Cyber Resilience Act](https://digital-strategy.ec.europa.eu/en/policies/cyber-resilience-act) · [S3NS — cualificación SecNumCloud](https://www.s3ns.io/actualite/s3ns-annonce-qualification-sec-num-cloud) · [Arcep — RGESN](https://www.arcep.fr/mes-demarches-et-services/entreprises/fiches-pratiques/referentiel-general-ecoconception-services-numeriques.html) · [Arcep — Enquête "Pour un numérique soutenable" 2026](https://www.arcep.fr/cartes-et-donnees/nos-publications-chiffrees/impact-environnemental/enquete-annuelle-pour-un-numerique-soutenable-edition-2026.html)

### Fuentes de datos públicas y gratuitas

La columna "Probado" indica si la fuente respondió desde el entorno donde se construyeron los repos (septiembre de 2026). Un "no" se debe a la política de red de ese entorno, no a la fuente. Desde un portátil normal o desde GitHub Actions son accesibles.

| Tema | Fuente | Qué aporta | Clave | Probado |
| --- | --- | --- | --- | --- |
| Precios cloud | [AWS Price List Bulk API](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/using-the-aws-price-list-bulk-api.html) | Precio on-demand por instancia y región (CSV oficial) | No | Sí |
| Precios cloud | [Azure Retail Prices API](https://learn.microsoft.com/en-us/rest/api/cost-management/retail-prices/azure-retail-prices) | Precio por SKU y región (JSON paginado) | No | No |
| Energía cloud | [Cloud Carbon Footprint coefficients](https://github.com/cloud-carbon-footprint/cloud-carbon-coefficients) | Vatios mín./máx. por vCPU según microarquitectura | No | Sí |
| Carbono de la red | [Our World in Data — energy-data](https://github.com/owid/energy-data) (basado en Ember) | gCO₂/kWh de la electricidad por país y año | No | Sí |
| Carbono de la red | [RTE éCO2mix en ODRÉ](https://odre.opendatasoft.com/explore/dataset/eco2mix-national-tr/) | gCO₂/kWh en Francia cada 15 min | No (cuota mensual) | No |
| Mercado eléctrico | [ENTSO-E Transparency Platform](https://transparency.entsoe.eu/) | Precios day-ahead y generación en Europa | Token gratuito | No |
| Trazas de carga | [Azure Public Dataset](https://github.com/Azure/AzurePublicDataset) | Trazas reales de VM, Functions y de inferencia LLM (2023, 2024) | No | Sí |
| Vulnerabilidades | [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) (espejo oficial [cisagov/kev-data](https://github.com/cisagov/kev-data)) | CVE explotadas activamente | No | Sí (espejo) |
| Vulnerabilidades | [FIRST EPSS](https://www.first.org/epss/api) | Probabilidad de explotación en 30 días | No | No |
| Vulnerabilidades | [OSV.dev](https://google.github.io/osv.dev/) | Vulnerabilidades por paquete (API y dumps) | No | Sí (dumps) |
| Vulnerabilidades | [CVE List V5](https://github.com/CVEProject/cvelistV5) y [CISA Vulnrichment](https://github.com/cisagov/vulnrichment) | Registro CVE, CVSS y decisiones SSVC | No | Sí |
| Vulnerabilidades | [NVD API 2.0](https://nvd.nist.gov/developers/vulnerabilities) | CVSS y CPE | Opcional | No |
| Enrutamiento | [RIPEstat Data API](https://stat.ripe.net/docs/02.data-api/) | Prefijos, vecinos y visibilidad por AS y país | No | No |
| Interconexión | [PeeringDB API](https://www.peeringdb.com/apidocs/) | IXPs, miembros, capacidad de puertos | Opcional | No |
| Topología AS | [CAIDA AS Relationships](https://www.caida.org/catalog/datasets/as-relationships/) | Relaciones cliente-proveedor y peering | No | No |
| Telecom Francia | [Arcep en data.gouv.fr — déploiements FttH](https://www.data.gouv.fr/datasets/le-marche-du-haut-et-tres-haut-debit-fixe-deploiements) | Despliegue FttH por municipio, Mon réseau mobile, etc. | No | No |
| Radio Francia | [ANFR open data](https://data.anfr.fr/) | Sitios y antenas por tecnología | No | No |
| Velocidad medida | [Ookla Open Data](https://github.com/teamookla/ookla-open-data) | Velocidades fijas y móviles por tesela (Parquet en S3) | No | Sí |
| Popularidad web | [Wikimedia pageviews](https://dumps.wikimedia.org/other/pageviews/) | Vistas por página y hora | No | No |

## Fase 1.3 — Diez propuestas

Cada propuesta tiene un lado técnico (GIN), un lado económico o estratégico (MODS) y un componente de IA o DevOps que se aprende haciéndolo. Los tiempos asumen ≈10–12 h/semana y cero experiencia previa en la herramienta.

### P1 — `cloud-cost-carbon`: brújula de costo y carbono cloud (FinOps + GreenOps)

- **Problema de empresa.** Una ETI que migra o renegocia su nube no sabe qué combinación de proveedor, región e instancia minimiza costo y huella de carbono, ni cuánto le costaría cambiar de proveedor ahora que el Data Act elimina los cargos por cambio.
- **Qué se construye.** Una ingesta de catálogos oficiales de precios (AWS, luego Azure), de coeficientes de energía por microarquitectura y de la intensidad de carbono de la red por país. Encima, un modelo transparente de €/mes y kgCO₂e/mes por carga de trabajo y un comparador (CLI, luego API y dashboard). Como pieza econométrica, una regresión hedónica de precios que mide la prima por región y proveedor.
- **Cursos.** GIN: CSC_4GI04 Systèmes cloudifiés, CSC_4GI08 Cloud Automation & DevOps. MODS: ECO_4MO10 Microeconomics & IO (pricing, costos de cambio), ECO_4MO21 Economics of sustainable development and IT, ECO_4MO11 Econometrics (regresión hedónica), IME_4MO22 (estrategia de soberanía).
- **Respaldo RMS.** [Towards Market-oriented Clouds (2010)](https://telecom-paris.hal.science/hal-02278648v1) · [Pay-as-you-Book pricing (2012)](https://imt.hal.science/hal-01326274v1) · [CompatibleOne: Cloud as a Commodity (2014)](https://imt.hal.science/hal-01326269v1) · [Placement for cost and recovery in multi-cloud (2013)](https://imt.hal.science/hal-01326271v1) · [Federation and Revenue Sharing in Cloud (2014)](https://hal.science/hal-02358694v1) · [5G-EcoSim, estimación energética con datos reales (2026)](https://hal.science/hal-05512984v1)
- **Datos.** AWS Price List, Azure Retail Prices, Cloud Carbon Footprint, OWID/Ember y RTE éCO2mix.
- **IA/DevOps.** Empaquetado Python, pytest, GitHub Actions (CI y snapshot programado), Docker, FastAPI, Terraform (estimar el costo de un `terraform plan`), statsmodels/scikit-learn.
- **Tiempo.** 5 semanas.

### P2 — `carbon-aware-scheduler`: planificador de tareas batch según carbono y precio

- **Problema de empresa.** Los jobs flexibles (ETL, entrenamiento, CI nocturno) corren a hora fija aunque en Francia la intensidad de carbono y el precio spot varían mucho dentro del día.
- **Qué se construye.** Una ingesta de éCO2mix y de precios day-ahead, un pronóstico a 24 h (primero un baseline estacional, luego gradient boosting) y un planificador que elige la ventana más barata o más limpia dentro de un deadline. Se despliega como CronJob en kind, con métricas en Prometheus.
- **Cursos.** GIN: CSC_4GI04, CSC_4GI08. MODS: ECO_4MO21, ECO_4MO11 (series temporales), ECO_4MO14 Financial Markets (mercado day-ahead, volatilidad).
- **Respaldo RMS.** [Sensitivity to forecast errors in storage arbitrage (2019)](https://telecom-paris.hal.science/hal-02163114v2) · [Benchmarks for Grid Flexibility Prediction (2020)](https://hal.science/hal-02547982v1) · [Demand Response for Capacity Markets (2015)](https://hal.science/hal-01225293v1) · [Misalignments in demand response programs (2020)](https://hal.science/hal-02883435v2) · [The Long Road to Sobriety (2023)](https://telecom-paris.hal.science/hal-04082598v1)
- **Datos.** RTE éCO2mix (ODRÉ) y ENTSO-E (token gratuito).
- **IA/DevOps.** Kubernetes (kind), Helm, Prometheus, scikit-learn/LightGBM, MLflow.
- **Tiempo.** 6 semanas.

### P3 — `llm-capacity-planner`: planificador de capacidad para inferencia LLM (MLOps/SRE)

- **Problema de empresa.** Quien sirve modelos de IA paga GPUs por hora. Si sobre-aprovisiona, quema presupuesto; si se queda corto, rompe el SLO de latencia. Es la primera prioridad FinOps de 2026.
- **Qué se construye.** Una ingesta de trazas reales de inferencia LLM de Azure (2023 y una semana de 2024: timestamp, tokens de entrada y de salida), un pronóstico de demanda por minuto, un simulador de capacidad (réplicas → latencia p95) y una comparación entre autoscaling reactivo y predictivo en €/día y en minutos con el SLO violado. Al final, una demo en kind con un servicio simulado y k6 reproduciendo la traza.
- **Cursos.** GIN: CSC_4GI04, CSC_4GI08, CSC_4CS01 Réseaux IP (colas y latencia). MODS: ECO_4MO11 (series temporales y evaluación de pronósticos), ECO_4MO10 (decisión tipo newsvendor, compromiso reservado frente a on-demand), IME_4MO22.
- **Respaldo RMS.** [Dynamic Resource Allocation under Time-variant Requests (2011)](https://imt.hal.science/hal-01326287v1) · [Resource over-Reservation and Dropping Policies (2011)](https://telecom-paris.hal.science/hal-02278569v1) · [Pay-as-you-Book pricing (2012)](https://imt.hal.science/hal-01326274v1) · [Traffic Prediction with AI and Self-Controlled Components (2025)](https://hal.science/hal-05172767v1) · [Arena: Kubernetes-based testbed (2026)](https://inria.hal.science/hal-05517164v2) · [Non-invasive performance prediction of softwarized services (2024)](https://hal.science/hal-04322420v1)
- **Datos.** Azure Public Dataset (trazas LLM 2023 y 2024, CC-BY) y precios públicos de instancias GPU.
- **IA/DevOps.** pandas, statsmodels, scikit-learn/LightGBM, MLflow, Docker, kind con HPA, k6, Prometheus/Grafana.
- **Tiempo.** 6 semanas.

### P4 — `vuln-prioritizer`: priorización de vulnerabilidades con presupuesto (DevSecOps)

- **Problema de empresa.** Un equipo de plataforma recibe cientos de CVE por sus imágenes de contenedor y no puede parchearlas todas. NIS2 (ReCyF) y el CRA exigen una gestión de vulnerabilidades demostrable. Con X horas-ingeniero, ¿qué se parchea primero?
- **Qué se construye.** SBOM (Syft) y escaneo (Trivy) de imágenes públicas en CI. Enriquecimiento con KEV, EPSS, OSV y CVSS. Un modelo de riesgo esperado (probabilidad de explotación × impacto) y una optimización del parcheo bajo presupuesto (mochila 0/1), comparada contra la regla habitual "parchear por CVSS".
- **Cursos.** GIN: CSC_4CS05 Solutions de sécurité, CSC_4GI08, CSC_4CS02 Cryptologie (firma de imágenes y cadena de suministro, como extensión). MODS: ECO_4MO10 (economía de la seguridad, modelo Gordon-Loeb), IME_4MO22 (riesgo y cumplimiento como decisión estratégica), ECO_4MO12 Data analysis in economics.
- **Respaldo RMS.** [SINARI: security analysis and risk assessment (2013)](https://hal.science/hal-00991386v1) · [Risk analysis of ITS communication architecture (2012)](https://imt.hal.science/hal-00814320v1) · [MAGMA: malware traffic classifier (2016)](https://imt.hal.science/hal-01351259v1) · [Macroscopic View of Malware in Home Networks (2015)](https://imt.hal.science/hal-01351253v1) · [Digitalisation as threat to resilience (2024)](https://hal.science/hal-04926341v1) · [SigN: anomaly detection at the cellular edge (2025)](https://hal.science/hal-04920040v1)
- **Datos.** CISA KEV, FIRST EPSS, OSV.dev, CVE List V5 / Vulnrichment y NVD.
- **IA/DevOps.** Trivy, Syft, escaneo de seguridad en GitHub Actions (SARIF), Docker, pandas, PuLP (optimización), scikit-learn (extensión).
- **Tiempo.** 5 semanas.

### P5 — `fr-internet-dependency`: observatorio de dependencia de Internet en Francia

- **Problema de empresa.** Operadores, hosters y la ANSSI (NIS2) necesitan saber cuán concentrada está la conectividad de las redes francesas en pocos proveedores de tránsito e IXPs, y detectar eventos que la degradan.
- **Qué se construye.** Un pipeline sobre RIPEstat, PeeringDB y CAIDA; índices de concentración (HHI, CR4) por upstream e IXP; un dashboard; y un detector de anomalías de visibilidad BGP.
- **Cursos.** GIN: CSC_4CS01 Réseaux IP, CSC_4CS05, CSC_4GI03 Distribution de contenu. MODS: ECO_4MO10 (concentración y poder de mercado), IME_4MO22 (soberanía y dependencia), ECO_4MO12.
- **Respaldo RMS.** [Kumori: steering cloud traffic at IXPs for resiliency (2016)](https://telecom-paris.hal.science/hal-02287812v1) · [Inter-domain stability for BGP dynamics (2018)](https://imt.hal.science/hal-01712226v1) · [Unsupervised real-time detection of BGP anomalies (2018)](https://telecom-paris.hal.science/hal-02412401v1) · [On multi-exit routings and AS relationships (2013)](https://hal.science/hal-01698837v1) · [Ressources numérisées : nouveau féodalisme (2011)](https://telecom-paris.hal.science/hal-02286240v1)
- **Datos.** RIPEstat, PeeringDB, CAIDA AS Relationships y RIPE RIS.
- **IA/DevOps.** networkx, scikit-learn (IsolationForest), Docker Compose, Grafana o Streamlit, cron en GitHub Actions.
- **Tiempo.** 6 semanas.

### P6 — `ftth-rollout-economics`: economía del despliegue de fibra en Francia

- **Problema de empresa.** Operadores, inversores y colectividades necesitan saber dónde falta fibra, qué explica el retraso y cuánto costaría cerrar la brecha antes del cierre del cobre.
- **Qué se construye.** Una ingesta de despliegues FttH por municipio (Arcep) y de variables INSEE, un modelo econométrico de panel más gradient boosting con SHAP, un modelo de CAPEX por toma según densidad y un dashboard.
- **Cursos.** GIN: CSC_4CS01 (redes de acceso), CSC_4GI03. MODS: ECO_4MO11, ECO_4MO12, ECO_4MO10 (co-inversión y competencia), HSS_4MO18 (desigualdad territorial).
- **Respaldo RMS.** [Co-investment under uncertainty (2025)](https://hal.science/hal-05063036v2) · [Coalitional approach to coinvestment (2023)](https://hal.science/hal-04492328v1) · [Translucent Network Design from a CapEx/OpEx Perspective (2011)](https://hal.science/hal-01326198v1) · [Toward a new Telco role in content distribution (2012)](https://hal.science/hal-01119048v1) · [Performances 5G : zones rurales et urbaines (2021)](https://telecom-paris.hal.science/hal-03367918v1)
- **Datos.** Arcep en data.gouv.fr, INSEE, IGN Admin Express y Ookla Open Data.
- **IA/DevOps.** geopandas, statsmodels/linearmodels, scikit-learn + SHAP, DuckDB, Streamlit y CI.
- **Tiempo.** 6 semanas.

### P7 — `cdn-cache-economics`: simulador de caché CDN consciente del costo

- **Problema de empresa.** Un proveedor de contenidos o un ISP decide cuánto almacenamiento de caché poner en el borde frente a pagar tránsito.
- **Qué se construye.** Una ingesta de popularidad (Wikimedia pageviews), un simulador de políticas LRU/LFU/cost-aware, un modelo de costo de tránsito frente a almacenamiento, predicción de popularidad para prefetch y una demo con nginx en Docker Compose.
- **Cursos.** GIN: CSC_4GI03, CSC_4GI07 Applications et services multimédia. MODS: ECO_4MO10 (organización industrial de CDNs, peering frente a tránsito).
- **Respaldo RMS.** [Cost-aware caching: caching more for less (2015)](https://imt.hal.science/hal-01279355v1) · [Cost-aware caching in ICN (2014)](https://hal.science/hal-01109072v1) · [Cacheable traffic in ISP access networks (2014)](https://inria.hal.science/hal-01137871v1) · [Netflix catalog dynamics and caching (2013)](https://imt.hal.science/hal-00858194v1) · [Improving content delivery through coalitions (2014)](https://hal.science/hal-01119041v1)
- **Datos.** Wikimedia pageviews y PeeringDB. Los precios de tránsito no son públicos: habría que usar supuestos.
- **IA/DevOps.** Docker Compose, nginx, scikit-learn.
- **Tiempo.** 5 semanas.

### P8 — `ran-energy-estimator`: energía y carbono de la red móvil por departamento

- **Problema de empresa.** Operadores (CSRD, encuesta Arcep) y colectividades quieren estimar el consumo de la red móvil en su territorio.
- **Qué se construye.** Una ingesta ANFR de sitios por tecnología, modelos de potencia por estación base tomados de la literatura RMS, energía por departamento y carbono con RTE.
- **Cursos.** GIN: CSC_4GI06 Réseaux mobiles et IoT. MODS: ECO_4MO21.
- **Respaldo RMS.** [5G-EcoSim (2026)](https://hal.science/hal-05512984v1) · [Consommation énergétique de la 5G en France (2025)](https://hal.science/hal-05034070v1) · [The Long Road to Sobriety (2023)](https://telecom-paris.hal.science/hal-04082598v1) · [Carbon Footprint of Urban 5G Traffic in Lyon (2026)](https://hal.science/hal-05559389v1)
- **Datos.** ANFR, Arcep "Mon réseau mobile" y RTE éCO2mix.
- **IA/DevOps.** pandas, geopandas y CI.
- **Tiempo.** 5–6 semanas.

### P9 — `netops-copilot`: asistente LLM para configuraciones de red con validación automática

- **Problema de empresa.** Los errores de configuración causan incidentes y escribir o validar configs consume horas de ingeniero.
- **Qué se construye.** Un RAG sobre RFCs y la documentación de FRR, generación de configs para topologías pequeñas y validación con Batfish y Containerlab dentro de CI.
- **Cursos.** GIN: CSC_4CS01, CSC_4GI08. MODS: IME_4MO22 (ROI de la automatización).
- **Respaldo RMS.** [Towards network automation: planning and monitoring (2022)](https://theses.hal.science/tel-04842213v1) · [ADT: AI-Driven network Telemetry (2023)](https://telecom-paris.hal.science/hal-04281988v1) · [DESTIN (2021)](https://telecom-paris.hal.science/hal-04282057v1) · [Zen and the Art of Network Troubleshooting (2015)](https://hal.science/hal-01411178v1)
- **Datos.** RFCs del IETF y documentación de FRR.
- **IA/DevOps.** LLM + RAG, Containerlab, Batfish y CI.
- **Tiempo.** 6 semanas o más.

### P10 — `edge-coinvest`: herramienta de decisión para co-invertir en edge computing

- **Problema de empresa.** Municipios, operadores y empresas estudian co-invertir en un nodo edge: ¿dónde ponerlo y cuánto paga cada uno?
- **Qué se construye.** Latencias medidas hacia regiones cloud (RIPE Atlas), demanda por municipio (INSEE), costos de nodo y reparto por valor de Shapley.
- **Cursos.** GIN: CSC_4GI04, CSC_4CS01. MODS: ECO_4MO10 (juegos cooperativos), IME_4MO20 Incuber un projet entrepreneurial.
- **Respaldo RMS.** [Co-investment in MEC with dynamic participation (2026)](https://hal.science/hal-05610103v2) · [Co-Investment under Revenue Uncertainty (2026)](https://hal.science/hal-05689326v1) · [Coalitional approach to coinvestment (2023)](https://hal.science/hal-04492328v1) · [Popularity-based cloud offload in fog (2018)](https://telecom-paris.hal.science/hal-02288021v1)
- **Datos.** RIPE Atlas, INSEE y precios cloud.
- **IA/DevOps.** Python científico y algo de CI.
- **Tiempo.** 6 semanas o más.

## Fase 2 — Revisión crítica

Criterios de 1 (débil) a 5 (fuerte). "Factibilidad" = 4–6 semanas, solo, con datos públicos y sin hardware especial. Puntajes después de aplicar las correcciones indicadas.

| # | Proyecto | GIN | MODS | IA/DevOps | Factib. | Reclutador | Total /25 | Decisión y justificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | cloud-cost-carbon | 4 | 5 | 4 | 5 | 5 | **23** | **Elegido.** Datos oficiales sin clave y FinOps muy demandado. El Data Act y la sostenibilidad le dan un MODS real. |
| P4 | vuln-prioritizer | 4 | 4 | 5 | 5 | 5 | **23** | **Elegido.** DevSecOps en CI desde la semana 1 y NIS2/CRA como contexto. *Corrección*: el clasificador ML queda como extensión opcional; el núcleo es riesgo esperado + optimización. |
| P3 | llm-capacity-planner | 4 | 4 | 5 | 4 | 5 | **22** | **Elegido.** Es el que más enseña (series temporales, Kubernetes, MLflow). *Corrección*: se simula primero en Python y Kubernetes entra recién en la semana 5, para no bloquearse. |
| P2 | carbon-aware-scheduler | 4 | 4 | 5 | 4 | 4 | 21 | **Fusionado en P1** como extensión (carbono horario con RTE): comparten datos y área, y dos proyectos GreenOps diluyen el portafolio. |
| P5 | fr-internet-dependency | 5 | 4 | 3 | 3 | 3 | 18 | **Corregido y en reserva.** La detección de anomalías BGP es investigación; queda solo la concentración (HHI). Además se apoya mucho en tu base de redes. Buen 4.º proyecto. |
| P7 | cdn-cache-economics | 4 | 3 | 4 | 4 | 3 | 18 | **En reserva.** Se parece demasiado a tu experiencia de NOC de streaming, y los precios de tránsito no son públicos. |
| P6 | ftth-rollout-economics | 2 | 5 | 3 | 4 | 3 | 17 | **En reserva.** Excelente para MODS (econometría), pero con poco DevOps y el lado GIN es más análisis que construcción. |
| P9 | netops-copilot | 4 | 2 | 4 | 2 | 4 | 16 | **Descartado por ahora.** MODS débil, costo de API o CPU lento, Containerlab necesita privilegios y evaluar un LLM es difícil para un principiante. |
| P8 | ran-energy-estimator | 3 | 4 | 2 | 3 | 2 | 14 | **Descartado.** Depende de tu base 5G y reproduce modelos de investigación; aporta poca práctica de IA o DevOps. |
| P10 | edge-coinvest | 3 | 5 | 2 | 2 | 2 | 14 | **Descartado.** Es investigación (juegos coalicionales) con demanda sintética; a un reclutador de ingeniería le dice poco. |

Filtros aplicados:

- **Demasiado apoyado en la experiencia previa**: P8 (5G), P7 (CDN/streaming) y en parte P5 (redes).
- **Solo investigación**: P10 y la parte BGP de P5.
- **Datos privados**: ninguno de los 10. P7 necesita supuestos de precio de tránsito, lo que debilita su caso de negocio.
- **Difícil de terminar para un principiante**: P9 y P10.

## Fase 3 — Decisión

Elegidos: **P1 `cloud-cost-carbon`**, **P4 `vuln-prioritizer`** y **P3 `llm-capacity-planner`**.

Por qué estos tres y no otros:

- **Cubren tres áreas y tres familias de puestos distintas**: FinOps/GreenOps (economía del cloud), DevSecOps (seguridad y cumplimiento) y MLOps/SRE (operar IA). En las ofertas francesas son tres búsquedas diferentes.
- **Cada uno aporta un MODS diferente**: P1, estructura de mercado y precios; P4, riesgo con presupuesto limitado y regulación; P3, decisión bajo incertidumbre y econometría de pronósticos.
- **Aprendizaje de IA y DevOps escalonado**: P4 enseña CI/CD y seguridad desde el día 1; P1 añade IaC y pipelines de datos programados; P3 añade ML de series temporales, MLflow y Kubernetes.
- **Los tres usan datos oficiales y públicos, verificados en septiembre de 2026.**
- P1 y P3 tocan ambos el cloud, pero no se solapan: P1 decide *dónde comprar* (proveedor, región, instancia) y P3 decide *cuánta capacidad y cuándo*. P5 (redes) queda como candidato natural para un cuarto proyecto.

### Repos

| Repo | Área | Qué funciona hoy | Semanas |
| --- | --- | --- | --- |
| [cloud-cost-carbon](https://github.com/BryanTxz10/cloud-cost-carbon) | FinOps / GreenOps | Ingesta de precios oficiales AWS (4 regiones UE, 3 431 filas), carbono por país (OWID/Ember) y coeficientes CCF; 27 tests; notebook con resultados reales | 5 (+1 opcional) |
| [vuln-prioritizer](https://github.com/BryanTxz10/vuln-prioritizer) | DevSecOps | Ingesta de CISA KEV (1 729), registros CVE v5 con CVSS/SSVC (312 recientes) y dump OSV PyPI (25 767); clientes EPSS y consulta OSV probados sin red; 20 tests; notebook | 5 (+1 opcional) |
| [llm-capacity-planner](https://github.com/BryanTxz10/llm-capacity-planner) | MLOps / SRE | Ingesta y agregación por segundo de 44,1 M de solicitudes reales (trazas Azure LLM 2023–2024) con < 700 MB de RAM; 10 tests; notebook | 6 |

Cada repo trae: README en inglés con resumen en español, `docs/architecture.md`, `docs/roadmap.md` (plan semanal con recursos), `docs/business-case.md`, módulos esqueleto con firmas y docstrings, `notebooks/01_exploracion.ipynb` ejecutado, tests, `pyproject.toml`, `Makefile`, `.gitignore`, `.env.example`, licencia MIT, CI con ruff y pytest, y un workflow manual de verificación de fuentes. Los hitos del roadmap son issues etiquetados (data, model, infra, devops, docs, mods).
