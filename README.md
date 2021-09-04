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

On creer les fichiers playbook.yml 

- name: Mon Playbook
    hosts: ipsecsrv
    become: yes
    roles:
      - Ansible-strongswan  

et inventaire.yml

all:
  children:
    ipsecsrv:
      hosts:
        node1:
        node2:
        node3:  

On stipule ainsi le(s) host(s) sur lequelles sera jouer le playbook.

Puis on utilise la commande ansible-playbook -K --ask-vault-pass -i inventaire.yml playbook.yml.

L'option -K stipule le mot de passe SUDO pour avoir des droit utilisateurs elevés.

L'option --ask-vault-pass est pour donner le mot du passe du vault qui contient notre secret partagé,
ce dernier etant definis en CLI de la maniere suivante:  

License
-------

BSD

Information sur l'Auteur
------------------------

cedrik.dorez@gmail.com

