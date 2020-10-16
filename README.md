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

**Como pré-requisito necessitamos realizar a configuração da troca de chaves ssh.

Para isso devemos criar nossa chave ssh e realizar a troca de chaves entre os servidores:

ssh-keygen

Abaixo o resultado da execução do comando.
![comando](https://github.com/dmoraesrs/images/blob/master/ssh.png)

Para realização da troca de chaves necessitamos que o usuario exista nos dois servidores. A copia deverá ser realizada atraves do comando:

ssh-copy-id -i /home/sshuser/.ssh/id_rsa.pub sshuser@ipdoservidor

Para a instalação do AWX há o playbook setup-awx.yml o mesmo poderá ser executado chamando o arquivo de inventário que será criado dinamicamente no path: /tmp/awx/installer/inventoryng. 


A Sintaxe para a execução do playbook devera ser:

ansible-playbook -i hosts setup-awx.yml


# Projeto


### # Ansible Galaxy

É um comando para gerenciar funções Ansible em repositórios compartilhados, o padrão dos quais é Ansible Galaxy https://galaxy.ansible.com. No nosso caso iremos utilzar ele para a criação de nossas roles, com o proposito de manter o padrão estrutural dos diretórios garantindo as boas práticas.


A estrutura do projeto será composta de 2 servidores um com função de Banco de dados e outro com a função de webserver. O hypervisor que sera utilizado será o virtualbox.

![Projeto](https://github.com/dmoraesrs/images/blob/master/Captura%20de%20tela%20de%202020-10-16%2014-13-37.png)

Para o servidor de banco de dados utilizaremos a versão do linux CentOs 7.
Para o servidor de banco de dados utilizaremos a versão do linux Ubuntu 18.04.

Para a configuração dos serviços de webserver e banco de dados serão crido duas roles conforme a baixo:



* role webserver: Neste serviço será utilizado o **Apache** com modulos PHP.
* role db-server: Neste serviço será utilizado o **MariaDB**.

Para a criação destas roles utilizaremos o **ansible-galaxy** com a sintaxe abaixo:


**ansible-galaxy init webserver**


**ansible-galaxy init db-server**




