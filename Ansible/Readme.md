# Estudos sobre Ansible
![Ansible](https://datascientest.com/en/wp-content/uploads/sites/9/2023/11/ansible.webp)

Primeiramente e recomendado ter um servidor central, para poder gerenciar os demais servidores.


## 📌 Instalando o Ansible

Esse processo pode mudar de acordo com a distribuição linux escolhida, para mais opções, segue o link da documentação oficial.

![Documentação](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-specific-operating-systems)

```
apt install ansible
```
Comando utilizando para fazer a instalação do Ansible
```
apt install epel-release
```
Caso não encontre o pacote do ansible para instalação, instale o epel-release, e atualize os repositorios.


## ⚙️ Estrutura do Ansible

*Control Node*: Servidor central onde as configurações do ansible são armazenadas e onde ocorre a propagação dos comandos para os demais servidores.

*Managed Nodes*: Cada um dos seus servidores que estão sendo gerenciados em sua infraestrutura.

*Inventario* : Lista das maquinas que vão ser gerenciadas normalmente colocamos o IP das maquinas.

*Modulos*: Os módulos no Ansible são pequenos programas que executam tarefas específicas, como instalar pacotes, copiar arquivos ou reiniciar serviços.

*Tasks*: Cada task utiliza um módulo, que é um pequeno programa que executa uma tarefa específica, como instalar pacotes ou copiar arquivos.

*Play*: Onde são agrupadas as tasks.

*Playbook*: Playbooks no Ansible são como listas de instruções para dizer ao Ansible o que fazer em seus servidores. Eles são escritos em YAML e contem de forma organizada as roles (tasks)

**Comandos ad-hoc**

Os comandos ad-hoc permitem executar tarefas sem precisar escrever um playbook. Eles são muito úteis quando você simplesmente precisa fazer uma ou duas coisas de maneira rápida e frequente para muitos servidores.

*Estrutura do comando*

```
ansible [all/grupo] -i [Hosts/inventario] -m [Modulo]
```

**ansible.cfg**

O ansible.cfg é um arquivo de configuração usado para ajustar o comportamento padrão do Ansible. Ele fornece configurações para coisas como diretórios de inventário, usuários remotos, configurações de SSH, entre outros.

Exemplo:
```
[defaults]
inventory = /caminho/para/seu/inventario
remote_user = seu_usuario
transport = ssh
host_key_checking = false
nocows = 1

```


**Roles**

Uma role no Ansible é como um conjunto organizado de tarefas. Em vez de colocar todas as suas tarefas diretamente em um playbook, você pode criar uma role para agrupar funcionalidades relacionadas. Pense em uma role como um "pacote de ações" que você pode reutilizar em diferentes playbooks.

Utilizamos o comando abaixo para facilitar a criação da estrutura da role, também podemos utilizar roles disponibilizadas diretamente da comunidade.

```
ansible-galaxy init
```

**Comandos de verificação**

Como sabemos os arquivos .ymal são muito criteoriosos quanto sua identação, assim podendo gerar bastante confusão ou erros, para minimizar esse problemas, podemos conferir se a Syntax dos nossos arquivos estão corretos, antes de executalos.

```
ansible-playbook playbook.yml  --syntax-check
```

Além de testar a syntax, podemos simular nosso playbook sem aplicar as mudanças de fato, como se fosse um "ambiente de teste".

```
ansible-playbook playbook.yml -C
```

⌨️ com ❤️ por [Elias Assunção](https://github.com/Hooligam) 🔥