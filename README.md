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

10.
