# Northstar OS - Modèle de Sécurité

## Présentation

La sécurité de Northstar OS repose sur le principe de sécurité par conception.

Le système doit limiter les risques avant qu'un incident ne se produise plutôt que tenter de les corriger après coup.

La sécurité constitue une composante fondamentale du noyau, du NSM et du système de modules.

## Principes Fondamentaux

### Principe du Privilège Minimal

Chaque composant reçoit uniquement les permissions nécessaires à son fonctionnement.

Cela s'applique à :

- utilisateurs ;
- applications ;
- services ;
- modules ;
- pilotes.

### Principe d'Isolation

Les composants du système doivent être isolés autant que possible.

Objectifs :

- limiter la propagation des erreurs ;
- limiter les compromissions ;
- faciliter le diagnostic.

### Principe de Transparence

Les permissions accordées doivent être visibles et compréhensibles.

L'utilisateur doit savoir :

- qui accède à quoi ;
- pourquoi ;
- pendant combien de temps.

## Identités

### Utilisateurs

Chaque utilisateur possède :

- un identifiant unique ;
- des rôles ;
- des permissions ;
- des groupes.

### Services

Les services système possèdent leur propre identité.

Ils ne doivent pas utiliser les privilèges administrateur par défaut.

### Modules

Chaque module possède une identité indépendante.

Le système suit précisément :

- ses permissions ;
- ses ressources ;
- ses communications IPC.

## Modèle de Permissions

Les permissions sont accordées par ressource.

Exemples :

- lecture ;
- écriture ;
- exécution ;
- administration ;
- partage ;
- supervision.

Les permissions peuvent être :

- permanentes ;
- temporaires ;
- conditionnelles.

## Sandboxing

### Applications

Les applications sont exécutées dans des environnements isolés.

Par défaut :

- aucun accès matériel ;
- aucun accès aux données d'autres applications ;
- aucun accès administratif.

### Modules

Les modules fonctionnent dans des espaces contrôlés.

Leur accès aux ressources est limité aux permissions déclarées.

## Signature Numérique

### Modules

Les modules peuvent être signés.

La signature permet :

- l'identification de l'auteur ;
- la verification de l'intégrité ;
- la validation de l'origine.

### Mise à jour

Les mises à jour officielles doivent être vérifiées avant installation.

Le système peut refuser une mise à jour invalide ou corrompue.

## Contrôle IPC

Toutes les communications IPC sont soumises à validation.

Le système vérifie :

- l'identité de l'émetteur ;
- les permissions ;
- les ressources concernées.

Les messages non autorisés sont rejetés.

## Audit

Le système maintient des journaux de sécurité.

Exemples :

- connexions ;
- élévations de privilèges ;
- accès aux ressources ;
- chargements de modules ;
- violations de permissions.

## Récupération

En cas d'incident :

- démarrage sécurisé ;
- mode récupération ;
- rollback ;
- désactivation de modules défaillants.

doivent être disponibles.

## Compatibilité

Les couches de compatibilité Linux et Windows doivent respecter les règles de sécurité Northstar.

Aucune application externe ne peux contourner le modèle de sécurité du système.

## Niveaux de Confiance

Les composants sont classés selon les différents niveaux de confiance.

### Niveau 0

Noyau.

### Niveau 1

NSM et services critiques.

### Niveau 2

Modules système.

### Niveau 3

Applications utilisateur.

### Niveau 4

Applications non vérifiées ou expérimentales.

## Objectif Long Terme

Créer un système où la sécurité est intégrée à chaque couche de l'architecture.

La protection du système ne doit jamais dépendre uniquement de comportement de l'utilisateur.
