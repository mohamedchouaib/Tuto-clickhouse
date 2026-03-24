# - Introduction à ClickHouse

TP d'introduction à **ClickHouse**, une base de données orientée colonnes optimisée pour l'analyse de données (OLAP).

## Objectifs

- Comprendre l'architecture orientée colonnes de ClickHouse
- Manipuler les moteurs de tables MergeTree
- Écrire des requêtes analytiques (agrégations, séries temporelles, fonctions fenêtres)
- Comparer avec les bases relationnelles classiques (MySQL, PostgreSQL)
- Visualiser les résultats avec Python (pandas, seaborn)

## Données

Le TP utilise 3 jeux de données adaptés aux cas d'usage typiques de ClickHouse :

| Table | Description | Cas d'usage |
|-------|------------|-------------|
| `web_logs` | Logs d'un serveur web (~100 lignes) | Analyse de trafic, monitoring |
| `iot_metrics` | Métriques de capteurs IoT (~60 lignes) | Séries temporelles |
| `ecommerce_events` | Événements e-commerce (~80 lignes) | Funnel d'achat, analytics |

## Prérequis

- Docker et Docker Compose installés
- Navigateur web (pour Jupyter Lab)

## Lancement

```bash
docker compose up --build -d
```

Accéder au notebook : [http://localhost:8888](http://localhost:8888)

Ouvrir le fichier `clickhouse.ipynb`.

## Arrêt

```bash
docker compose down
```

Pour supprimer aussi les volumes de données :

```bash
docker compose down -v
```

## Structure

```
tp5-clickhouse/
├── docker-compose.yml          # ClickHouse + Jupyter
├── Dockerfile                  # Image Jupyter avec dépendances
├── requirements.txt            # Dépendances Python
├── README.md                   # Ce fichier
├── clickhouse.ipynb        # Notebook du TP
└── init-db/
    └── 01_init.sql             # Schéma + données initiales
```
