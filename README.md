# Teste DevOps
Repositório criado para apresentação do teste feito com ferramentas de DevOps.

#### Ferramentas usadas no teste.
Todo o teste foi realizado usando o sistema operacional FreeBSD como base e o VIM como editor de texto para escrever o código.

Foi usado o [Vagrant](https://www.vagrantup.com/) para provisionar uma imagem do [debian/stretch64](https://app.vagrantup.com/debian/boxes/stretch64).
Dentro do diretório principal tem o arquivo usado para provisionar usando o virtualbox, e um arquivo nomeado *Digital_Vagrant* usado para provisionar a maquina diretamente na Digital Ocean.
Essa imagem pode ser acessada atrávez do link http://prometheus.kanazuchi.com.

Toda configuração da instancia foi feita utilizando o [Ansible](https://www.ansible.com/).
Ao iniciar o provisionamento da maquina com o Vagrant, o ansible se encarregará de configurar e subir os serviços necessários.

### Ferramenta de monitoramento.
Como ferramenta para o monitoramento das instancias Linux e Windows foi usado o [Prometheus](https://prometheus.io/) como servidor para armazenar e acessar os graficos com os dados de serviços e recursos das instancias.

### Clients End-Point
Como client end-points foram usasados o [Node_Exporter](https://github.com/prometheus/node_exporter) e [Process-Exporter](https://github.com/ncabatoff/process-exporter) para instancias Linux/FreeBSD, para as instancias Windows foi usado o [WMI_Exporter](https://github.com/martinlindhe/wmi_exporter).

### Templates para visualização.
Foram usados templates do [Grafana](http://grafana.com/) para visualizar os dados.

### Alertas.
Para os alertas (no teste foram usados apenas envios para email e um canal no slack #prometheus-alerts) foi usado o [AlertManager](https://prometheus.io/docs/alerting/alertmanager/).

Foram criados tresholds nos graficos, e algumas regras para enviar alertas, assim como condições para que controlassem o tempo de envio e as removessem.
