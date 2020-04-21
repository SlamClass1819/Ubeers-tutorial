# ubeers-tutorial




 
 
###Installation et Config de Mongodb sur WSL/linux ###

[Installation](https://github.com/michaeltreat/Windows-Subsystem-For-Linux-Setup-Guide/blob/master/readmes/installs/MongoDB.md)

*1.* Créer un répertoire de destination de la DB (data + db) 

>
>```mkdir /home/data/db```
>

*2.* Ajout d’un répertoire pour le path 

>
>```export PATH=$PATH:/chemin/vers/le/répertoire``` 
>

*3.* On indique le chemin vers le fichier de l’install mongo 

>```export PATH=$PATH:/home/usr/opt/mongodb-linux-x86_64-ubuntu1804-4.2.3/bin/``` 
>
*4.* Sinon si le mongo n’est pas dans le path, toutes les commandes devront être précédées par le chemin vers le fichier d’installation) 

>```usr/opt/mongodb-linux-x86_64-ubuntu1804-4.2.3/bin/mongod``` 
 
*5.* On indique au daemon mongo le dossier vers lequel placer la base de données.

>```mongod --dbpath /home/data/db```  


## Installation et lancement de Ghost
>Tout ce passe [ICI](https://github.com/SlamClass1819/ubeers-ghost-content)


## Récupération répo et lancement serveur de: ubeers-strapi ##


1. Fork du rep de [ubeers-strapi](https://github.com/TonyCois/ubeers-strapi)
1. git clone
1. ```npm install``` du package.json > rep ubeers-strappi
1. ```npm run develop```
1. ```mongorestore data/dump```
1. ```npm run develop```

## Récupération répo et lancement serveur de: ubeers-gatsby ##

1. Fork du du rep de [ubeers-strapi](https://github.com/TonyCois/ubeers-gatsby)
1. git clone
1. ```npm install``` du package.json > rep ubeers-gatsby
1. connexion to http://localhost:2368/ghost/ ajout de new custom integration et copy de l' API content key
1. copy de la content key into  gatsby-config.js
1. ```npm run develop```

