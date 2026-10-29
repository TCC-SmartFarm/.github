# SmartFarm

Plataforma open source de agricultura de precisão. Este ecossistema é baseado em arquitetura de microserviços, dividindo responsabilidades entre captura de dados no *edge*, processamento assíncrono e interfaces de usuário.

## Topologia da Arquitetura

### 📟 Hardware & Edge Computing
* [firmware]([URL_DO_REPO]): Firmware em C para a estação de coleta de dados no campo.

### 📡 Ingestão e Mensageria
* [mqtt-broker]([URL_DO_REPO]): Camada primária de recepção, gerenciando a telemetria enviada pelos sensores.
* [mqtt-sub]([URL_DO_REPO]): Serviço de subscrição para tópicos MQTT.
* [barramento-de-eventos]([URL_DO_REPO]): Broker de mensageria assíncrona utilizando RabbitMQ.

### ⚙️ Core & Regras de Negócio
* [backend]([URL_DO_REPO]): Serviço base estrutural para a aplicação do cliente.
* [api-service]([URL_DO_REPO]): Interface de comunicação/Gateway entre os clientes front-end e os serviços de back-end.
* [irrigacao-mss]([URL_DO_REPO]): Microserviço dedicado à lógica de acionamento e controle de irrigação.

### 💾 Persistência e Otimização
* [influx-connector]([URL_DO_REPO]): Consumidor do barramento de eventos dedicado à inserção de dados de telemetria no InfluxDB.
* [cache-service]([URL_DO_REPO]): Camada de otimização de consultas utilizando Redis.

### 📱 Interfaces de Usuário (Front-end)
* [frontend]([URL_DO_REPO]): Aplicação web em TypeScript para acesso do cliente final.
* [SmartFarm_App]([URL_DO_REPO]): Aplicativo móvel construído via Expo (TypeScript).
