# Écosystème iProspective

> Dépôt public : <https://github.com/iprospective/mmi-ecosystem>  
> Licence : GPL-3.0-or-later.

Documentation et conventions de l'écosystème iProspective.

## Infrastructure

L'écosystème repose sur **plusieurs serveurs** et des services séparés par
conteneurs :

- **ZFS** pour le stockage, les snapshots et la réplication ;
- **conteneurs LXC** pour isoler les services, avec **OpenSVC** pour le cycle de
  vie et la bascule ;
- un service **mail** dédié ;
- des environnements séparés pour les infrastructures clientes ;
- **GitLab** pour les projets, **Nextcloud** pour la collaboration ;
- **Zabbix** pour la supervision ;
- **Karl/PM** pour piloter le projet, avec synchronisation Redmine pour les tâches.

Ce dépôt décrit les **principes et l'organisation**, pas les adresses, secrets,
sauvegardes détaillées ni procédures d'urgence. Ces éléments restent dans les
documents privés d'exploitation.

## Principes

- séparation stricte entre production, recette et développement ;
- isolation des services et des environnements client ;
- **GitLab** pour le code, **Karl/PM** pour les tâches et décisions, **Knowledge**
  pour les faits produit, **TestKit** pour les verdicts ;
- sauvegardes, supervision et moindre privilège par défaut ;
- détails d'exploitation, secrets et procédures sensibles dans les documents privés.

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
