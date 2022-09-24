# tp-3-yanis692
tp-3-yanis692 created by GitHub Classroom

## Exercice 1. Gestion des utilisateurs et des groupes

1. ![image](https://user-images.githubusercontent.com/77662970/190976354-cfa0ac38-d0ac-452d-a35b-80e9521437a8.png)


2. ![image](https://user-images.githubusercontent.com/77662970/190975835-af5b72f7-af60-4127-88e5-e31f438974b0.png)


3.  ![image](https://user-images.githubusercontent.com/77662970/190977140-56ddd0e8-f81d-4595-965a-270b6cfcf60b.png)


4. La commande cat /etc/group nous permet de voir les groupes et leurs membres.

![image](https://user-images.githubusercontent.com/77662970/190978228-34520b39-6bf5-4425-a6db-297cb7840668.png)

La commande getent group infra nous permet de nous afficher que le groupe infra et les membres.

![image](https://user-images.githubusercontent.com/77662970/190978491-98657183-c63c-497d-a8c2-49dac28a83c0.png)

5. La commande chgrp dev /home/alice et /home/bob nous permet de faire le groupe dev de alice et bob le groupe propriétaire. La commande chgrp infra /home/charlie et /home/dave permet de faire le groupe infra le groupe propriétaire.

6. Pour remplacer le groupe primaire il faut utiliser la commande sudo usermod -g infra dave/ infra charlie/ dev alice/ dev bob.

7. On peut se rendre dans le répertoire home pour ensuite éxécuter la commande suivantes sudo mkdir dev infra.

8. On fait sudo chmod +t infra/infra pour que seule seul le propriétaire d’un fichier ait le droit de renommer
ou supprimer ce fichier.

![image](https://user-images.githubusercontent.com/77662970/190992187-ca654cfe-dda0-4d57-9945-9915dffdff7f.png)

9. On ne peut pas avoir accées a la sessions car aucun mot de passe a été rentrer pour alice et donc sa session est inactif.

10.Nous pouvons accéder a alice après avoir crée un mot de passe

![image](https://user-images.githubusercontent.com/77662970/191008031-d0f5bbda-2016-4ff7-b63a-88bbf305cf4e.png)


11.On obtien l’uid et le gid avec la commande 

![image](https://user-images.githubusercontent.com/77662970/191009040-63243d65-9142-4325-a308-000014f959bc.png)

12. La commande qui permet de retrouver l’utilisateur dont l’uid est spécifique est 

![image](https://user-images.githubusercontent.com/77662970/191009979-6982c6c8-a7ae-4f22-9635-c6ca9a995f82.png)

13.  La commande pour retrouver l'id d'un groupe spécifique est 

![image](https://user-images.githubusercontent.com/77662970/191012796-6d718b0a-6fbf-4f7b-a1df-699750803c1f.png)


14. Le group dont le gid est 1002 est: 

![image](https://user-images.githubusercontent.com/77662970/191013760-02898255-2e63-4e8c-9ec6-2c09533d7635.png)


15.L'utilisateur charlie supprimer du groupe infra : charlie n'aura plus l'accées au dossier infra.

![image](https://user-images.githubusercontent.com/77662970/191017926-adc4b1c3-5c52-4e51-9554-481a8a0cba6d.png)

16.
![image](https://user-images.githubusercontent.com/77662970/191021099-2655812b-c6ef-4884-99db-1acca0bb237b.png)

17. L'intérpréteur de rott est bash :
![image](https://user-images.githubusercontent.com/77662970/191021657-3a60a6b9-bd69-4a9e-ba16-2213cc556531.png)

18. Nobody compte existant : 

![image](https://user-images.githubusercontent.com/77662970/191027677-ba5493ba-e182-420e-a6e3-b35c598ee882.png)

L'utilisateur nobody permet de lancer des démons en tant que nobody, spécialement pour des serveurs, de façon à limiter les dommages qui pourrait être occasionnés par un utilisateur malicieux qui aurait réussi à prendre leur contrôle car celui-ci a aucun fichier n'appartient, qui n'est dans aucun groupe qui a des privilèges et dont les seules possibilités sont celles que tous les "autres utilisateurs" ont.


19. La commande sudo garde le mot de passe 15 minutes en mémoire. La commande sudo -k nous permet de forcer a oublier un mot de passe.


## Exercice 2. Gestion des permissions

1. Les droit pour le dossier test sont :

![image](https://user-images.githubusercontent.com/77662970/191080656-6f49cbbf-001c-4ff7-a545-9bde368dd5f7.png)

Pour le fichier :

![image](https://user-images.githubusercontent.com/77662970/191080770-f04297f3-4449-437c-b2fb-1fa65fd45aad.png)

2. On peut observer que sudo peut lire le fichier :

![image](https://user-images.githubusercontent.com/77662970/191082004-27ae4e52-1262-4d31-a9d1-e2c213a472b8.png)


3. Les droit sont correctement appliquer

4. On ne peut pas éxecuter le fichier car nous avons pas les priviléges nécessaire par rapport a root qui peut lui éxecuter un fichier même ci celui-ci n'est pas éxecutable.

![image](https://user-images.githubusercontent.com/77662970/191086447-af4ebdc8-f82b-45bb-aeb2-906f36e543fe.png)

5. On peut observer que nous ne pouvons pas lire le dossier test mais on peut lire le 'fichier'


![image](https://user-images.githubusercontent.com/77662970/191090028-f1a1d1ad-6d3a-4a40-af9a-5a58c5d5cf88.png)


6. Je ne peut pas modifier le contenue du fichier 'nouveau' puisque j'en ai pas la permission 

![image](https://user-images.githubusercontent.com/77662970/191093842-0c2efcba-05cc-4822-b23b-17414efcdbe8.png)

Je peut supprimer le fichier 'nouveau' maême si les droits d'écriture on était retirer sur le fichier car j'ai toujours le droit d'écriture sur le dossier mere donc je peut supprimer le fichier.

![image](https://user-images.githubusercontent.com/77662970/191094338-853ce950-4ac1-4616-a61a-821666e162f0.png)

7. On peut comprendre que l'on peut éxecuter aucune commande sur le dossier test et son contenu si nous avons pas les droits d'éxecuter sur le dossir.

![image](https://user-images.githubusercontent.com/77662970/191096327-87dd85d3-815e-4800-b134-07931cc634bb.png)


8. Les droits d'un fichier sont separés de ceux d'un dossier c'est a dire que les droits d'xecution d'un dossier n'influent pas sur ceux des fichiers qu'ils contient.

9. Rétablissez le droit en exécution du répertoire test. Attribuez au fichier fichier les droits suffisants pour qu’une autre personne de votre groupe puisse y accéder en lecture, mais pas en écriture.    
```
chmod 740 fichier
```




