# Northstar OS - Modèle de Ressources

## Philosophie

Northstar OS adapte un modèle hybride centré sur les ressources.

Le système considère que tous les composants manipulables sont des ressources système.

Cette approche permet d'unifier :

- les fichiers ;
- les processus ;
- les modules ;
- les périphériques ;
- les services ;
- les connexions réseau.

## Définition d'une Ressource

Une ressource est un objet système identifié et géré par le noyau ou par les services système.

Chaque ressource possède :

- un identifiant unique ;
- un type ;
- un propriétaire ;
- un ensemble de permissions ;
- un état ;
- des métadonnées.

## Types de Ressources

### Fichiers

Exemples :

- documents ;
- exécutables ;
- archives.

### Processus

Exemples :

- applications ;
- services système.

### Modules

Exemples :

- réseau ;
- audio ;
- compatibilité Linux ;
- compatibilité Windows.

### Périphériques

Exemples :

- disquees ;
- cartes réseau ;
- périphériques USB.

### Services

Exemples :

- gestionnaire de paquets ;
- serveur graphique ;
- journalisation.

### Ressources Réseau

Exemples :

- sockets ;
- tunnels ;
- connexions.

## Gestion Unifiée

Les opérations fondamentales doivent être similaires pour toutes les ressources.

Exemples :

- créer ;
- détruire ;
- lire ;
- modifier ;
- surveiller ;
- partager.

## Permissions

Toutes les ressources utilisent le même modèle de permissions.

Exemples :

- lecture ;
- écriture ;
- exécution ;
- administration ;
- partage.

## Événements

Les ressources peuvent émettre des événements.

Exemples :

- création ;
- suppression ;
- modification ;
- erreur ;
- changement d'état.

Le système d'événements constitue une base importante de l'architecture Northstar.

## Objectif

Permettre une administration cohérente du système en appliquant les mêmes principes à l'ensemble des composants manipulés par l'utilisateur ou par le système.