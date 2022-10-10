## Automação com Ansible
Projeto: Balanceador de carga para uma aplicação que é executada no apache.

Usarei o Ansible para configurar 4 servidores para criar uma estrutura de alta disponibilidade com HAProxy + Keepalived, que vai balancear o tráfego para 2 instâncias que vão rodar um simples html.

## Servidores que serão usados:
- 1 vm com Almalinux: balanceador1;
- 1 vm com Debian: balanceador2;
- 1 vm com Centos: webserver1;
- 1 vm com Debian: webserver2;
- 1 vm com Centos: servidor do Ansible;

## Arquivos
- ansible.cfg : arquivo de configuração do ansible.
- balancers.yml: playbook para provisionamento dos servidores que serão configurados com balanceadores de cargas.
- debian.yml: playbook com as tasks dos servidores debian.
- inventario.ini: lista de ips dos hosts.
- redhat.yml: playbook com as tasks dos servidores centos e almalinux.
- webserveres.yml: playbook para provisionamento dos servidores que serão configurados como servidores de aplicação.
- files/haproxy.cfg: template do arquivo de configuração do HAProxy.
- files/Keepalived.yml: template do arquivo de configuração do Keepalived.
- site/index.html: arquivo simples em html que será usado com página de teste.

## Execução:
Para que tudo seja executado com sucesso, é necessário que as chaves ssh sejam configuradas e enviadas paras os servidores que serão configurados.

Adicione ao arquivo inventario.ini os hosts que serão configurados. Em seguida, execute a playbook webserveres.yml e depois a balancers.yml.
