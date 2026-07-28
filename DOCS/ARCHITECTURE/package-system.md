# Northstar OS - Système de Paquets

## Présentation

Le système de paquets Northstar est responsable de l'installation, de la mise à jour, de la suppression et de la gestion des composants du système.

Contrairement aux gestionnaires de paquets traditionnels, il gère de manière unifiée :

- les modules ;
- les profils ;
- les applications ;
- les services ;
- les couches de compatibilité.

## Philosophie

Le système est construit autour d'une idée simple :

> Tout composant installable est un paquet Northstar.

L'utilisateur ne doit pas avoir à distinguer :

- une application ;
- un module ;
- un profil ;
- un service.

Le système gère ces différences automatiquement.

## Format de Paquet

Extension proposée :

`.nspkg`

Chaque paquet contient :

- fichiers ;
- métadonnées ;
- dépendances ;
- permissions ;
- signatures ;
- informations de compatibilité.

## Métadonnées

Chaque paquet doit déclarer :

- identifiant ;
- version ;
- auteur ;
- licence ;
- type ;
- dépendances ;
- ressources utilisées ;
- permissions demandées.

Exemple :

```
name: northstar-gaming-profile
version: 1.0.0
type: profile
dependencies:
    - graphics
    - audio
    - windows-compat
permissions:
    - system.read
```

## Types de Paquets

### Application

Logiciel utilisateur.

Exemples :

- éditeurs ;
- navigateurs ;
- jeux.

### Module

Ajout d'une fonctionnalité système.

Exemples :

- audio ;
- réseau ;
- bluetooth.

### Profil

Ensemble préconfiguré de modules.

Exemples :

- gaming ;
- développement ;
- serveur ;

### Service

Composant exécuté en arrière-plan.

Exemples :

- synchronisation ;
- journalisation ;
- supervision.

### Compatibilité

Sous-systèmes externes.

Exemples :

- Linux Compatibility Layer ;
- Windows Compatibility Layer.

## Dépôts

### Dépôt Officiel

Maintenu par le projet Northstar.

Garantit :

- validation ;
- signature ;
- compatibilité.

### Dépôts Communautaires

Crées par la communauté.

Le système doit clairement distinguer :

- officiel ;
- communautaire ;
- expérimental.

### Dépôts Privés

Utilisés en entreprise ou pour des usages spécifiques.

## Commandes

Outil officiel :

`ns`

Exemples :

```
ns install firefox

ns install gaming-profile

ns remove audio-module

ns update

ns search browser
```

## Gestion des Dépendances

Le gestionnaire résout automatiquement :

- dépendances ;
- conflits ;
- versions compatibles.

Les dépendances circulaires doivent être détectées.

## Mises à Jour

Le système supporte :

- mises à jour individuelles ;
- mises à jour globales ;
- mises à jour différentielles.

Le mises à jour peuvent être annulées.

## Rollback

Chaque opération importante doit pouvoir être annulée.

Exemples :

- installation ;
- suppression ;
- mise à jour.

Le rollback constitue une fonctionnalité native du système.

## Sécurité

Les paquets peuvent être :

- signés ;
- vérifiés ;
- analysés.

Le système doit avertir l'utilisateur lorsqu'un paquet demande des permissions sensibles.

## Profils

Les profils constituent des paquets spéciaux.

Installation

`ns install gaming-profile`

Le système installe automatiquement tous les modules requis.

## Intégration avec le NSM

Le NSM supervise :

- l'enregistrement ;
- l'activation ;
- la désactivation ;
- la suppression.

Le gestionnaire de paquets communique avec le NSM via l'IPC officiel.

## Objectif Long terme

Permettre à un utilisateur de construire entièrement son système à partir de paquets.

Le système de paquets devient le mécanisme principal de personnalisation de Northstar OS.