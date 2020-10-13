**#####  Pre-Reqs**

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


***