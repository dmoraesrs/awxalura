# Requisitos
Como editor dos códigos que iremos criar utilizaremos o [vscode](https://code.visualstudio.com/), mas pode ser utilizado outro editor de sua preferencia.

Como virtualizador iremos utilizar o [virtualbox](https://www.virtualbox.org/) mas pode ser utilizado outro virtualizador de sua preferencia.

Para versionador utilizaremos o [https://github.com/](github) e ferramenta de linha de comando o git.

# Inicio

Para iniciar o projeto iremos inicialmente criar nosso repositório no github.

Vamos acessar o endereço: https://github.com/ caso você não tenha uma conta crie, porque será necessario para o projeto. Após o acesso vamos criar um repositório chamado: **projetoansiblealura** conforme a imagem:

![Repositório](https://github.com/dmoraesrs/images/blob/master/git.png)

Após a criação do nosso repositório vamos clonar ele para nosso computador com o comando git clone:

Para clonarmos o nosso repo devemos pegar a url do mesmo, para pegar a url você deve ir botçao code e selecionar o método ou **https** ou **SSH**.
![Tipo Clone](https://github.com/dmoraesrs/images/blob/master/git2.png)

Copiando a URL vamos fazer o clone:

![Clone](https://github.com/dmoraesrs/images/blob/master/git3.png)

# Pre-Requisitos

1. COnfiguração de Chaves SSH.

Para isso devemos criar nossa chave ssh e realizar a troca de chaves entre os servidores:

ssh-keygen

Abaixo o resultado da execução do comando.
![comando](https://github.com/dmoraesrs/images/blob/master/ssh.png)

Para realização da troca de chaves necessitamos que o usuario exista nos dois servidores. A copia deverá ser realizada atraves do comando:

ssh-copy-id -i /home/sshuser/.ssh/id_rsa.pub sshuser@ipdoservidor

2. Instalaçãop do Awx

Será apresentado o projeto Awx para o que o aluno tenha a referencia do projeto para estudo: 

Para a instalação do [awx](https://github.com/ansible/awx) há o playbook setup-awx.yml o mesmo poderá ser executado chamando o arquivo de inventário que será criado dinamicamente no path: /tmp/awx/installer/inventoryng.

Sintaxe de execução:

ansible-playbook -i hosts setup-awx.yml


# Projeto

A estrutura do projeto será composta de 2 servidores com funções dstintas cada, um com função de Banco de dados e outro com a função de webserver. O hypervisor que sera utilizado será o virtualbox.

![Projeto](https://github.com/dmoraesrs/images/blob/master/Captura%20de%20tela%20de%202020-10-16%2014-13-37.png)

Para o servidor de Webserver utilizaremos a versão do linux CentOs 7.
Para o servidor de banco de dados utilizaremos a versão do linux Ubuntu 18.04.

Para a configuração dos serviços de webserver e banco de dados serão crido duas roles conforme a baixo:

* role webserver: Neste serviço será utilizado o **Apache** com modulos PHP.

* role db-server: Neste serviço será utilizado o **MariaDB**.


É um comando para gerenciar funções Ansible em repositórios compartilhados, o padrão dos quais é Ansible Galaxy https://galaxy.ansible.com. No nosso caso iremos utilzar ele para a criação de nossas roles, com o proposito de manter o padrão estrutural dos diretórios garantindo as boas práticas.

Para a criação destas roles utilizaremos o **ansible-galaxy** com a sintaxe abaixo:

**ansible-galaxy init webserver**

**ansible-galaxy init db-server**

Após a criação das roles será demonstrado a estrutura dos diretórios e explicado suas funcões.


## **Variveis**

Para variaveis utilizaremos facts e variveis com definições de Url, parametros de configuração.

**ansible_facts['distribution'] == "CentOS"**
**ansible_facts['distribution'] == "Ubuntu"**


## Ansible-Vault

Na camada de seguraça utilizaremos o ansible-vault para criptografia dos dados onde serão criptografado os itens:

**Senhas de banco de dados.**


**my.cnf**


**arquivos de configuraçao do wordpress.**





