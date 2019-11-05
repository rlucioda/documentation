# Documentos relacionados ao banco de dados

## Instalação do MySQL 5.7 com Vagrant

Vagrant é um utilitário de linha de comando que disponibiliza ferramentas para administrar softwares de máquinas virtuais, como por exemplo o virtualbox. Você pode encontrar mais detalhes sobre o Vagrant na documentação. Clique no link installation, se tiver dúvidas quanto a sua instalação.

Eu escrevi um script que está disponível no github. Ele cria uma máquina virtual usando centos 7 e instala o mysql 5.7 nela:

git clone https://github.com/altmannmarcelo/mysql-vagrant.git
cd mysql-vagrant
vagrant up
vagrant ssh mysql57
mysql
Se você olhar nos arquivos que foram clonados do git, vai ver um arquivo chamado bootstrap.sh. Este arquivo vai configurar o repositório do mysql, instalar o pacote do mysql 5.7 e resetar o password do usuário root.

## Sites

https://www.barrykooij.com/connect-mysql-vagrant-machine/

https://nandovieira.com.br/usando-o-vagrant-como-ambiente-de-desenvolvimento-no-windows

https://www.digitalocean.com/community/tutorials/como-criar-um-novo-usuario-e-conceder-permissoes-no-mysql-pt
