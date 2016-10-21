Lab6

Travail individuel
Compte pour 2 points
Remettre avant la fin du cours du 21 octobre
Installation

Copier tout le contenu du lab 5 dans ce repository (sans le dossier cach� .git)
Faire un commit et synchroniser
Objectif

Ex�cuter un conteneur sur TravisCi qui d�marre les tests unitaires associ�s � une app web .net core
�tapes

Ex�cution du conteneur en local

Le dossier /src doit contenir les deux dossiers suivants :
appweb: Code source de l'application web
appweb.unittests: Code des tests unitaires. Pour cr�er un projet de tests, utiliser dotnet new -t xunittest. Remplacer le fichier Tests.cs par celui-ci.
Ajouter au fichier project.json du projet appweb.unittests la d�pendance au projet webapp.
Tester l'ex�cution des tests en local. Les tests doivent passer.
Faire les modifications n�cessaires pour que les tests unitaires s'ex�cutent avec l'instruction docker run -it --rm -v $PWD/packages:/root/.nuget/packages webapp:test.
Si les tests passent dans le conteneur alors faire un commit est synchroniser sur GitHub .
Ex�cution du conteneur sur TravisCI

� la racine du repo cr�er le fichier .travis.yml. Ce fichier doit contenir les instructions n�cessaires pour:
Pouvoir construire (docker build ...) l'image docker contenant l'application web et les tests unitaires.
Ex�cuter le conteneur (docker run ...).
Identifier la branche (master) github � aller chercher.
Utiliser une cache pour stocker les packages entre les diff�rents "builds" de Travis.
Configurer sur https://travis-ci.org/ un compte pour que TravisCI puisse ex�cuter le conteneur de tests.
S'assurer que les tests passent sur TracisCI !