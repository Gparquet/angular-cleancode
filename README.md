
# angular-cleancode

Mise en place d'outils afin de faciliter la vie d'un développeur Angular.

Le but est de déléguer les tâches de "clean code" à ces outils permettant ainsi au développeur de se concentrer uniquement sur ces tâches.

## ESLint

[![ESLint logo](./Images/eslint.png#center)](https://eslint.org/  "Redirect to eslint site")

ESLint est un linter permettant d'analyser le code et de vérifier si les règles de syntaxe et de qualité spécifiées par un ensemble de personne sont respectés.

Ce linter, est le plus connu dans le monde du JavaScript/TypeScript pour ses multiples configurations.

## Prettier

## Husky

### Installation / Utilisation

Cet outil, peut être installé soit au global ou au niveau du projet, dans les dépendances de développement *(--save-dev)* . Chaque projet **dispose de règles et d'outils différents**. Pour cela, je vous conseil de **l'installer au niveau du projet.** 

    npm i eslint --save-dev

Comme Angular est un Framework orienté TypeScript, il faut installer un plugin contenant tout un tas de règles spécifiques pour TypeScript.

    npm install @typescript-eslint/eslint-plugin --save-dev

Création d'un fichier de configuration permetant de
https://dev.to/dreiv/using-eslint-and-prettier-with-vscode-in-an-angular-project-42ib?signin=true
https://www.alexisjanvier.net/eslint-prettier
https://www.daptontechnologies.com/angular-prettier-husky/
