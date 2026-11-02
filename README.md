# Écosystème iProspective

> Dépôt public : <https://github.com/iprospective/mmi-ecosystem>  
> Licence : GPL-3.0-or-later.

Documentation et conventions de l'écosystème iProspective.

## Infrastructure

L'écosystème repose sur **plusieurs serveurs** et une séparation des services par
conteneurs :

- **ZFS** pour le stockage, les datasets, les snapshots et les sauvegardes ;
- **conteneurs LXC** pour isoler les services et limiter les dépendances ;
- **OpenSVC** pour piloter le cycle de vie et la bascule des conteneurs ;
- **Zabbix** pour la supervision et les alertes ;
- **Nextcloud** pour le partage et la collaboration ;
- GitLab, Redmine/Karl, les services mail et les environnements de recette pour le
  développement et les tests.

L'objectif est de garder des services **isolés, sauvegardables, supervisés et
reproductibles**, sans mélanger production, recette et développement.

## Outils

- **Karl / PM** : <https://github.com/iprospective/karl-ai-project-manager>
- **MMI TestKit** : <https://github.com/iprospective/mmi-testkit>
- **mmi-dev-knowledge** : <https://github.com/iprospective/mmi-dev-knowledge>

Karl et PM sont **le même outil** : `karl-ai-project-manager`.

Karl/PM est le **gestionnaire de projet assisté par IA, modulaire** : il porte le
projet, les tâches, les décisions, les environnements et les workflows. TestKit
exécute les tests ; Knowledge porte les faits produits génériques.

## Règle

Les outils sont utilisés **conjointement** : Karl/PM pilote le projet, décrit les
tâches et les envs, TestKit produit les verdicts, Knowledge fournit les faits
produit.

## Licence

GNU GPL v3 ou ultérieure — voir `LICENSE`.
