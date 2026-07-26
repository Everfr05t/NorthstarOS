# Northstar OS - Noyau

## Présentation

Le noyau Northstar est un noyau hybride modulaire.

Il conserve les composants critiques dans l'espace noyau afin d'assurer des performances élevées tout en permettant l'ajout ou le remplacement de nombreuses fonctionnalités via des modules indépendants.

## Objectifs

Le noyau doit être :

- Modulaire ;
- Sécurisé ;
- Évolutif ;
- Performant ;
- Portable.

## Responsabilités du Noyau

Les fonctions suivantes font partie du noyau principal :

- Gestion mémoire ;
- Ordonnancement des tâches ;
- Gestion des interruptions ;
- IPC (Communication Inter-Processus) ;
- Gestion des privilèges ;
- Gestion des modules ;
- Sécurité fondamentale.

Ces composants sont considérés comme indispensables au fonctionnement du système.

## Architecture

Le noyau suit un architecture hybride :

### Espace Noyau

Composants critiques :

- Scheduler ;
- Gestion mémoire ;
- IPC ;
- Gestion des modules ;
- Contrôle matériel essentiel.

### Espace Utilisateur

Services non critiques :

- Interface graphique ;
- Réseau avancé ;
- Audio ;
- Compatibilité Linux ;
- Compatibilité Windows ;
- Services applicatifs.

## Gestion des Modules

Les modules peuvent être :

- chargés dynamiquement ;
- déchargés ;
- mis à jour indépendamment ;
- remplacés par des implémentations alternaatives.

Chaque module possède :

- un identifiant unique ;
- une version ;
- des dépendances ;
- des permissions.

## Sécurité

Les modules doivent être isolés autant que possible.

Un module défaillant ne doit pas provoquer l'arrêt complet du système.

Les permissions accordées aux modules sont limitées au strict nécessaire.

## Compatibilité

Les couches de compatibilité ne font pas partie du noyau.

Elles sont considérées comme des modules système.

Exemples :

- Linux Compatibility Module ;
- Windows Compatibility Module ;
- Virtualization Module.

## Vision Long Terme

Le noyau doit rester relativement compact.

Toute fonctionnalité qui n'est pas indispensable au démarrage ou à la stabilité du système doit être envisagée comme un module externe.

