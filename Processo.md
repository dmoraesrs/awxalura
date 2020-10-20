# Execução

## 1. Servidores

**2 VMS**

### Webserver
* Ubuntu Server 18.04
* Ansible 2.9
* Docker
* Awx
* hostname (dbserver01)
* Mariadb
* ssh-key private

### db-server
* CentOs 7
* Docker
* Apache+PHP(docker)
* ssh-key pub
* hostname (web01)

## 2. Conexões 
1. Gerar Chave SSH.
2. Trocar Chaves entre os servidores.
3. Validar Acessos.

## 3. Tarefas
1. Adicionar Ansible Repositório Apt.
2. Atualizar repositórios.
3. Instalar Pacotes servidor **dbserver01**:

   * Ansible
   * git

4. Criar playbook simples para testar a execução.
5. Testar execução do playbook nos servidores via linha de comando
6. Apresentar o projeto
7. Criar repositório [https://github.com/](github).
8. Configurar ssh no git.
9. Realizar o clone do projeto.

## 3. 
1. Criando playbook Awx.
2. Instalando o Awx
3. Configurar(Usuarios, key ssh, servidores, variaveis.
4. Executar playbook Awx

## 4. 
1. Criar roles(webserver e dbserver)
2. Definir my.cf(mariadb)
3. Parameros de  segurança.
4. Configurar repo git no awx
5. Fazer upload para o git e galaxy
 
## 5.
1. Definir variaveis para execução dos playbooks.
2. Validar Facts

## 6.
1. Encriptar os dados sensiveis (my.cnf)
2. Cadastrar no awx o vault
3. Executar playbook com o vault
