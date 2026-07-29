# Northstar OS - Modèle Applicatif

## Présentation

Le modèle applicatif Northstar a pour objectif de fournir un environnement simple, flexible et sécurisé pour l'exécution des logiciels.

Le système doit permettre aussi bien :

- l'exécution rapide d'un exécutable autonome ;
- l'installation d'application complexes via le système de paquets ;
- le développement d'applications natives Northstar.

## Philosophie

Une application ne doit pas être obligatoirement liée à un format unique.

Northstar privilégie la simplicité d'exécution tout en permettant des mécanismes avancés lorsque nécessaire.

## Types d'Applications

### Exécutable Autonome

L'application est distribuée sous forme d'un simple exécutable.

Exemple :

`mon_application`

Le système peut l'exécuter directement.

Aucune installation n'est nécessaire.

### Application Packagée

L'application est distribuée sous forme d'un paquet Northstar.

Exemple :

`mon_application.nspkg`

Le système gère :

- installation ;
- mises à jour ;
- dépendances ;
- permissions.

## Manifestes

### Optionnels

Les manifestes ne sont pas obligatoires pour les exécutables simples.

Ils deviennent recommandés pour :

- les applications complexes ;
- les applications nécessitant des permissions ;
- les applications distribuées via les dépôts.

Exemple :

```
name: text-editor
version: 1.0.0

permissions:
    - filesystem.read
    - filesystem.write

gui: true
```

## Sandboxing

Les applications sont isolées par défaut.

Sans permission explicite, une application ne peut pas :

- accéder au système complet ;
- accéder aux fichiers d'autres applications ;
- accéder au matériel ;
- communiquer librement avec d'autres processus.

## Permissions

Les permissions sont déclaratives.

L'utilisateur peut :

- accepter ;
- refuser ;
- limiter.

Exemples :

- stockage ;
- réseau ;
- audio ;
- caméra ;
- USB ;
- impression.

## Applications CLI

Les applications en ligne de commande sont des citoyens de première classe.

Northstar ne privilégie pas exclusivement les applications graphiques.

## Applications Graphiques

Les applications graphiques utilisent les interfaces officielles du système.

Elles restent compatibles avec les mécanismes de sécurité Northstar.

## Applications Sans Interface

Une application peut fonctionner :

- comme service ;
- comme démon ;
- comme outil CLI ;
- comme processus de fond.

Aucune interface graphique n'est requise.

## Intégration avec le NSM

Le NSM maintient :

- les permissions ;
- les ressources utilisées ;
- les évènements ;
- les statistiques.

## Compatibilité

Les applications compatibles Linux ou Windows doivent respecter les politiques de sécurité Northstar.

La couche de compatibilité ne constitue pas une exception au modèle de sécurité.

## Objectif Long Terme

Permettre l'exécution de logiciels simples ou complexes tout en conservant :

- modularité ;
- sécurité ;
- simplicité ;
- performance.