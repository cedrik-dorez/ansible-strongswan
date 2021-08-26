Role Strongswan
===============

Un role pour automatiser la creation de tunnels VPN IPsec en utilisant la solution OpenSource Strongswan

Prerequis
----------

Tester sur les distribution Ubuntu 20.04 (focal) et Debian 10 (buster) avec le protocole IPv4

Variables de role
-----------------

A venir ^^

Exemple de Playbook
----------------

ansible-playbook -K -i inventaire.yml playbook.yml 

L'option -K stipule le mot de passe SUDO pour avoir des droit utilisateurs elevés, par choix je n'ai pas voulu
creer un utilisateur SUDO sans mot de passe ( option NOPASSWD dans le fichier /etc/sudoers )

License
-------

BSD

Information sur l'Auteur
------------------------

cedrik.dorez@gmail.com

