# UBEERS-TUTORIAL



### *Pré-requis* ###
* une clé ssh publique 
* un compte [github](https://github.com/)
* un compte [gitlab](https://gitlab.com/)
 
### *mise à jour d'un repo fork* ###
* Update de votre [repo](https://rick.cogley.info/post/update-your-forked-repository-directly-on-github/) 

### *Installation et Config de Mongodb sur WSL/linux* ###

[Installation](https://github.com/michaeltreat/Windows-Subsystem-For-Linux-Setup-Guide/blob/master/readmes/installs/MongoDB.md)

>*1.* Créer un répertoire de destination de la DB (data + db) 
>
>```mkdir ~/data/db```
>

>*2.* Ajout d’un répertoire pour le path 
>
>```export PATH=$PATH:/chemin/vers/le/répertoire``` 
>

>*3.* On indique le chemin vers le fichier de l’install mongo 
>
>```export PATH=$PATH:/home/usr/opt/mongodb-linux-x86_64-ubuntu1804-4.2.3/bin/``` 
>

>*4.* Si le mongo n’est pas dans le path, toutes les commandes devront être précédées par le chemin vers le fichier d’installation) 
>
>```usr/opt/mongodb-linux-x86_64-ubuntu1804-4.2.3/bin/mongod``` 
 
> *5.* On indique au daemon mongo le dossier vers lequel placer la base de données.
>
>``sudo mongod --dbpath ~/data/db``  






## *Installation et lancement de Ghost*
>Suivre le  [README](https://github.com/TonyCois/ubeers-ghost-content) de Tony


## *Récupération répo et lancement serveur de: ubeers-strapi* ##


>1. Fork du rep de [ubeers-strapi](https://github.com/TonyCois/ubeers-strapi)
>1. git clone
>1. ```npm install``` du package.json > rep ubeers-strappi
>1. ```npm run develop```
>1. ```mongorestore data/dump```
>1. ```npm run develop```

Si problème de droits lors du lancement de strapi:

``error Bootstrap function in plugin "users-permissions" failed``
 
* Lancer ``mongo``

* Se connecter à la bdd -> `use bzh-beers`

* db.dropDatabase()

* refaire le ``mongorestore dump`` dans le repertoire ```/data``` de ubeers-strapi

* relancer ``npm run develop``

## *Récupération répo et lancement serveur de: ubeers-gatsby* ##

>1. Fork du du rep de [ubeers-strapi](https://github.com/TonyCois/ubeers-gatsby)
>1. git clone
>1. ```npm install``` du package.json > rep ubeers-gatsby
>1. connexion to http://localhost:2368/ghost/ ajout de new custom integration et copy de l' API content key
>1. copy de la content key into  gatsby-config.js
>1. ```npm run develop```

## *Récupération data de strapy et de ghost dans le GraphQl de Gatsby* ##
>* Datas Ghost suivre le [README](https://github.com/TonyCois/ubeers-gatsby/tree/step-1-1) de Tony 
>* Datas de Strapi suivre le [README](https://github.com/TonyCois/ubeers-gatsby/tree/step-2-2) de Tony

## *Déploiement de Strapi sur Clever Cloud* ##
* Suivre le [README](https://github.com/TonyCois/ubeers-deploy/blob/master/clevercloud/strapi.md) de Tony

## *Déploiement de Ghost sur Clever Cloud* ##
* Suivre le [README](https://github.com/TonyCois/ubeers-deploy/blob/master/clevercloud/ghost.md) de Tony

## *Déploiement de Gatsby sur Clever Cloud* ##
*  Suivre le [README](https://github.com/TonyCois/ubeers-deploy/blob/master/clevercloud/gatsby.md) de Tony
*  Déploiement de Gatsby without ghost suivre le [README](https://github.com/TonyCois/ubeers-gatsby/tree/step-2-8-without-ghost) de Tony et faire un checkout de la Step-2-8-without-ghost pour récupérer les modifs du ``config.js`` et du code relatif à Ghost.
 suivi d'un petit ``npm install``  et retour sur [README](https://github.com/TonyCois/ubeers-deploy/blob/master/clevercloud/gatsby.md) de Tony sans tenir compte des ajouts de variables pour ghost.