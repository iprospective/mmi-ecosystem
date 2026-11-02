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
- **Vaultwarden** pour la gestion des secrets ;
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

## En cours de développement

### Atombox

Serveur mail en développement pour gérer des **domaines complets** dans une optique
d'entreprise : domaines, comptes, livraison et administration de la messagerie.

- GitHub : <https://github.com/iprospective/atombox>
- GitLab : `iprospective/atombox`

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

## Annexe — dépôts des outils

### Infrastructure

- [OpenZFS](https://github.com/openzfs/zfs)
- [LXC](https://github.com/lxc/lxc)
- [OpenSVC](https://github.com/opensvc/opensvc)
- [CrowdSec](https://github.com/crowdsecurity/crowdsec)
- [Zabbix](https://github.com/zabbix/zabbix)
- [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
- [Apache HTTP Server](https://github.com/apache/httpd)
- [PHP](https://github.com/php/php-src)
- [BIND 9](https://gitlab.isc.org/isc-projects/bind9)
- [Certbot](https://github.com/certbot/certbot)

### Mail

- [Postfix](https://github.com/Postfix/postfix)
- [Dovecot](https://github.com/dovecot/core)
- [Roundcube](https://github.com/roundcube/roundcubemail)
- [Atombox](https://github.com/iprospective/atombox)

### Applications
### Développement Dolibarr

- [Modules Dolibarr MMI](https://github.com/lemathou/dolibarr-mmi-modules)
- [Fork Dolibarr](https://github.com/lemathou/dolibarr)


- [Dolibarr](https://github.com/Dolibarr/dolibarr)
- [PrestaShop](https://github.com/PrestaShop/PrestaShop)
- [Nextcloud](https://github.com/nextcloud/server)
- [WordPress](https://github.com/WordPress/WordPress)
- [Redmine](https://github.com/redmine/redmine)
- [GitLab](https://gitlab.com/gitlab-org/gitlab)

### Données

- [MariaDB](https://github.com/MariaDB/server)
- [PostgreSQL](https://github.com/postgres/postgres)
- [Redis](https://github.com/redis/redis)

### Outils internes

- [Karl/PM](https://github.com/iprospective/karl-ai-project-manager)
- [MMI TestKit](https://github.com/iprospective/mmi-testkit)
- [mmi-dev-knowledge](https://github.com/iprospective/mmi-dev-knowledge)
- Atlas — outil interne, pas de dépôt public.

## Licence

GNU GPL v3 ou ultérieure — voir `LICENSE`.
