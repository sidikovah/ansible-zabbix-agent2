# Ansible Zabbix Agent 2

Este repositório contém um playbook Ansible para instalar e configurar o Zabbix Agent 2 em servidores Linux. O Zabbix Agent 2 oferece maior flexibilidade e desempenho em relação ao agente tradicional, além de suporte a novos recursos.

## Requisitos

- Ansible 2.9+ instalado na máquina de controle
- Servidores de destino rodando um sistema operacional Linux
- Acesso SSH aos servidores de destino

## Estrutura do Repositório

- `playbook.yml`: Playbook principal para instalar e configurar o Zabbix Agent 2.
- `hosts.ini`: Arquivo de inventário que define os servidores de destino.
- `roles/`: Diretório contendo as funções Ansible para instalação e configuração do Zabbix Agent 2.

## Uso

1. Clone este repositório para sua máquina local:

    ```bash
    git clone https://github.com/roberto103/ansible-zabbix-agent2.git
    cd ansible-zabbix-agent2
    ```

2. Edite o arquivo `hosts.ini` para adicionar seus servidores de destino e credenciais, exemplo:

    ```ini
    [server]
    server1.example.com
    server2.example.com

    [server:vars]
    host_key_checking=false
    ansible_port=22
    ansible_user=root
    ansible_password=abcd1234
    ```

3. Execute o playbook:

    ```bash
    ansible-playbook -i hosts.ini main.yml
    ```

## Variáveis

As variáveis podem ser configuradas no playbook ou nos arquivos de variáveis dentro das funções (em `roles/zabbix-agent2/vars/main.yml`). Algumas variáveis comuns incluem:

- `zabbix_server`: Endereço do servidor Zabbix ou Proxy.
- `zabbix_version`: Versão do Zabbix Agent 2 a ser instalada.

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.