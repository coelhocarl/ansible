Role Name
=========

Processo para aplicar todos os Patch em Sistemas Operacionais Linux (CentOS, Debian, SUSE) e Windows (todas as versoes)

Example Playbook
----------------

Conteudo da playbook.yml
    - name: Default Playbook
      hosts: all
      roles:
        - common

Execução da playbook 
  ansible-playbook -i inventory.yml playbook.yml -K


License
-------

BSD

Author Information
------------------

José Carlos C. <github.com/coelhocarl/>