# Postmortem — Brute Force Attack — 2026-04-30

## Résumé
50 requêtes POST vers /login.php depuis 172.20.0.1 en moins d'1 seconde.

## Timeline
- 18:54:07 — Début attaque (50 POST en <1s)
- 18:54:08 — Logs visibles dans Grafana/Loki
- 18:54:08 — Alerte déclenchée

## Cause racine
Pas de rate-limiting sur /login.php.

## Impact
Lab uniquement — en prod : compromission compte admin possible.

## Actions correctives
- Ajouter rate-limit dans nginx.conf
- Mettre en place MFA

## Leçon DevSecOps
Le pipeline CI/CD sécurise le code.
Le SOC sécurise l'exécution.
Les deux sont indispensables.
