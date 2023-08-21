install-docker-desktop-linux
=========

Role do Ansible com os passos para a instalação do Docker CE em distribuições Linux.

Distribuições Suportadas pela Role
------------

- Fedora 37 ou superior
- Linux Mint 21 ou superior
- Ubuntu 22.10 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
  
- repo: Inclui todos os repositórios da role no Sistema.
- deps: Instala os pacotes de dependências.

- docker: Instala o Docker.
- docker-fix: Aplica algumas correções no SO após instalar o Docker.


Dependências da Role 
--------------

Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - install-docker-desktop-linux


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "docker" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, docker"


License
-------

MIT