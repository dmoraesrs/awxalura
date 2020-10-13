**#####  Pre-Reqs**

**Como pré-requisito necessitamos realizar a configuração da troca de chaves ssh.

Para isso devemos criar nossa chave ssh e realizar a troca de chaves entre os servidores:

ssh-keygen

Abaixo o resultado da execução do comando.
![comando](https://github.com/dmoraesrs/images/blob/master/ssh.png)

Para realização da troca de chaves necessitaos que o usuario exista nos dois servidores. A copia deverá ser realizada atraves do comando:

ssh-copy-id -i /home/sshuser/.ssh/id_rsa.pub sshuser@ipdoservidor

***