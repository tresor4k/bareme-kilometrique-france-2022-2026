# Barème kilométrique fiscal France 2022-2026 : la série complète des coefficients (et un gel de quatre ans)

Le **barème kilométrique fiscal** permet aux salariés français qui optent pour les frais réels de déduire leurs frais de déplacement domicile-travail. Ce jeu de données rassemble la **série complète des coefficients sur les cinq déclarations de revenus 2022 à 2026** (revenus 2021 à 2025) : automobiles (5 tranches de puissance), motocyclettes (3 tranches), cyclomoteurs — soit **135 lignes** couvrant chaque combinaison année × type de véhicule × puissance administrative × tranche kilométrique.

## Ce que montre la série

- **Déclaration 2022** (revenus 2021) : revalorisation de **+10 %** (arrêté du 1er février 2022), en réponse à la flambée des prix des carburants.
- **Déclaration 2023** (revenus 2022) : revalorisation de **+5,4 %** (arrêté du 27 mars 2023).
- **Déclarations 2024, 2025 et 2026** : barème **reconduit à l'identique** — aucune revalorisation en quatre déclarations consécutives, une première depuis 2020.
- **Véhicules électriques** : majoration constante de **+20 %** sur le montant calculé (II de l'article 6 B, annexe IV du CGI).

Exemple concret : pour 10 000 km/an en 5 CV thermique, les frais déductibles passent de 4 710 € (déclaration 2022) à **4 965 €** (déclaration 2023) — puis restent figés à 4 965 € quatre années de suite, jusqu'à la déclaration 2026 incluse.

Formule officielle : `frais déductibles = distance × coefficient + constante` (puis ×1,20 si véhicule électrique).

## Structure du fichier CSV

| Colonne | Description |
|---|---|
| `annee_declaration` | Année de la déclaration (2022-2026) |
| `annee_revenus` | Année des revenus déclarés (2021-2025) |
| `type_vehicule` | automobile / motocyclette / cyclomoteur |
| `puissance_administrative` | Tranche de puissance fiscale (CV) |
| `tranche_kilometrique` | Libellé officiel de la tranche |
| `km_min` / `km_max` | Bornes de la tranche (km_max vide = sans plafond) |
| `coefficient_eur_par_km` | Coefficient multiplicateur (€/km) |
| `constante_eur` | Constante additive de la tranche intermédiaire (€) |
| `majoration_electrique_pct` | Majoration véhicule électrique (%) |
| `source_arrete` / `jorf_id` | Arrêté source et identifiant Légifrance |

## Sources primaires (vérifiées le 10/07/2026)

- Arrêté du 1er février 2022, JORF n°0037 du 13/02/2022 (Légifrance `JORFTEXT000045160753`)
- Arrêté du 27 mars 2023 (Légifrance `JORFTEXT000047416556`), codifié à l'article 6 B de l'annexe IV au Code général des impôts
- Non-revalorisation 2024-2026 confirmée par economie.gouv.fr et service-public.gouv.fr (actualité A14686)

## Où trouver ces données

- Dépôt de référence : [data.gouv.fr — barème kilométrique fiscal France 2022-2026](https://www.data.gouv.fr/datasets/bareme-kilometrique-fiscal-france-2022-2026-coefficients-complets-autos-motos-cyclomoteurs)
- Archive DOI : [Zenodo 10.5281/zenodo.21297050](https://zenodo.org/records/21297050)
- Analyse détaillée : [dev.to — Barème kilométrique 2022-2026, la série complète](https://dev.to/tresor4k/bareme-kilometrique-2022-2026-la-serie-complete-des-coefficients-et-un-gel-de-4-ans-3eji)

## Pages du site utilisant ces coefficients

Les coefficients de ce fichier sont identiques pour les déclarations 2024, 2025 et 2026 (même barème reconduit). Ils sont repris (contrôle du 13/10/2026) sur :

- [Barème kilométrique 2026 (revenus 2025)](https://macalculatriceenligne.com/finance/impots/bareme-km-2026/) : tableau et simulateur de frais réels
- [Calcul des frais kilométriques](https://macalculatriceenligne.com/finance/divers/calcul-frais-kilometriques/) : page de référence également pour les déclarations 2024 et 2025
- [Calculateur de frais réels 2026](https://macalculatriceenligne.com/finance/impots/calcul-frais-reels/) : frais de trajet au barème dans la déduction des frais réels
- [Prix de l'essence au kilomètre](https://macalculatriceenligne.com/auto/calcul-prix-essence-km/) : coût kilométrique comparé au barème

Exemple identique dans le CSV et sur la page barème 2026 : 5 CV, 10 000 km, tranche 5 001 à 20 000 km : (10 000 × 0,357) + 1 395 = 4 965 €.

**Licence : CC BY 4.0** — attribution : Rédaction MaCalculatrice, macalculatriceenligne.com.
