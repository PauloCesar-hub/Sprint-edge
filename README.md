# Monitor de Passes – ESP32 + MQTT + Node-RED

Este projeto permite monitorar **passes entre jogadores** utilizando um **ESP32**, enviando os dados em tempo real via **MQTT (HiveMQ)** para um **Dashboard Node-RED**.  
O sistema exibe no display **LCD I2C** o jogador atual, total de passes, tempo entre passes e um indicador de ritmo (`FAST`, `MED`, `SLOW` ou `WAIT`).

O Dashboard mostra:
- Jogador atual
- Total de passes
- Intervalo médio
- Status da jogada
- Gráficos em tempo real
- Controles para trocar jogador e resetar contagem

---

## 📌 Funcionalidades

| Função | Descrição |
|------|-----------|
| Contagem de Passes | Cada aperto no botão registra 1 passe |
| Alternar Jogador | Seleciona entre 5 jogadoras da equipe |
| Reset Geral | Reinicia contagem e métricas instantaneamente |
| Envio MQTT | Dados enviados a cada 1 segundo para o broker HiveMQ |
| Controle Remoto via Node-RED | Reset e troca de jogadora por comandos MQTT |
| Exibição LCD | Mostra jogador, total, intervalo e ritmo |

---

## 🧱 Hardware Utilizado

| Componente | Quantidade |
|-----------|------------|
| ESP32 | 1 |
| Display LCD 16x2 com I2C | 1 |
| Botões (Pass, Jogador, Reset) | 3 |
| Jumpers | diversos |

---

## 🧩 Ligações (PINOUT)

| Função | Pino ESP32 |
|------|-----------|
| Botão de Passe | GPIO 12 |
| Botão de Jogadora | GPIO 14 |
| Botão Reset | GPIO 27 |
| SDA do LCD | GPIO 21 |
| SCL do LCD | GPIO 22 |

---

## 🌐 Conexão Wi-Fi + MQTT

| Item | Valor |
|------|------|
| SSID | `Wokwi-GUEST` |
| Senha | (vazia) |
| Broker MQTT | `broker.hivemq.com` |
| Porta | `1883` |
| Tópico Publicação | `esp32/passes/data` |
| Tópico Comandos | `esp32/passes/cmd` |

---

## 🖥 Execução no Wokwi

1. Abra o projeto no Wokwi
2. Certifique-se que o `diagram.json` contém:
```json
"libraries": [
  { "name": "PubSubClient" },
  { "name": "LiquidCrystal_I2C" }
]
Clique em Start e veja o LCD reagindo ao apertar os botões

📊 Dashboard Node-RED
Importar Fluxo
No Node-RED, clique em:

mathematica
Copiar código
Menu > Import > Cole o fluxo fornecido > Import
Dependências
No Node-RED:

mathematica
Copiar código
Menu > Manage Palette > Install > node-red-dashboard
Menu > Manage Palette > Install > node-red-contrib-mqtt-broker
Ajustar o broker MQTT
Abra os nós MQTT In e MQTT Out

Use:

yaml
Copiar código
Server: broker.hivemq.com
Port: 1883
🧠 Comandos via MQTT
Comando	Função
reset	Zera tudo
next	Passa para próxima jogadora

Exemplo via MQTT Explorer / Node-RED:

makefile
Copiar código
Tópico: esp32/passes/cmd
Payload: next
📈 Exemplo de Payload Enviado
json
Copiar código
{
  "player": "Andressa",
  "passes": 12,
  "interval": 1.8,
  "status": "FAST"
}

## Links importantes 
-🔗 [Link do Video Explicativo do Projeto no Youtube](https://youtube.com/shorts/iJNGlCjh49o)

-🔗 [Link da aplicação em teste no wokwi](https://wokwi.com/projects/446725743634396161)

<div align="center">
  <img src="Captura de Tela 2025-11-05 às 18.07.34" width="600" alt="Arquitetura do Projeto">
</div>

<div align="center">
  <img src="Captura de Tela 2025-11-05 às 18.07.41" width="600" alt="Arquitetura do Projeto">
</div>

## 👨‍💻 Autores

- Paulo Cesar de Govea Junior - (RM:566034)
- Guilherme Vilela Perez - (RM:564422)
- Gustavo Panham Dourado - (RM:563904)
- Christian Schunck de Almeida - (RM:563850)
- Thomas Jeferson Santana Wang - (RM565104)



