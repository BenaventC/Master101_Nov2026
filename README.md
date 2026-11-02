# Master 101 — Analyse des données ESS (Round 11)

Matériel du cours : analyse pas à pas des données de l'[European Social Survey, Round 11](https://ess.sikt.no/en/series/50ebb530-c72e-4002-a7bf-5581e3fdfe21).

## Notebooks

| Notebook | Contenu |
|---|---|
| `ESS11_analyse.ipynb` | **Étape 1** — Lecture du fichier ESS11MD (9 348 colonnes), sélection de 50 variables (socio-démo, confiance, valeurs de Schwartz, bonheur), recodage des valeurs manquantes, export de `ESS_start.csv` |
| `ESS11_confiance.ipynb` | **Étape 2** — Corrélations, KMO/Bartlett, EFA oblimin sur les 10 items de confiance (interpersonnelle vs institutionnelle), scores factoriels, scattergram des moyennes par pays |
| `ESS11_bonheur.ipynb` | **Étape 3** — Index de bonheur (happy, stflife, health ; α de Cronbach), régressions WLS du bonheur sur la confiance (avec contrôles socio-démo et effets fixes pays) |
| `ESS11_valeurs.ipynb` | **Étape 4** — EFA des 21 valeurs de Schwartz (4 dimensions d'ordre supérieur), clustering mixte (k-means 100 micro-classes + CAH de Ward), typologie en 6 clusters et lien avec le bonheur |

## Données

- `ESS_start.csv` : sous-ensemble prêt à l'emploi (46 162 répondants × 58 variables), incluant les scores factoriels (`trust_inst`, `trust_interp`, `val_F1`–`val_F4`), l'index de bonheur (`bonheur_index`) et la typologie de valeurs (`val_cluster`).
- Le fichier source `ESS11MD_e01_2.csv` (1,7 Go) n'est pas versionné : il se télécharge sur le [portail de données ESS](https://ess.sikt.no/en/series/50ebb530-c72e-4002-a7bf-5581e3fdfe21).

## Dépendances

```
pandas numpy matplotlib seaborn statsmodels factor_analyzer scikit-learn scipy
```

Note : `factor_analyzer` 0.5.x requiert `scikit-learn<1.8` (épinglé ici en 1.7.2).
