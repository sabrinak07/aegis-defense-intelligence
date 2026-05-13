# Aegis Demo Script

## Introduction

Hi, my name is Sabrina Kessler, and this is Aegis, my defense intelligence alert monitor built with Palantir Foundry and Workshop.

Aegis uses public military-spending data from SIPRI and the World Bank. I transformed that data in Foundry into country-level alert records, modeled those alerts in the Ontology, and built a Workshop app that lets analysts review and filter alerts.

The goal of Aegis v1 is to show how raw public data can become an operational alert workflow.

## What Aegis Does

Aegis v1 helps a user monitor defense-spending alerts by country.

Each alert includes fields like:

- country
- year
- alert score
- priority
- status
- alert reason
- alert title

Instead of looking through raw spreadsheets, an analyst can use Aegis to quickly filter alerts, select a record, and understand why that country was flagged.

## Data and Pipeline

The project starts with public military-spending data from SIPRI and the World Bank.

In Foundry, I cleaned and joined the data into a curated dataset called `country_risk_curated`.

Then I created a final alert dataset called `country_alerts_final`, which contains the alert records used in the app.

## Ontology

The main ontology object is `Alert`.

Each Alert object represents one country-level defense-spending signal. This lets the app behave more like an operational workflow instead of a static dashboard.

## Workshop App Walkthrough

At the top of the app, there are filters for narrowing down the alerts.

On the left side, there is an alert list, which acts like an alert queue.

On the right side, there is an alert details panel. When I select an alert, the details panel updates with the selected alert’s country, year, score, priority, status, and reason.

## Example Walkthrough

For example, I can filter by a country or priority level, then select an alert from the list.

The details panel shows why that alert matters, including the score and the reason it was generated.

This makes the workflow easier for analysts because they do not have to manually search through raw spending data. They can focus on the highest-priority alerts and quickly understand the context.

## Version 1 and Future Work

Aegis v1 is the MVP. It proves the core workflow: public spending data can be transformed into ontology-backed alerts and reviewed in a Workshop app.

For Aegis v2, I would add stronger triage actions, better visual trend analysis, and a more polished analyst workflow.

In the longer-term version, Aegis could expand into a full geopolitical watchfloor with procurement data, map-based intelligence, AI-generated summaries, and regional risk monitoring.

## Closing

Aegis shows how Foundry can turn public data into an operational application. The project starts with defense-spending alerts, but the same structure could be expanded into a larger decision-support system for geopolitical monitoring.
