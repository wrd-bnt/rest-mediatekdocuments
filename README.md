# rest_mediatekdocuments

Ce dépôt présente les fonctionnalités ajoutées à l'API d'origine disponible ici : https://github.com/CNED-SLAM/rest_mediatekdocuments (Le readme de ce dépôt contient la présentation de l'API d'origine, sa structure et comment l'exploiter).

Cette évolution ajoute la gestion de l'authentification des utilisateurs via une nouvelle requête dans MyAccessBDD.php.

## Fonctionnalité ajoutée

### Méthode selectUtilisateur

Une méthode selectUtilisateur a été ajoutée dans MyAccessBDD.php. Elle permet de vérifier les identifiants d'un utilisateur (login et mot de passe) et de récupérer ses informations ainsi que son service d'appartenance.

Cette méthode est appelée par l'application C# MediatekDocuments lors de l'authentification au démarrage.

## L'API en ligne

L'API est déployée sur AwardSpace et accessible via authentification Basic Auth.
Le mode opératoire pour l'utiliser est décrit dans le readme du dépôt d'origine.

## La base de données

Le script SQL se trouve à la racine du dépôt : mediatek86.sql

Les tables ajoutées par rapport à la base d'origine sont : suivi, service, utilisateur. La table commandedocument a été modifiée avec l'ajout de la colonne idSuivi.

## Documentation technique

La documentation technique générée avec phpDocumentor est disponible dans le dossier doc/ du dépôt.

## Installation de l'API en local

### Prérequis

- WampServer ou équivalent
- NetBeans ou équivalent
- Composer
- Postman pour les tests

### Installation

- Cloner ou télécharger le dépôt
- Copier le dossier dans www de WampServer et le renommer rest_mediatekdocuments
- Ouvrir une fenêtre de commandes en mode admin, aller dans le dossier et taper composer install
- Avec phpMyAdmin, créer la base de données mediatek86 et importer le fichier mediatek86.sql
- L'API est accessible à l'adresse : http://localhost/rest_mediatekdocuments/ 

### Test avec Postman

Pour tester l'API avec Postman, configurer l'authentification :
- Onglet **Authorization**
- Type : **Basic Auth**

Les identifiants de connexion sont fournis dans la fiche de réalisation professionnelle.

### Mode opératoire de l'API

Se référer au readme du dépôt d'origine pour le détail complet des requêtes possibles :
https://github.com/CNED-SLAM/rest_mediatekdocuments 
