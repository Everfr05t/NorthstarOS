# Northstar OS - Système de Modules

## Présentation

Le système de modules constitue le mécanisme principal d'extension de Northstar OS.

Toute fonctionnalité non essentielle au fonctionnement fondamental du système doit être implémentée sous forme de module.

Cette approche permet :

- une forte modularité ;
- des mises à jour indépendantes ;
- une maintenance simplifiée :
- une personnalisation avancée.

## Philosophie

Principe fondamental :

> Tout ce qui n'est pas indispensable au démarrage du système doit être un module.

Le noyau reste minimal.

Les fonctionnalités sont ajoutées progressivement selon les besoins de l'utilisateur.

## Types de Modules

### Modules Système

Ajoutent des capacités fondamentales.

Exemples :

- Réseau ;
- Audio ;
- Bluetooth ;
- Impression ;
- Gestion énergétique.

### Modules de Compatibilité

Permettent l'exécution d'applications provenant d'autres écosystèmes.

Exemples :

- Compatibilité Linux ;
- Compatibilité Windows ;
- Compatibilité POSIX.

### Modules d'Interface

Responsables de l'expérience utilisateur.

Exemples :

- Northstar Pixel UI ;
- Northstar Modern UI ;
- Gestionnaires de fenêtres alternatifs.

### Modules de Développement

Ajoutent des outils destinés aux développeurs.

Exemples :

- SDK ;
- Débogage ;
- Virtualisation ;
- Compilation.

### Modules Expérimentaux

Fonctionnalités en test.

Ces modules peuvent être instables ou réservés aux utilisateurs avancés.

## Structure d'un Module

Chaque module possède :

- un identifiant unique ;
- un nom ;
- une version ;
- un auteur ;
- des dépendances ;
- des permissions ;
- une interface IPC ;
- des métadonnées.

## Cycle de Vie

### Installation

Le module est enregistré auprès du NSM

Le système vérifie :

- l'intégrité ;
- les dépendances ;
- les permissions demandées.

### Chargement

Le module est activé.

Ses services sont enregistrés.

Ses interfaces IPC deviennent accessibles.

### Mise à jour

Les modules peuvent être mis à jour indépendamment du noyau.

Le NSM vérifie :

- la compatibilité ;
- les dépendances ;
- les migrations éventuelles.

### Désinstallation

Le module est arrêté proprement.

Toutes ses ressources sont libérées.

Le registre système est mis à jour.

## Permissions

Chaque module doit déclarer explicitement :

- accès réseau ;
- accès stockage ;
- accès matériel ;
- accès IPC ;
- privilèges système.

Le principe appliqué est :

> Privilège minimal.

## Dépendances

Les modules peuvent dépendre d'autres modules.

Exemple :

```
Gaming Profile
 ├── Graphics Module
 ├── Audio Module
 └── Windows Compatibility Moduleq
```

Le NSM résout automatiquement les dépendances.

## Profils

Les profils sont des ensembles prédéfinis de modules.

Exemples :

### Profil Gaming

- Audio
- Réseau
- Graphiques
- Compatibilité Windows

### Profil Développement

- SDK
- Virtualisation
- Outils de débogage

### Profil Serveur

- Réseau
- SSH
- Gestion de services

## Sécurité

Les modules sont isolés autant que possible.

Un module défaillant ne doit pas compromettre :

- le noyau ;
- les autres modules ;
- le système complet.

## Compatibilité Future

Le système doit permettre l'ajout de nouveaux types de modules sans modification majeur du noyau.

La modularité est considérée comme une caractéristique fondamentale de Northstar OS.

## Vision Long Terme

Northstar OS doit pouvoir être assemblé comme un ensemble de briques indépendantes.

Chaque utilisateur construit son système selon ses besoins.

Le noyau fournit la base.

Les modules construisent l'expérience.