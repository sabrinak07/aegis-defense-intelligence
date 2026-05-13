# Aegis Architecture

Aegis is built as an ontology-backed alert monitoring app using Palantir Foundry and Workshop.

## High-Level Architecture

The project follows this flow:

1. Public military-spending data is collected from SIPRI and the World Bank.
2. The data is cleaned and joined in Foundry.
3. Foundry transforms create curated country-level records.
4. Final alert records are generated in `country_alerts_final`.
5. The `Alert` object type is created in the Ontology.
6. Workshop uses the Alert object to power the alert list, filters, and details panel.

## Main Components

| Component | Purpose |
|---|---|
| Foundry Pipeline | Cleans, joins, and transforms public spending data |
| Ontology | Models each alert as an operational object |
| Workshop App | Provides the user interface for reviewing and filtering alerts |
| Alert Object | Represents one country-level defense-spending alert |

## Main Object Type

### Alert

The `Alert` object contains fields such as:

- `alert_id`
- `alert_title`
- `alert_score`
- `priority`
- `status`
- `alert_reason`
- `country`
- `year`

## App Layout

The Workshop app is organized into three main sections:

| Section | Description |
|---|---|
| Top Filters | Used to narrow alerts by year, country, priority, and status |
| Left Panel | Displays the alert list / alert queue |
| Right Panel | Displays details for the selected alert |

## Design Goal

The goal of the architecture is to show how public data can be transformed into an operational monitoring workflow. Aegis is not just a chart dashboard; it is designed as a small analyst-facing application for reviewing defense-spending alerts.
