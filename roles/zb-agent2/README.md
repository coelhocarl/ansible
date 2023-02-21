Role Name
=========

Essa role automatiza a instalação e configuração do Agent2 do Zabbix em diferentes sistemas operacionais utilizando o Ansible.

Requirements
------------

O ansible-core e o target windows precisam ser configurados para conexão WinRM e autenticação Kerberos. Saiba como: https://jscarloscoelho.wordpress.com/2023/01/09/configurar-o-ansible-com-winrm-e-kerberos/ 

O ansible-core e os targets linux precism ser configurados para autenticação com chaves ssh, nenhum ajuste, plugin ou modulo adicional foi necessário. Saiba como: <pendente>

Role Variables
--------------

Em dois locais foram atribuídas variáveis. 

inventario.yml - parâmetros de conexão. 
Para Windows: 
ansible_connection: winrm
ansible_winrm_transport: kerberos
ansible_winrm_user: <insert_user>
ansible_winrm_password: <insert_password>

vars/main.yml - define o servidor zabbix, local para os logs do windows, repositório para cada distribuição linux e nome dos pacotes a serem instalados. 

Dependencies
------------

Não são necessários plugins, modulos, bibliotecas ou configurações adicionais. 

Example Playbook
----------------

Conteudo da playbook.yml
    - name: Default Playbook
      hosts: all
      roles:
        - zb-agent2

Execução da playbook 
  ansible-playbook -i inventory.yml playbook.yml -K

License
-------

BSD

Author Information
------------------

José Carlos C. <github.com/coelhocarl/>
