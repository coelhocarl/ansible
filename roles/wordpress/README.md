Role Name
=========

Essa role baixa, instala e configura o Wordpress em um servidor CentOS 9

Requirements
------------

CentOS 9 instalados com suas configurações padroes. 
Ansible-Core instalado com suas configurações padroes. 
O usuário para execução da playbook precisa ter privilegios de root no target. 

Role Variables
--------------

Defina em vars/main.yml o nome, usuário e senhas para o banco de dados mariadb. 
  db_name: wp_db1
  db_user: wp_db_usr
  db_user_password: P@$$w0rD1
  db_root_password: P@$$w0rD3


Dependencies
------------

Não são necessários plugins ou modulos adicionais. Uma biblioteca é exigida para automatizar a criação do banco de dados, já incluida na role (library/mysql_secure_installation). 

Example Playbook
----------------

Conteudo da playbook.yml
    - name: Default Playbook
      hosts: all
      roles:
        - wordpress

Execução da playbook 
  ansible-playbook -i inventory.yml playbook.yml --limit <server_name> -K


License
-------

BSD

Author Information
------------------

José Carlos C. <github.com/coelhocarl/>