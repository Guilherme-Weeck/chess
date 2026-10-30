# ♟️ Xadrez Multiplayer via MQTT no GitHub Pages

Um jogo de xadrez multiplayer em tempo real que roda 100% no navegador como uma página estática hospedada no **GitHub Pages**, sem a necessidade de um servidor backend próprio.

---

## 🎯 Sobre o Projeto

O objetivo deste projeto é proporcionar partidas de xadrez entre dois jogadores à distância utilizando uma arquitetura completamente *serverless* e desacoplada. A comunicação entre os jogadores ocorre via WebSockets por meio de um broker MQTT público e gratuito.

### ✨ Funcionalidades
* ♟️ **Tabuleiro Interativo**: Suporte a *drag-and-drop* e rotação automática do tabuleiro dependendo da cor atribuída ao jogador.
* ⚖️ **Validação de Regras**: Gerenciamento estrito de movimentos válidos, xeque, xeque-mate, empate e promoção de peças usando `chess.js`.
* 🔗 **Salas via URL**: Geração automática de ID de sala e botão para copiar link de convite (`?sala=ID`).
* ⚡ **Comunicação em Tempo Real**: Sincronização instantânea de jogadas via MQTT sobre WebSockets Seguros (`wss://`).
* 📦 **Sem Dependências Externas (CDNs)**: Todos os scripts, estilos e imagens das peças ficam armazenados localmente no próprio repositório.

---

## ⚙️ Arquitetura e Tecnologias

| Componente | Tecnologia | Função |
| :--- | :--- | :--- |
| **Hospedagem** | GitHub Pages | Servidor de arquivos estáticos (HTML, CSS e JS) |
| **Interface Visual** | Chessboard.js + jQuery | Renderização do tabuleiro e interação visual |
| **Lógica do Jogo** | Chess.js | Validação de regras do xadrez e gerenciamento do estado (FEN) |
| **Protocolo de Rede** | MQTT sobre WebSockets (`wss://`) | Troca de mensagens de jogadas entre navegadores |
| **Cliente MQTT** | MQTT.js | Biblioteca JavaScript para publicação e inscrição em tópicos |
| **Broker MQTT** | EMQX Broker (`broker.emqx.io`) | Intermediário gratuito de mensagens via WebSockets Seguros |

---

## 📂 Estrutura do Repositório

```text
.
├── index.html                  # Interface do jogo e lógica principal
├── css/
│   └── chessboard-1.0.0.min.css # Estilos visuais do tabuleiro
├── js/
│   ├── jquery-3.7.1.min.js     # Dependência do Chessboard.js
│   ├── chessboard-1.0.0.min.js # Gerenciador gráfico do tabuleiro
│   ├── chess.min.js            # Validador de regras de xadrez
│   └── mqtt.min.js             # Cliente MQTT para WebSockets
└── img/
    └── chesspieces/
        └── wikipedia/          # Imagens PNG das peças (Brancas e Pretas)
