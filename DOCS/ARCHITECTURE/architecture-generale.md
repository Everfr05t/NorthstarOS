# Northstar OS - Architecture Générale

## Philosophie

Northstar OS repose sur une architecture hybride et modulaire.

L'objectif est de combiner :

- les performances d'un noyau monolithique ;
- la flexibilité d'un micro-noyau ;
- la modularité d'un système à composants

## Architecture en Couches

### Couche Matérielle

Gestion directe du matériel :

- processeur ;
- mémoire ;
- stockage ;
- périphériques ;
- réseau.

### Noyau Northstar

Le noyau contient uniquement les fonctions essentielles.

Responsabilités :

- gestion mémoire ;
- ordonnancement des tâches ;
- interruptions ;
- IPC ;
- sécurité ;
- gestion des privilèges.

Ces composants ne peuvent pas être désactivés.

### Modules Système

Les fonctionnalités non critiques sont implémentées sous forme de modules.

Exemples :

- réseau ;
- audio ;
- interface graphique ;
- Bluetooth ;
- compatibilité Linux ;
- compatibilité Windows ;
- virtualisation.

Les modules peuvent être :

- installés ;
- désinstallés ;
- mis à jour ;
- remplacés.

### Services Utilisateur

Services exécutés hors du noyau.

Exemples :

- gestionnaire de connexion ;
- serveur graphique ;
- gestionnaire de paquets ;
- outils d'administration.

### Applications

Applications natives ou compatibles.

Les applications doivent être isolées du système par défaut.

## Principe de Modularité

Tout composant non indispensable au démarrage du système doit être considéré comme un module.

Le noyau doit rester aussi petit que possible.

## Principe de Compatibilité

Les sous-systèmes de compatibilité ne font pas partie du noyau.

Ils sont installés comme modules indépendants.

Exemples :

- Module Linux ;
- Module Windows ;
- Module POSIX ;
- Module Virtualisation.

## Objectif Long Terme

Permettre à un utilisateur d'installer :

- uniquement le noyau ;
- un environnement serveur ;
- un environnement gaming ;
- un environnement de développement ;

sans modifier la base du système.