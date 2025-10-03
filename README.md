# Jogo da Cobrinha em Python para o Terminal 🐍

Este é um projeto simples do clássico Jogo da Cobrinha (Snake), desenvolvido em Python para ser jogado diretamente no terminal.

## Visão Geral do Jogo

O jogador controla uma cobra que se move pela tela, com o objetivo de comer as frutas (`♦`) que aparecem em locais aleatórios. Cada vez que a cobra come uma fruta, ela cresce de tamanho. O jogo termina se a cobra colidir com as bordas da tela ou com o seu próprio corpo.

![Gameplay do Jogo da Cobrinha no Terminal](https://media1.giphy.com/media/fq8JHOzq9ZML4DDWfK/giphy.gif)


## Como Jogar

1.  **Pré-requisitos:**
    * **Python 3** instalado.
    * Este jogo usa a biblioteca `curses`, que já vem instalada com Python em sistemas Linux e macOS.
    * Para usuários de **Windows**, pode ser necessário instalar o pacote `windows-curses` via pip:
        ```bash
        pip install windows-curses
        ```

2.  **Instalação:**
    * Clone este repositório ou simplesmente baixe o arquivo `.py` para o seu computador.

3.  **Execução:**
    * Abra seu terminal ou prompt de comando.
    * Navegue até o diretório onde você salvou o arquivo.
    * Execute o seguinte comando (substitua `snake_game.py` pelo nome do seu arquivo):
        ```bash
        python SnakeGame.py
        ```
    * Ao iniciar, o jogo pedirá para você **selecionar a dificuldade** de 1 (mais lento) a 5 (mais rápido).
    * Use as **teclas de seta** (↑, ↓, ←, →) para controlar a direção da cobra.

## Como Foi Feito

O jogo foi construído inteiramente em Python, utilizando algumas bibliotecas padrão para gerenciar a interface do terminal, a lógica do jogo e a aleatoriedade.

### 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Python 3**: A linguagem de programação principal.
* **`curses`**: Uma biblioteca fundamental para criar interfaces de usuário baseadas em texto (TUI). Ela nos permite:
    * Controlar a posição do cursor.
    * Desenhar caracteres em coordenadas específicas da tela (`window.addch`).
    * Capturar teclas pressionadas pelo usuário em tempo real (`window.getch`) sem precisar que o usuário aperte Enter.
    * Limpar a tela e desenhar bordas.
    * O `curses.wrapper` é usado para inicializar e fechar a biblioteca `curses` de forma segura, restaurando as configurações do terminal ao final do jogo, mesmo que ocorra um erro.
* **`random`**: Usada para gerar as coordenadas da fruta em posições aleatórias na tela (`random.randint`).
* **`time`**: Utilizada para criar uma pequena pausa (`time.sleep`) na tela de "Game Over", permitindo que o jogador veja sua pontuação final antes do programa encerrar.

### 🧠 Lógica do Jogo

O fluxo principal do jogo está contido na função `game_loop`, que opera em um loop `while True`. A cada iteração deste loop, o jogo executa os seguintes passos:

1.  **Limpa e Redesenha a Tela**: A tela é limpa e as bordas são desenhadas.
2.  **Desenha os Elementos**: A cobra (`@` para a cabeça e `s` para o corpo) e a fruta (`♦`) são desenhadas em suas posições atuais.
3.  **Captura de Input**: O jogo aguarda por um curto período de tempo (definido pela dificuldade) por um comando do jogador. Se nenhuma tecla for pressionada, a
