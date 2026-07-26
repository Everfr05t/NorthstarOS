# Northstar OS - Séquence de Démarrage

## Objectif

La séquence de démarrage de Northstar OS a pour rôle de préparer l'environnement matériel et logiciel nécessaire à l'exécution du noyau.

Elle doit être :

- Fiable ;
- Modulaire ;
- Compatible BIOS et UEFI ;
- Extensible ;
- Sécurisée.

## Vue d'ensemble

```
                               BIOS / UEFI
                                    │  
                                    ▼
                           Northstar Bootloader
                                    │  
                                    ▼
                            Hardware Discovery
                                    │  
                                    ▼
                              Kernel Loader
                                    │  
                                    ▼
                             Northstar Kernel
                                    │  
                                    ▼
                               Core Services
                                    │  
                                    ▼
                                 Modules
                                    │  
                                    ▼
                            Interface ou Shell
```

## Étape 1 : Firmware

Northstar doit pouvoir démarrer depuis :

- BIOS Legacy ;
- UEFI.

Le firmware initialise :

- le processeur ;
- la mémoire ;
- les périphériques essentiels.

Puis transmet l'exécution au chargeur d'amorçage Northstar.

## Étape 2 : Northstar Bootloader

Le Bootloader Northstar consitue la première composante contrôlée par le système.

Responsabilités :

- Détection du mode BIOS ou UEFI ;
- Vérification de l'intégrité du système ;
- Chargement du noyau ;
- Chargement de la configuration de démarrage ;
- Préparation des informations matérielles.

Le bootloader doit rester léger.

Il ne doit pas contenir de logique système complexe.

## Étape 3 : Hardware Discovery

Le système collecte les informations nécessaires :

- Mémoire disponible ;
- Nombre de coeurs CPU ;
- Contrôleurs de stockage ;
- Cartes graphiques ;
- Interfaces réseau.

Les données sont regroupées dans une structure unique transmise au noyau.

## Étape 4 : Kernel Loading

Le noyau est chargé en mémoire.

Avant son exécution :

- Vérification de l'intégrité ;
- Initialisation des structures mémoire ;
- Préparation des zones réservées.

Le contrôle est ensuite transféré au noyau.

## Étape 5 : Initialisation du Noyau

Le noyau initialise :

- Gestion mémoire ;
- Scheduler ;
- Interruptions ;
- IPC ;
- Gestionnaire de modules ;
- Gestionnaire de sécurité.

À ce stade, Northstar devient autonome.

## Étape 6 : Services Fondamentaux

Les premiers services système sont lancés.

Exemples :

- Gestionnaire de stockage ;
- Journalisation ;
- Configuration système ;
- Gestionnaire de périphériques.

Ces services sont considérés comme essentiels.

## Étape 7 : Chargement des modules

Le système charge les modules sélectionnés.

Exemples :

- Réseau ;
- Audio ;
- Interface graphique ;
- Compatibilité Linux ;
- Compatibilité Windows ;
- Virtualisation.

Le chargement dépend du profil installé.

## Étape 8 : Session Utilisateur

Selon la configuration :

Mode Serveur :

- Shell système ;
- Services réseau ;
- Administration distante.

Mode Desktop :

- Northstar UI ;
- Gestionnaire de session ;
- Applications utilisateur.

## Mode de Récupération

Si une erreur critique est détectée :

- Module corrompu ;
- Échec de démarrage ;
- Mise à jour incomplète ;

le système peut démarrer dans un environnement minimal sécurisé.

Ce mode permet :

- le diagnostic ;
- la réparation ;
- le rollback.

## Objectif Long Terme

Le temps de démarrage doit être optimisé afin que seuls les composants réellement nécessaires soient chargés.

La philosophie reste :

"Ne charger que ce qui est utile."