
# angular-cleancode

Mise en place d'outils afin de faciliter la vie d'un développeur Angular.

Le but est de déléguer les tâches de "clean code" à ces outils permettant ainsi au développeur de se concentrer uniquement sur ces tâches.

## ESLint

[![ESLint logo](./Images/eslint.png)](https://eslint.org/  "Redirect to eslint site")

ESLint est un linter permettant d'analyser le code et de vérifier si les règles de syntaxe et de qualité spécifiées par un ensemble de personne sont respectés.

Ce linter, est le plus connu dans le monde du JavaScript/TypeScript pour ses multiples configurations.

## Prettier

[![Prettier logo](./Images/prettier.png)](https://prettier.io/  "Redirect to prettier site")

Le but de prettier est de formater automatiquement le code selon des règles définies.

## Husky

Librairie permettant la création et la gestion des "git hooks" plus facilement.

> Pour information, **un "hook"** est un **script qui s'exécute de manière automatique** lorsqu'un événement se produit. Dans notre cas, les événements proviennent de git.

Nous pouvons ajouter des hooks sur à peut-près sur tous les événements : 

-  applypatch-msg
-   pre-applypatch
-   post-applypatch
-   pre-commit
-   prepare-commit-msg
-   commit-msg
-   post-commit
-   pre-rebase
-   post-checkout
-   post-merge
-   pre-receive
-   update
-   post-receive
-   post-update
-   pre-auto-gc
-   post-rewrite
-   pre-push

Dans notre cas, nous utiliserons les événements **pre-commit** et **pre-push** cf.configuration. Ces événements, sont les plus utilisés. Ils permettent d'assurer au développeur un filet de sécurité visant à maintenir la qualité du code avant d'effectuer les actions de commit et de push sur le serveur.

### Installation

#### 1°) ESLint 
Cet outil, peut être installé soit au global ou au niveau du projet, dans les dépendances de développement *(--save-dev)* . Chaque projet **dispose de règles et d'outils différents**. Pour cela, je vous conseil de **l'installer au niveau du projet.** 

    npm i --save-dev eslint

Comme Angular est un Framework orienté TypeScript, il faut installer un plugin contenant tout un tas de règles spécifiques pour TypeScript.

    npm install --save-dev @typescript-eslint/eslint-plugin

#### 2°) Prettier

    npm i --save-dev prettier prettier-eslint eslint-config-prettier eslint-plugin-prettier

#### 3°) Husky 

    npm i --save-dev husky


### Configuration

#### 4°) ESLint 

##### 4.1°) Ajouter un fichier .eslintrc.json à la racine du projet, puis ajouter cette configuration : 

    {
	  "parser": "@typescript-eslint/parser", // Spécification du parser ESLint
	  "extends": [
	    "plugin:@typescript-eslint/recommended", // Utilisation des règles recommandées hérité de @typescript-eslint/eslint-plugin
	    "prettier/@typescript-eslint", // Utilisation de eslint-config-prettier pour désactiver les règles ESLint héritées de @typescript-eslint/eslint-plugin qui peut être en conflit avec prettier
	    "plugin:prettier/recommended" // Activation de eslint-plugin-prettier et de eslint-config-prettier. Ceci affichera des erreurs provenant de prettier. Soyez sûr que cette configuration soit toujours la dernière configuration de ce tableau d'extension.
	  ],
	  "parserOptions": {
    "ecmaVersion": 2020, // Permet de "parser" les dernières fonctionnalités ECMAScript.
    "sourceType": "module" // Permet d'utiliser les imports
	  },
	  "rules": {
    // Placer ici les règles ESLint. Ils peuvent être utilisées pour surcharger les règles déjà spécifiées dans le tableau d'héritage.
	  }
	}

##### 4.2°) Ajouter un fichier .eslintignore à la racine du projet : 
https://dev.to/dreiv/using-eslint-and-prettier-with-vscode-in-an-angular-project-42ib?signin=true
https://www.alexisjanvier.net/eslint-prettier
https://www.daptontechnologies.com/angular-prettier-husky/
https://www.codeheroes.fr/2020/07/27/git-lutilisation-des-hooks-avec-husky/
