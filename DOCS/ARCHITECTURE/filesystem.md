# Northstar OS - Système de Fichiers

## Présentation

Le système de fichiers Northstar a pour objectif de fournir :

- sécurité ;
- modularité ;
- performance ;
- fiabilité ;
- évolutivité.

Il constitue l'une des fondations du système et doit s'intégrer naturellement avec le modèle de ressources Northstar.

## Philosophie

Dans Northstar OS, un fichier est une ressource.

Le système de fichiers est donc une implémentation particulière du modèle global de ressources.

Les fichiers, répertoires et volumes utilisent les mêmes principes que les autres ressources système :

- identifiant ;
- propriétaire ;
- permissions ;
- événements ;
- métadonnées.

## Objectifs

Le système doit permettre :

- snapshots ;
- rollback ;
- permissions avancées ;
- chiffrement ;
- journalisation ;
- modularité.

## Organisation

Structure proposée :

```
/
├── system/
├── users/
├── apps/
├── modules/
├── profiles/
├── services/
├── devices/
├── virtual/
└── data/
```

## Répertoires Principaux

### /system

Composants fondamentaux du système.

Contient :

- fichiers système ;
- bibliothèques ;
- configurations essentielles.

### /users

Données des utilisateurs.

Chaque utilisateur possède son propre espace isolé.

### /apps

Applications installées.

Chaque application possède :

- ses fichiers ;
- ses métadonnées ;
- ses permissions.

### /modules

Modules Northstar.

Contient :

- modules système ;
- modules de compatibilité ;
- modules expérimentaux.

### /profiles

Définitions des profils système.

Exemples :

- gaming ;
- développement ;
- serveur ;
- bureautique.

### /services

Services installés.

### /devices

Représentation des périphériques.

Exemples :

- stockage ;
- USB ;
- audio ;
- réseau.

### /virtual

Ressources virtuelles exposées par le système.

Exemples :

- statistiques ;
- informations système ;
- IPC ;
- événements.

### /data

Données partagées entre composants.

## Permissions

Le système utilise les permissions Northstar.

Chaque ressource peut définir :

- lecture ;
- écriture ;
- exécution ;
- partage ;
- administration.

Les permissions sont gérées par le NSM.

## Snapshots

Le système supporte nativement les snapshots.

Utilisation :

- sauvegarde ;
- tests ;
- mises à jour ;
- récupération.

## Rollback

Chaque snapshot peut être restauré.

Objectifs :

- récupération rapide ;
- protection contre les mises à jour défaillantes ;
- expérimentation sécurisée.

## Journalisation

Les opérations importantes sont enregistrées.

Exemples :

- suppression
- déplacement ;
- modification ;
- installation.

## Chiffrement

Le chiffrement peut être appliqué :

- à un fichier ;
- à un répertoire ;
- à un volume ;
- à un profil utilisateur.

Le système doit permettre un fonctionnement transparent pour l'utilisateur.

## Compatibilité

Northstar doit pouvoir monter différents systèmes de fichiers.

Exemples :

- FAT32 ;
- exFAT ;
- NTFS ;
- ext4 ;
- Btrfs.

Le support est assuré via des modules.

## Événements

Les ressources du système de fichiers peuvent produire des événements.

Exemples :

- création ;
- modification ;
- suppression ;
- accès.

Ces événements peuvent être utilisés par :

- le NSM ;
- les applications ;
- les outils de sécurité.

## Objectif Long terme

Créer un système de fichiers capable de servir aussi bien :

- un ordinateur personnel ;
- une station de travail ;
- un serveur ;
- un environnement de développement.

Tout en restant cohérent avec le modèle de ressources Northstar.