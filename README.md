# 3-Tier .NET & MongoDB Application

Ce projet est une application web **3-tiers** développée avec **.NET** et **MongoDB**.  
L’application est composée de :

- une **couche de présentation**  
- une **couche de logique métier**  
- une **couche d’accès aux données**  

**MongoDB** est utilisé comme base de données pour stocker et gérer les données de l’application.

---

## Table des matières

- [Prérequis](#prérequis)
- [Installation](#installation)
  - [1. Installation du SDK et du Runtime .NET](#1-installation-du-sdk-et-du-runtime-net)
  - [2. Installation de MongoDB](#2-installation-de-mongodb)
  - [3. Configuration de MongoDB](#3-configuration-de-mongodb)
- [Exécution de l’application](#exécution-de-lapplication)
- [Utilisation du Shell MongoDB](#utilisation-du-shell-mongodb)


---

## Prérequis

Avant de configurer le projet, assurez-vous d’avoir installé les éléments suivants sur votre machine :

- Ubuntu (ou une autre distribution Linux compatible)
- [.NET SDK 8.0](https://dotnet.microsoft.com/download/dotnet/8.0)
- [MongoDB 7.0](https://www.mongodb.com/try/download/community)

---

## Installation

### 1. Installation du SDK et du Runtime .NET

Pour installer le SDK et le Runtime .NET, exécutez les commandes suivantes dans votre terminal :

#### 1️⃣ Installer le SDK .NET 8.0

```bash
sudo apt-get update && \
sudo apt-get install -y dotnet-sdk-8.0
   ```
     2️⃣ Installer le Runtime ASP.NET Core 8.0
sudo apt-get update && \
sudo apt-get install -y aspnetcore-runtime-8.0

2. Installation de MongoDB
1️⃣ Ajouter la clé GPG et le dépôt MongoDB

curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
--dearmor

   ```bash
   echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
   ```

2. **Installer MongoDB:**

   ```bash
   sudo apt update
   sudo apt install -y mongodb-org
   ```

3. **Activer et démarrer MongoDB service:**

   ```bash
   sudo systemctl enable mongod
   sudo systemctl start mongod
   ```

### 3. Configuration de MongoDB

1. **Installer MongoDB Shell:**

   Suivre le guide d'installation [MongoDB Shell Installation](https://www.mongodb.com/docs/mongodb-shell/install/).

2. **Acceder au MongoDB Terminal:**

   Pour intéragir avec MongoDB instance, il faut ouvrir le shell MongoDB:

   ```bash
   mongosh
   ```

3. **Manipuler la base de données et les Collections:**

   - Show databases:

     ```bash
     show dbs;
     ```

   - Use a specific database:

     ```bash
     use db_name;
     ```

   - Show collections in the database:

     ```bash
     show collections;
     ```

   - Query the `Products` collection:

     ```bash
     db.Products.find().pretty();
     ```

## Lancer l'Application

Pour lancer l'application .NET:

1. **Se rendre au répertoire racine ou se trouve Program.cs**

2. **Builder l'application:**

   ```bash
   dotnet build
   ```

3. **Lancer l'application:**

   ```bash
   dotnet run
   ```

   L'application va démarrer, et on peut y acceder sur notre navigateur.

## Utilisation du MongoDB Shell


1. **Lancer le shell:**

   ```bash
   mongosh
   ```

2. **Exemple de commande shell:**

   - **Lister les bases de données:**

     ```bash
     show dbs;
     ```

   - **Changer de base de données:**

     ```bash
     use db_name;
     ```

   - **Voir les collections dans la base de données:**

     ```bash
     show collections;
     ```

   - **Trouver les elements de la collection:**

     ```bash
     db.Products.find().pretty();
     ```
     
     ## Pourquoi utiliser cette application

Cette application 3-tiers .NET & MongoDB permet de :

- Structurer un projet web avec une séparation claire des responsabilités (présentation, logique métier, accès aux données)
- Travailler avec une base de données NoSQL performante et flexible
- Fournir un exemple concret d’intégration entre .NET et MongoDB
- Servir de point de départ pour vos projets professionnels ou d’apprentissage
- Apprendre à **compiler et construire un projet .NET** grâce au processus de build intégré



