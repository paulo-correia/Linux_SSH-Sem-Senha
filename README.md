# SSH Sem Senha

Requisitos básicos:

Ter o mesmo usuário na máquina cliente e na maquina que deseja acessar (servidor), ambos com a mesma senha.

Definições:

servidor: A máquina que deseja acessar

cliente: A máquina da qual deseja acessar o servidor.

Na máquina **cliente** no terminal como **root** ou como o usuário digite o seguinte comando:

 `ssh-keygen -t rsa`

**Obs:** Não digite nenhuma senha.

Serão gerados dois arquivos **/root/.ssh/id\_rsa** e **/root/.ssh/id\_rsa.pub** ou /home/usuário/.ssh/id\_rsa e /home/usuário/.ssh/id\_rsa.pub  
Entre na pasta com o comando cd (Ex: cd /root/.ssh ou cd /home/usuário/.ssh)

Transfira o arquivo **id\_rsa.pub** para a máquina a qual deseja acessar(servidor) no terminal com o comando:

 `ssh-copy-id -i id_rsa.pub root@servidor ou ssh-copy-id -i id_rsa.pub usuário@servidor`

**Obs:** substitua **cliente** pelo nome ou IP

Digite a senha do **root** ou do usuário da máquina **cliente**

Conecte-se na máquina **servidor** no terminal com o comando:

 `ssh root@servidor ou ssh usuário@servidor`

Digite a senha do usuário **root** da máquina **servidor**

**Obs:** Só será pedida esta senha uma única vez

Adicione a chave privada ao ssh-agent estando logado na máquina cliente com o comando:

 `ssh-add /root/.ssh/id_rsa ou ssh-add /home/usuário/.ssh/id_rsa`

Isto é necessário em caso o usuário não seja o root