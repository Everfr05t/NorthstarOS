# Northstar OS - Décisions Techniques Fondamentales

## Firmware Supporté

Northstar OS prend en charge :

- UEFI ;
- BIOS Legacy.

L'objectif est de permettre l'exécution du système sur du matériel moderne comme sur du matériel plus ancien.

L'architecture du processus de démarrage doit être conçue dès l'origine afin de permettre la coexistence de ces deux modes.

## Langages de Développement

Le projet privilégie Rust comme langage principal.

Objectifs :

- sécurité mémoire ;
- fiabilité ;
- maintenabilité ;
- performances.

Rust est utilisé pour :

- le noyau ;
- les services système ;
- les modules ;
- les outils officiels.

## Compatibilité avec d'autres Langages

L'utilisation de composants en C ou C++ reste possible lorsque cela apporte un avantage technique ou facilite l'intégration de bibliothèques existantes.

Ces composants doivent cependant rester minoritaires dans l'architecture du projet.

## Orientation Technique

À long terme, Northstar OS vise une architecture majoritairement Rust.

Les nouveaux développements doivent privilégier Rust lorsque cela est raisonnablement possible.