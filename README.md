# :moneybag: Hard Money vs. Fiat: Pipeline de Engenharia de Dados

![Status](https://img.shields.io/badge/Status-Concluído-green)
![Stack](https://img.shields.io/badge/Stack-Databricks%20|%20Python%20|%20SQL%20|%20PowerBI-blue)

> **"Se eu tivesse investido R$ 10.000,00 há 5 anos, qual seria meu patrimônio hoje?"**

Este projeto de Engenharia de Dados constrói um pipeline ETL completo (Bronze, Silver, Gold) para responder a essa pergunta, comparando a performance da moeda fiduciária brasileira (Poupança) e ativos escassos (Bitcoin,ouro), todos normalizados em Reais (BRL).

---

## :bar_chart: Resultado Final (Dashboard)

<img width="1919" height="1079" alt="Image" src="https://github.com/user-attachments/assets/a750e2c2-7033-4f16-9eff-6970cc2eb62a" />
---

## Arquitetura da Solução

O projeto segue a **Arquitetura Medalhão (Medallion Architecture)** dentro do Databricks, garantindo rastreabilidade e qualidade dos dados.

```mermaid
graph LR
    A[APIs Externas] -->|Python/YFinance/BCB| B[(Bronze Layer\nRaw Data)]
    B -->|SQL/Clean| C[(Silver Layer\nUnified & BRL Converted)]
    C -->|SQL/Agg| D[(Gold Layer\nFinancial Logic)]
    D -->|ODBC| E[Power BI\nVisualization]

    style B fill:#cd7f32,stroke:#333,stroke-width:2px
    style C fill:#c0c0c0,stroke:#333,stroke-width:2px
    style D fill:#ffd700,stroke:#333,stroke-width:2px

