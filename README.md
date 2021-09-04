Role Strongswan
===============

Un role pour automatiser la creation de tunnels VPN IPsec en utilisant la solution OpenSource Strongswan

Prerequis
----------

Tester sur les distribution Ubuntu 20.04 (focal) et Debian 10 (buster) avec le protocole IPv4

Variables de role
-----------------



Exemple de Playbook
----------------

Avec un editeur de texte on creer le fichier playbook.yml puis on lui insere les lignes suivantes:

  - name: Mon Playbook
    hosts: ipsecsrv
    become: yes
    roles:
      - Ansible-strongswan 

On stipule le(s) host(s) sur lequelles sera jouer le playbook ainsi qu'une elevation des droits en root.

On designe ensuite le nom du roles contenant les différends fichiers YAML.

Puis on utilise la commande ansible-playbook -K --ask-vault-pass playbook.yml 

L'option -K stipule le mot de passe SUDO pour avoir des droit utilisateurs elevés.

L'option --ask-vault-pass est pour donner le mot du passe du vault qui contient notre secret partagé. 

License
-------

BSD

Information sur l'Auteur
------------------------

cedrik.dorez@gmail.com

