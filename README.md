## README.md — Projeto IoT: Monitoramento de Passes e Intensidade do Jogo
📌 Visão Geral

Este projeto implementa um sistema IoT para monitoramento de passes em uma partida e análise da intensidade do jogo em tempo real.
Utilizando Node-RED e sensores simulados (ou físicos, se desejado), o sistema registra a quantidade de passes, calcula o tempo médio entre passes e classifica o ritmo do jogo em três níveis:

🟢 Intenso → tempo médio ≤ 5s

🟡 Moderado → tempo médio > 5s e ≤ 15s

🔴 Lento → tempo médio > 15s

🔹 Arquitetura IoT

A solução é composta por três camadas principais:

1. Dispositivos IoT

Sensores simulados → podem ser representados no Node-RED via botões ou injeções de eventos.

Sensores físicos (opcional) → RFID, infravermelho (IR) ou LDR para capturar movimentações reais.

Microcontrolador (opcional) → ESP32 ou Arduino para coletar dados e transmiti-los.

2. Plataforma de Gerenciamento

Node-RED → plataforma principal usada para:

Receber os dados dos sensores.

Processar estatísticas dos passes.

Classificar o ritmo do jogo.

Publicar os resultados no dashboard.

HiveMQ (opcional) → pode ser usado para comunicação MQTT.

FIWARE (opcional) → alternativa para gerenciamento avançado e integração com Big Data.

3. Interface de Visualização

Node-RED Dashboard exibe:

Número de passes registrados.

Tempo médio entre passes.

Status do jogo: Intenso, Moderado ou Lento.

Gráficos históricos de desempenho.

## 📊 Fluxo da Arquitetura
graph TD
    A[Sensor/Simulação] -->|Evento de Passe| B[Node-RED]
    B --> C[Processamento dos Dados]
    C --> D[Classificação do Ritmo]
    D --> E[Dashboard Node-RED]

## ⚙️ Instalação e Configuração
1. Pré-requisitos

Node.js ≥ 18

npm ≥ 9

Node-RED ≥ 3.1

Node-RED Dashboard ≥ 3.6.6

2. Instalar o Node-RED
sudo npm install -g --unsafe-perm node-red

3. Iniciar o Node-RED
node-red


Após iniciar, acesse no navegador:
🔗 http://localhost:1880

4. Instalar o Node-RED Dashboard
cd ~/.node-red
npm install node-red-dashboard


Reinicie o Node-RED após a instalação.

5. Importar o Fluxo

Abra o Node-RED no navegador.

Clique no menu no canto superior direito → Importar.

Cole o conteúdo do arquivo fluxo-node-red.json.

Clique em Importar para carregar os nós.

## 🖥️ Como Usar

Clique no botão Simular Passe para registrar um passe.

O sistema irá:

Incrementar o contador de passes.

Calcular o tempo médio entre passes.

Atualizar automaticamente o status do jogo.

Veja tudo no dashboard:
🔗 http://localhost:1880/ui

📂 Estrutura do Projeto
Projeto-Passes-Futebol/
│── fluxo-node-red.json   # Fluxo completo do Node-RED
│── README.md             # Documentação do projeto

## 🚦 Status do Jogo
Tempo Médio	Status	Cor
≤ 5s	Intenso	🟢
5s < tempo ≤ 15s	Moderado	🟡
> 15s	Lento	🔴
## 💡 Futuras Melhorias

Integração com sensores físicos via Arduino/ESP32.

Envio de alertas automáticos via Telegram ou WhatsApp.

Armazenamento histórico em banco de dados (MongoDB ou FIWARE).
---
## Links importantes 
-🔗 [Link do Video Explicativo do Projeto no Youtube]()
<div align="center">
  <img src="Captura de Tela 2025-09-04 às 11.28.41.png" width="600" alt="Arquitetura do Projeto">
</div>

<div align="center">
  <img src="Captura de Tela 2025-09-04 às 11.29.02.png" width="600" alt="Arquitetura do Projeto">
</div>
---
## 👨‍💻 Autores

- Paulo Cesar de Govea Junior - (RM:566034)
- Guilherme Vilela Perez - (RM:564422)
- Gustavo Panham Dourado - (RM:563904)
- Christian Schunck de Almeida - (RM:563850)
- Thomas Jeferson Santana Wang - (RM565104)
  
Projeto desenvolvido para monitorar passes e intensidade de jogo usando IoT + Node-RED.
