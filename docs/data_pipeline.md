# Aegis Data Pipeline

The Aegis v1 data pipeline transforms public military-spending data into alert records that can be used in a Workshop app.

## Data Sources

Aegis v1 uses two public data sources:

| Source | Purpose |
|---|---|
| SIPRI | Military-spending data by country and year |
| World Bank | Military-spending indicators for country-level comparison |

## Pipeline Flow

The pipeline follows this general process:

1. Ingest public military-spending data.
2. Clean country and year fields.
3. Join SIPRI and World Bank data.
4. Create a curated country-level dataset.
5. Generate alert fields such as score, priority, status, and reason.
6. Output the final alert dataset.

## Main Datasets

| Dataset | Description |
|---|---|
| `country_risk_curated` | Cleaned and joined country-level spending/risk dataset |
| `country_alerts_final` | Final alert dataset used by the Ontology and Workshop app |

## Final Alert Fields

| Field | Description |
|---|---|
| `alert_id` | Unique alert identifier |
| `alert_title` | Human-readable alert title |
| `alert_score` | Numeric score used to represent alert significance |
| `priority` | Priority level for triage |
| `status` | Current alert review status |
| `alert_reason` | Explanation of why the alert was created |
| `country` | Country connected to the alert |
| `year` | Year connected to the alert |

## Output

The final output of the pipeline is `country_alerts_final`, which powers the `Alert` ontology object and the Workshop interface.
