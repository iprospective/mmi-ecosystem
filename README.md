# Écosystème iProspective

> Dépôt public : <https://github.com/iprospective/mmi-ecosystem>  
> Licence : GPL-3.0-or-later.

Documentation et conventions de l'écosystème iProspective.

## Infrastructure

L'infrastructure repose sur un **bloc de 16 IP OVH** et **trois serveurs**, avec
réplication et snapshots ZFS.

- **ZFS** : stockage, datasets, snapshots et réplication entre serveurs.
- **Conteneurs LXC** : services isolés, avec OpenSVC pour le cycle de vie et la
  bascule.
- **Mail** : conteneur dédié avec toute la stack mail.
- **Infra client** : plusieurs conteneurs séparés, chacun avec l'ensemble de ses
  outils.
- **Sécurité** : CrowdSec sur l'ensemble de l'infrastructure.
- **Données** : réplication de bases dans un conteneur dédié, qui assure aussi les
  sauvegardes externalisées des données client.
- **Atlas** : outil de sysadmin.
- **GitLab** : hébergement de l'ensemble des projets client.
- **`prd`** : conteneur des sites hébergés en mutualisé.
- **NAS ZFS sur Odroid** : isolé, sans accès entrant, utilisé comme redondance de
  sauvegarde synchronisée toutes les heures à la maison.
- **Supervision** : Zabbix.
- **Collaboration** : Nextcloud.
- **Pilotage** : Karl/PM, avec synchronisation Redmine pour visualiser les tâches.

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
