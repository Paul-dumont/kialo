# Relation-based Argument Mining sur Kialo

Projet de fouille d'arguments à partir des débats de la plateforme [Kialo](https://www.kialo.com).

1. **Scraping et exploration** : récupération des 250 discussions Kialo en anglais les plus actives et les mieux classées, puis analyse exploratoire des données.
2. **Relation discovery et relation classification** : pour une paire d'arguments, prédire s'ils sont liés, puis si la relation est un soutien (Pro) ou une attaque (Con).

## Contenu

| Fichier | Rôle |
|---|---|
| `Scraping_Kialo.ipynb` | Scraping des discussions via l'API Kialo et Selenium (inspiré de [4mbroise/ADC](https://github.com/4mbroise/ADC/blob/main/tool/kialo.ipynb)) |
| `Partie_2_Mining.ipynb` | Parsing, nettoyage, exploration des données et modèles |
| `rawData/` | Les 250 débats exportés depuis Kialo (un fichier `.txt` par débat) |
| `kialo-url-ids.csv` | Identifiant et tags de chaque débat |

## Données

- 250 débats en anglais, environ 96 000 arguments après nettoyage.
- Chaque argument a un parent et une relation : **Pro** (soutien) ou **Con** (attaque).
- Le classement Kialo évolue : relancer le scraping ne donnera pas exactement les mêmes débats. Les données utilisées sont donc fournies dans `rawData/`.

Le contenu des débats appartient à leurs auteurs sur Kialo et reste soumis aux [conditions d'utilisation de Kialo](https://www.kialo.com/terms). Il est fourni ici uniquement à des fins de recherche et d'enseignement.

## Installation

```bash
pip install pandas matplotlib requests selenium tqdm scikit-learn
```

Le scraping demande un compte Kialo : renseigner `kialoUsername` et `secret` dans `Scraping_Kialo.ipynb` (ne jamais les committer).
