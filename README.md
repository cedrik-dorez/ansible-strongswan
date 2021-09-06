Role Strongswan
===============

Un role pour automatiser la creation de tunnels VPN IPsec en utilisant la solution OpenSource Strongswan

Prerequis
----------

Tester sur les distribution Ubuntu 20.04 (focal) et Debian 10 (buster) avec le protocole IPv4

Variables de role
-----------------

Les variables de connections **ipsec_vpn_xxxx** sont déclarer dans le fichier defaut/main.yml et peuvent etre facilement surcharger en ligne de commande ou dans les differents emplacements de variables tes que group/variables.yml ou hosts/variables.yml.

Le secret a partager **ipsec_vpn_psk** est declarer dans une variables intermediaire **vault_ipsec_vpn_psk** qui est crypter dans un fichier specifique creer avec la commande ansible-vault, ce fichiers peut etre placer dans les group_vars ou les host_vars.


Exemple de Playbook
----------------

On creer les fichiers playbook.yml :

```
---
  - name: Mon Playbook
    hosts: ipsecsrv
    become: yes
    roles:
      - Ansible-strongswan

```
et inventaire.yml

```
all:
  children:
    ipsecsrv:
      hosts:
        node1:
        node2:
        node3:
```

On stipule ainsi le(s) host(s) sur lequelles sera jouer le playbook.

Puis on utilise la commande ansible-playbook -K --ask-vault-pass -i inventaire.yml playbook.yml.

L'option -K stipule le mot de passe SUDO pour avoir des droit utilisateurs elevés.

L'option --ask-vault-pass est pour donner le mot du passe du vault qui contient notre secret partagé.

License
-------

BSD

Information sur l'Auteur
------------------------

cedrik.dorez@gmail.com

