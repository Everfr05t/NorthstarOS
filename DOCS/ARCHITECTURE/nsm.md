# Northstar OS - Northstar System Manager (NSM)

## Présentation

Le Northstar System Manager (NSM) est le gestionnaire central des ressources, services et modules du système.

Le NSM fonctionne en espace utilisateur avec des privilèges élevés.

Il constitue l'intermédiaire principal entre le noyau, les modules et les services système.

## Philosophie

Le noyau Northstar fournit les mécanismes.

Le NSM fournit l'orchestration.

Cette séparation permet :

- un noyau plus léger ;
- une meilleure modularité ;
- une maintenance simplifiée ;
- une évolution indépendante du système.

## Responsabilités

### Gestion des Modules

Le NSM :

- détecte les modules ;
- charge les modules ;
- décharge les modules ;
- vérifie les dépendances ;
- contrôle les versions.

### Gestion des Ressources

Le NSM maintient un registre central des ressources système.

Exemples :

- fichiers ;
- processus  ;
- services ;
- périphériques ;
- connexions réseau ;
- machines virtuelles.

### Gestion des Permissions

Le NSM vérifie :

- les droits d'accès ;
- les demandes IPC ;
- les privilèges accordés

### Gestion des Services

Le NSM supervise :

- démarrage ;
- arrêt ;
- redémarrage ;
- surveillance.

### Routage IPC

Le NSM participe à :

- l'enregistrement des services ;
- la découverte des interfaces ;
- la résolution des destinations.

### Registre Système

Le NSM maintient un catalogue dynamique contenant :

- ressources ;
- services ;
- modules ;
- événements.

Ce registre constitue la référence officielle du système.

### Événements

Le NSM centralise les événements système.

Exemples :

- connexion d'un périphérique ;
- installation d'un module ;
- changement de permissions ;
- erreur critique.

### Sécurité

Le NSM applique les politiques de sécurité définies par le système.

Aucune ressource ne peut être utilisée sans validation appropriée.

### Tolérance aux Pannes

Le redémarrage du NSM ne doit pas nécessiter le redémarrage du noyau.

les mécanismes critiques restent assurés par le noyau.

## Objectif Long Terme

Faire du NSM le centre opérationnel de Northstar OS.

Le noyau gère les mécanismes fondamentaux.

Le NSM coordonne l'ensemble du système.