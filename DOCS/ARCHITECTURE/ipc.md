# Northstar OS - Communication Inter-Processus (IPC)

## Philosophie

Northstar OS utilise un système IPC centralisé.

Toutes les communications entre :

- processus ;
- services ;
- modules ;
- composants système ;

doivent transiter par l'infrastructure IPC du système.

Aucune communication directe entre modules ne doit être considérée comme standard.

## Objectifs

Le système IPC doit fournir :

- sécurité ;
- isolation ;
- observabilité ;
- modularité ;
- compatibilité.

## Architecture

```
   Module A
      │ 
      ▼ 
+-------------+ 
| IPC Manager | 
+-------------+ 
      │ 
      ▼
   Module B
```

Le gestionnaire IPC agit comme intermédiaire unique.

## Types de Messages

### Requête

Un composant demande une action.

Exemples :

- lecture de données ;
- accès à un périphérique ;
- chargement d'un module

### Réponse

Retour d'une requête

### Événement

Notification système.

Exemples :

- périphérique connecté ;
- module chargé ;
- erreur critique.

### Diffusion

Message envoyé à plusieurs destinataires.

Exemples :

- arrêt système ;
- changement de configuration.

## Permissions

Chaque message IPC est soumis à vérification.

Le système valide :

- l'identité de l'émetteur ;
- les permissions ;
- le type d'opération demandé.

## Journalisation

Le système peut enregistrer les communications IPC.

Objectifs :

- débogage ;
- audit ;
- sécurité ;
- diagnostic.

## Modules

Les modules doivent exposer leurs fonctionnalités via des interfaces IPC documentées.

Les dépendances implicites doivent être évitées.

## Services

Les services système utilisent également l'IPC.

Exemples :

- gestionnaire réseau ;
- gestionnaire de paquets ;
- serveur graphique.

## Compatibilité

Les couches de compatibilité Linux et Windows utiliser l'infrastructure IPC Northstar.

Aucun mécanisme parallèle ne doit être introduit sans justification technique majeure.

## Objectif Long Terme

Faire de l'IPC la colonne vertébrale du système.

Tout composant Northstar doit pouvoir communiquer de manière standardisée, sécurisée et observable.