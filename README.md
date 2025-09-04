# Projeto: Análise de Passes no Futebol com Node-RED

## Descrição

Este projeto utiliza o Node-RED para monitorar e analisar passes durante uma partida de futebol. Ele calcula o tempo médio entre passes, identifica o jogador que mais passa a bola e determina o status do jogo com base no intervalo entre os passes.

## Funcionalidades

- **Contagem de Passes**: Conta o número total de passes realizados.
- **Tempo Médio entre Passes**: Calcula o tempo médio entre os passes.
- **Jogador com Mais Passes**: Identifica o jogador que mais realizou passes.
- **Status do Jogo**: Determina o status do jogo com base no intervalo entre os passes:
  - 🟢 **Intenso**: Intervalo entre passes ≤ 5 segundos.
  - 🟡 **Moderado**: Intervalo entre passes > 5 e ≤ 15 segundos.
  - 🔴 **Lento**: Intervalo entre passes > 15 segundos.
- **Gráficos de Intervalos**: Exibe gráficos com os intervalos entre os passes ao longo do tempo.:contentReference[oaicite:30]{index=30}

## Requisitos

- [Node.js](https://nodejs.org/) (versão recomendada: 16.x ou superior)
- [Node-RED](https://nodered.org/) instalado e em funcionamento
- [Node-RED Dashboard](https://flows.nodered.org/node/node-red-dashboard) instalado no Node-RED

## Instalação

1. Clone ou baixe este repositório.
2. Abra o Node-RED em seu navegador (geralmente acessível em `http://localhost:1880`).
3. Clique no menu (☰) no canto superior direito e selecione **Importar**.
4. Escolha o arquivo `fluxo-node-red.json` e clique em **Importar**.
5. Clique em **Deploy** para aplicar as alterações.
6. Acesse o dashboard em `http://localhost:1880/ui` para visualizar os dados e gráficos.:contentReference[oaicite:43]{index=43}

## Personalização

- **Jogadores**: Para alterar os nomes dos jogadores, edite o nó **Inject** que simula a entrada de dados e modifique o campo `payload` para o nome desejado.
- **Intervalo entre Passes**: O tempo entre os passes é simulado pelo nó **Inject**. Ajuste o valor do campo `payload` para simular diferentes intervalos.
- **Gráficos**: Para personalizar os gráficos, edite o nó **Chart** e ajuste as configurações conforme necessário.:contentReference[oaicite:50]{index=50}

## Contribuições

Contribuições são bem-vindas! Se você tiver sugestões ou melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
