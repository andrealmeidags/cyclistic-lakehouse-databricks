# 🚲 Cyclistic Bike-Share: Arquitetura Lakehouse & BI Analytics

[![Databricks](https://img.shields.io/badge/Databricks-Serverless-orange?logo=databricks)](https://databricks.com/)
[![Delta Lake](https://img.shields.io/badge/Delta_Lake-Medallion-blue?logo=apache)](https://delta.io/)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python)](https://python.org/)
[![Looker Studio](https://img.shields.io/badge/Looker_Studio-Dashboard-4285F4?logo=google)](https://lookerstudio.google.com/)

> Pipeline analítico *end-to-end* projetado para ingestão, processamento e modelagem dimensional de mais de **26 milhões de registros** públicos do serviço de compartilhamento de bicicletas Cyclistic (Divvy Bikes, Chicago). A solução evoluiu de uma análise exploratória inicial em R(https://github.com/andrealmeidags/Projeto-Analise-Cyclistic_R) para uma arquitetura escalável de **Lakehouse Medalhão com Databricks, Delta Lake, SQL Warehouse e Looker Studio**.

---

## 🔗 Links e Recursos do Projeto

* 📊 **[Dashboard Interativo no Looker Studio](https://datastudio.google.com/reporting/c82a823d-8c2a-43fd-8755-ba62f1ce7d1b)**


---

## 🏛️ Arquitetura da Solução

O pipeline foi estruturado seguindo as melhores práticas de Lakehouse moderno, garantindo linhagem de dados, confiabilidade e consultas com performance de subsegundo no BI:

```mermaid
flowchart LR
    A[Dados Históricos CSV<br/>26M+ Viagens] --> B[(Camada Bronze<br/>Delta Lake Raw)]
    B --> C[(Camada Silver<br/>Limpeza e Enriquecimento)]
    C --> D[(Camada Gold<br/>Fato e Agregações Otimizadas)]
    D --> E[Databricks SQL<br/>Serverless Warehouse]
    E --> F[Looker Studio<br/>Dashboard Executivo]