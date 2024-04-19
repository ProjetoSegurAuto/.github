# Projeto Segurauto

Esta organização tem como objetivo hospedar soluções desenvolvidas pelo grupo LIVE-CIn para o projeto SegurAuto que visa o estudo de Platoons para rodovia. Este documento será dividido de acordo com as equipes do projeto.

## Comunicação
Refere-se a comunicação interna e externa do veiculo

### ECU
Atualmente trabalhamos no desenvolvimento de dois devices

#### ESP-32
Solução desenvolvida do zero para a comunicação Platoon. Atualmente temos vigente duas abordagem de software

- Polling: https://github.com/ProjetoSegurAuto/ECU-communication
- Concorrêncial - Produtor e Consumidor: https://github.com/ProjetoSegurAuto/Async_ESP_ECU-communication

Ambas implementam os seguintes submodulos:

- Datalogger, para guardar o timestamp das mensagens e o seu contexto(envio/recebimento intra/inter-veicular): https://github.com/ProjetoSegurAuto/Datalogger-ECU_communication
- Config datalogger, o submodulo acima espera a saida deste script desktop para configurar o RTC: https://github.com/ProjetoSegurAuto/Config_datalogger
- MAC, filtra os MACs que a ECU pode enviar via rádio. Tem como objetivo auxiliar em testes e estudos para Platoons já formados: https://github.com/ProjetoSegurAuto/MAC_Topology_Platoon

#### Cohda MK6C
Equipamento de comunicação que tem portabilidade CV2X, DSRC, CAN e entre outras soluções. A API praticamente vem pronta e modificamos para adequar à nosso projeto.

- exampleCN:

Todos os devices são conectados ao barramento CAN.

### Telemetria
Para visualização dos nossos dados, desenvolvimentos interfaces gráficas e ECU externas para ouvir o behavior do Platoon.

- Telemetria de um carro, verifica os dados de um carro em tempo real: https://github.com/ProjetoSegurAuto/Telemetry/tree/main
- Telemetria de um Platoon, apresenta a saúde dos carros no contexto Platoon: https://github.com/ProjetoSegurAuto/front

### Interface CAN-Orin
Neste projeto, temos um computador embarcado para a realização do behavior do carrinho. Para interfacear, utilizamos um equipamento da industria automotiva para comunicação e foi desenvolvido um software para mapear em mensagens da CAN para Ethernet. 

## Percepção
Sistema baseado em ROS, que processa e denota o behavior de um carro(sendo lider ou seguidor) 

- ADAS: https://github.com/ProjetoSegurAuto/ADAS-project

## Infra
