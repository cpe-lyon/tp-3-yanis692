# tp-3-yanis692
tp-3-yanis692 created by GitHub Classroom

# Exercice 1. Gestion des utilisateurs et des groupes

## 1. Utilisez la commande groupadd pour créer deux groupes dev et infra
![image](https://user-images.githubusercontent.com/77662970/190976354-cfa0ac38-d0ac-452d-a35b-80e9521437a8.png)
## 2. Créez ensuite 4 utilisateurs alice, bob, charlie, dave avec la commande useradd, en demandant la
création de leur dossier personnel et avec bash pour shell
![image](https://user-images.githubusercontent.com/77662970/190975835-af5b72f7-af60-4127-88e5-e31f438974b0.png)
## 3. Ajoutez les utilisateurs dans les groupes créés :
## - alice, bob, dave dans dev
## - bob, charlie, dave dans infra
![image](https://user-images.githubusercontent.com/77662970/190977140-56ddd0e8-f81d-4595-965a-270b6cfcf60b.png)
## 4. Donnez deux moyens d’afficher les membres de infra
La commande cat /etc/group nous permet de voir les groupes et leurs membres.
![image](https://user-images.githubusercontent.com/77662970/190978228-34520b39-6bf5-4425-a6db-297cb7840668.png)
La commande getent group infra nous permet de nous afficher que le groupe infra et les membres.
![image](https://user-images.githubusercontent.com/77662970/190978491-98657183-c63c-497d-a8c2-49dac28a83c0.png)
## 5. Faites de dev le groupe propriétaire des répertoires /home/alice et /home/bob et de infra le groupe
## propriétaire de /home/charlie et /home/dave
La commande chgrp dev /home/alice et /home/bob nous permet de faire le groupe dev de alice et bob le groupe propriétaire. La commande chgrp infra /home/charlie et /home/dave permet de faire le groupe infra le groupe propriétaire.
## 6. Remplacez le groupe primaire des utilisateurs :
## - dev pour alice et bob
## - infra pour charlie et dave
Pour remplacer le groupe primaire il faut utiliser la commande sudo usermod -g infra dave/ infra charlie/ dev alice/ dev bob.
## 7. Créez deux répertoires /home/dev et /home/infra pour le contenu commun aux membres de chaque
## groupe, et mettez en place les permissions leur permettant d’écrire dans ces dossiers.
On peut se rendre dans le répertoire home pour ensuite éxécuter la commande suivantes ```sudo mkdir dev``` et ```sudo mkdir infra```.
## 8. Comment faire pour que, dans ces dossiers, seul le propriétaire d’un fichier ait le droit de renommer
## ou supprimer ce fichier ?
On fait sudo chmod +t infra/infra pour que seule seul le propriétaire d’un fichier ait le droit de renommer
ou supprimer ce fichier.
![image](https://user-images.githubusercontent.com/77662970/190992187-ca654cfe-dda0-4d57-9945-9915dffdff7f.png)
## 9. Pouvez-vous ouvrir une session en tant que alice ? Pourquoi ?
On ne peut pas avoir accées a la sessions car aucun mot de passe a été rentrer pour alice et donc sa session est inactif.
## 10. Activez le compte de l’utilisateur alice et vérifiez que vous pouvez désormais vous connecter avec son
compte
Nous pouvons accéder a alice après avoir crée un mot de passe
![image](https://user-images.githubusercontent.com/77662970/191008031-d0f5bbda-2016-4ff7-b63a-88bbf305cf4e.png)
## 11. Comment obtenir l’uid et le gid de alice ?
On obtien l’uid et le gid avec la commande 
![image](https://user-images.githubusercontent.com/77662970/191009040-63243d65-9142-4325-a308-000014f959bc.png)
## 12. Quelle commande permet de retrouver l’utilisateur dont l’uid est 1003 ?
La commande qui permet de retrouver l’utilisateur dont l’uid est spécifique est 
![image](https://user-images.githubusercontent.com/77662970/191009979-6982c6c8-a7ae-4f22-9635-c6ca9a995f82.png)
## 13. Quel est l’id du groupe dev ?
La commande pour retrouver l'id d'un groupe spécifique est 
![image](https://user-images.githubusercontent.com/77662970/191012796-6d718b0a-6fbf-4f7b-a1df-699750803c1f.png)
## 14. Quel groupe a pour gid 1002 ? ( Rien n’empêche d’avoir un groupe dont le nom serait 1002...)
Le group dont le gid est 1002 est: 
![image](https://user-images.githubusercontent.com/77662970/191013760-02898255-2e63-4e8c-9ec6-2c09533d7635.png)
## 15. Retirez l’utilisateur charlie du groupe infra. Que se passe-t-il ? Expliquez.
L'utilisateur charlie supprimer du groupe infra : charlie n'aura plus l'accées au dossier infra.
![image](https://user-images.githubusercontent.com/77662970/191017926-adc4b1c3-5c52-4e51-9554-481a8a0cba6d.png)
## 16. Modifiez le compte de dave de sorte que :
## — il expire au 1er juin 2021
## — il faut changer de mot de passe avant 90 jours
## — il faut attendre 5 jours pour modifier un mot de passe
## — l’utilisateur est averti 14 jours avant l’expiration de son mot de passe
## — le compte sera bloqué 30 jours après expiration du mot de passe

![image](https://user-images.githubusercontent.com/77662970/191021099-2655812b-c6ef-4884-99db-1acca0bb237b.png)

## 17. Quel est l’interpréteur de commandes (Shell) de l’utilisateur root ?
L'intérpréteur de root est bash :
![image](https://user-images.githubusercontent.com/77662970/191021657-3a60a6b9-bd69-4a9e-ba16-2213cc556531.png)
## 18. Si vous regardez la liste des comptes présents sur la machine, vous verrez qu’il en existe un nommé
## nobody. A quoi correspond-il ?
Nobody compte existant : 
![image](https://user-images.githubusercontent.com/77662970/191027677-ba5493ba-e182-420e-a6e3-b35c598ee882.png)
L'utilisateur nobody permet de lancer des démons en tant que nobody, spécialement pour des serveurs, de façon à limiter les dommages qui pourrait être occasionnés par un utilisateur malicieux qui aurait réussi à prendre leur contrôle car celui-ci a aucun fichier n'appartient, qui n'est dans aucun groupe qui a des privilèges et dont les seules possibilités sont celles que tous les "autres utilisateurs" ont.
## 19. Par défaut, combien de temps la commande sudo conserve-t-elle votre mot de passe en mémoire ?
## Quelle commande permet de forcer sudo à oublier votre mot de passe ?
La commande sudo garde le mot de passe 15 minutes en mémoire. 
La commande sudo -k nous permet de forcer a oublier un mot de passe.

# Exercice 2. Gestion des permissions

## 1. Dans votre $HOME, créez un dossier test, et dans ce dossier un fichier fichier contenant quelques
## lignes de texte. Quels sont les droits sur test et fichier ?
Les droit pour le dossier test sont :

![image](https://user-images.githubusercontent.com/77662970/191080656-6f49cbbf-001c-4ff7-a545-9bde368dd5f7.png)

Pour le fichier :

![image](https://user-images.githubusercontent.com/77662970/191080770-f04297f3-4449-437c-b2fb-1fa65fd45aad.png)
## 2. Retirez tous les droits sur ce fichier (même pour vous), puis essayez de le modifier et de l’afficher en
## tant que root. Conclusion ?
On peut observer que root a toujours les droits sur le fichier :
![image](https://user-images.githubusercontent.com/77662970/191082004-27ae4e52-1262-4d31-a9d1-e2c213a472b8.png)
## 3. Redonnez vous les droits en écriture et exécution sur fichier puis exécutez la commande echo "echo
## Hello" > fichier. On a vu lors des TP précédents que cette commande remplace le contenu d’un
## fichier s’il existe déjà. Que peut-on dire au sujet des droits ?
On peut modifier le fichier, le lire sans l'utilisateur root. 
## 4. Essayez d’exécuter le fichier. Est-ce que cela fonctionne ? Et avec sudo ? Expliquez
Le fichier est éxécutable car nous avons les droit d'éxécution sur le fichier

## 5. . Placez-vous dans le répertoire test, et retirez-vous le droit en lecture pour ce répertoire. Listez le
## contenu du répertoire, puis exécutez ou affichez le contenu du fichier fichier. Qu’en déduisez-vous ?
## Rétablissez le droit en lecture sur test.
On peut observer que nous ne pouvons pas lire le dossier test mais on peut lire le 'fichier'

![image](https://user-images.githubusercontent.com/77662970/191090028-f1a1d1ad-6d3a-4a40-af9a-5a58c5d5cf88.png)

## 6. Créez dans test un fichier nouveau ainsi qu’un répertoire sstest. Retirez au fichier nouveau et au
## répertoire test le droit en écriture. Tentez de modifier le fichier nouveau. Rétablissez ensuite le droit
## en écriture au répertoire test. Tentez de modifier le fichier nouveau, puis de le supprimer. Que pouvezvous déduire de ## toutes ces manipulations ?
Je ne peut pas modifier le contenue du fichier 'nouveau' puisque j'en ai pas la permission 

![image](https://user-images.githubusercontent.com/77662970/191093842-0c2efcba-05cc-4822-b23b-17414efcdbe8.png)

Je peut supprimer le fichier 'nouveau' maême si les droits d'écriture on était retirer sur le fichier car j'ai toujours le droit d'écriture sur le dossier mere donc je peut supprimer le fichier.

![image](https://user-images.githubusercontent.com/77662970/191094338-853ce950-4ac1-4616-a61a-821666e162f0.png)

## 7. Positionnez vous dans votre répertoire personnel, puis retirez le droit en exécution du répertoire test.
## Tentez de créer, supprimer, ou modifier un fichier dans le répertoire test, de vous y déplacer, d’en
## lister le contenu, etc…Qu’en déduisez vous quant au sens du droit en exécution pour les répertoires ?
On peut comprendre que l'on peut éxecuter aucune commande sur le dossier test et son contenu si nous avons pas les droits d'éxecuter sur le dossir.
![image](https://user-images.githubusercontent.com/77662970/191096327-87dd85d3-815e-4800-b134-07931cc634bb.png)
## 8. Rétablissez le droit en exécution du répertoire test. Positionnez vous dans ce répertoire et retirez lui
## à nouveau le droit d’exécution. Essayez de créer, supprimer et modifier un fichier dans le répertoire
## test, de vous déplacer dans ssrep, de lister son contenu. Qu’en concluez-vous quant à l’influence des
## droits que l’on possède sur le répertoire courant ? Peut-on retourner dans le répertoire parent avec ”cd
##..” ? Pouvez-vous donner une explication ?
Les droits d'un fichier sont separés de ceux d'un dossier c'est a dire que les droits d'xecution d'un dossier n'influent pas sur ceux des fichiers qu'ils contient.
## 9. Rétablissez le droit en exécution du répertoire test. Attribuez au fichier fichier les droits suffisants
## pour qu’une autre personne de votre groupe puisse y accéder en lecture, mais pas en écriture
## Rétablissez le droit en exécution du répertoire test. Attribuez au fichier fichier les droits suffisants pour qu’une autre ## personne de votre groupe puisse y accéder en lecture, mais pas en écriture.    
```
chmod 740 fichier
```
## 10. Définissez un umask très restrictif qui interdit à quiconque à part vous l’accès en lecture ou en écriture,
## ainsi que la traversée de vos répertoires. Testez sur un nouveau fichier et un nouveau répertoire
Définissez un umask très restrictif qui interdit à quiconque à part vous l’accès en lecture ou en écriture, ainsi que la traversée de vos répertoires. Testez sur un nouveau fichier et un nouveau répertoire.

![image](https://user-images.githubusercontent.com/77662970/192113151-05ff51a3-87ea-452e-b5d1-8561c2b79fe4.png)


![image](https://user-images.githubusercontent.com/77662970/192113117-c82871de-0481-45d8-aeb4-2fc00181d4ed.png)
## 11. Définissez un umask très permissif qui autorise tout le monde à lire vos fichiers et traverser vos répertoires, mais n’autorise que vous à écrire. Testez sur un nouveau fichier et un nouveau répertoire.
```
umask 022
```
![image](https://user-images.githubusercontent.com/77662970/194312153-f9c4aed2-bdbe-4672-b355-ecc72cf6d9f5.png)
## 12. Définissez un umask équilibré qui vous autorise un accès complet et autorise un accès en lecture aux
membres de votre groupe. Testez sur un nouveau fichier et un nouveau répertoire.
```
umask 047
```
![image](https://user-images.githubusercontent.com/77662970/194312366-2b18bc6c-e831-453e-83ad-cf7a4cdbcd43.png)
## 13. Transcrivez les commandes suivantes de la notation classique à la notation octale ou vice-versa (vous
pourrez vous aider de la commande stat pour valider vos réponses) :
- chmod u=rx,g=wx,o=r fic = ```chmod 534```
- chmod uo+w,g-rx fic en sachant que les droits initiaux de fic sont r--r-x--- = ```chmod 602 fic```
- chmod 653 fic en sachant que les droits initiaux de fic sont 711 = ```rw-r-x-wx```
- chmod u+x,g=w,o-r fic en sachant que les droits initiaux de fic sont r--r-x--- = ```chmod 520 fic```
## 14. Affichez les droits sur le programme passwd. Que remarquez-vous ? En affichant les droits du fichier
/etc/passwd, pouvez-vous justifier les permissions sur le programme passwd ?
On peut remarquer que seul root peut éxécuter se fichier car se fichier contient dews information plus ou moins sensible sur les utilisateurs.
![image](https://user-images.githubusercontent.com/77662970/194313514-537fd1f4-1c35-4593-8c3c-596964baaf0d.png)



