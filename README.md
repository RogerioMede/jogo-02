# jogo-02
# Dungeon Crawler em C

## Sobre o jogo

**Dungeon Crawler em C** é um jogo desenvolvido em linguagem C, utilizando apenas o console como forma de interação com o jogador.

O jogo usa caracteres ASCII para representar o mapa, o jogador, monstros, paredes, portas, chaves, espinhos, caixas, botões e o boss final.

O jogador começa em uma vila, escolhe uma arma com um NPC e depois entra em uma masmorra com três andares. Cada andar possui desafios diferentes, como portas trancadas, chaves, caixas destrutíveis, espinhos, botões e monstros.

O objetivo final é chegar ao terceiro andar e derrotar o boss final para salvar a vila.

---

## Desenvolvedores

* Rogério Medeiros
* Haissam


---

## História

Uma vila foi atacada por criaturas vindas de uma antiga masmorra.

O herói da vila precisa se preparar antes de entrar na dungeon. Para isso, ele conversa com um NPC e escolhe uma das três armas disponíveis: espada, arco ou cajado.

Depois de escolher sua arma, o jogador entra na masmorra e precisa atravessar três andares cheios de obstáculos, armadilhas e monstros.

No último andar, o herói enfrenta o boss final. Ao derrotá-lo, a força maligna da masmorra desaparece e a vila é salva.

---

## Como jogar

Ao iniciar o programa, o jogador encontra um menu principal com três opções:

1. **Jogar**
   Inicia a partida a partir da vila.

2. **Tutorial**
   Mostra a história, os controles, os símbolos do mapa e as armas disponíveis.

3. **Sair**
   Exibe os créditos e encerra o jogo.

---

## Controles

| Tecla | Ação                                    |
| ----- | --------------------------------------- |
| `w`   | Move o jogador para cima                |
| `a`   | Move o jogador para a esquerda          |
| `s`   | Move o jogador para baixo               |
| `d`   | Move o jogador para a direita           |
| `i`   | Interage com o objeto que está à frente |
| `o`   | Ataca usando a arma escolhida           |
| `q`   | Volta para o menu principal             |

O jogo foi feito para ler as teclas diretamente, sem precisar apertar ENTER a cada comando.

---

## Símbolos do jogo

| Símbolo | Significado                     |
| ------- | ------------------------------- |
| `<`     | Jogador olhando para a esquerda |
| `^`     | Jogador olhando para cima       |
| `>`     | Jogador olhando para a direita  |
| `v`     | Jogador olhando para baixo      |
| `*`     | Parede                          |
| `#`     | Espinho                         |
| `k`     | Caixa destrutível               |
| `O`     | Botão                           |
| `D`     | Porta fechada                   |
| `=`     | Porta aberta                    |
| `@`     | Chave                           |
| `L`     | Escada ou entrada da masmorra   |
| `N`     | NPC da vila                     |
| `X`     | Monstro tipo 1                  |
| `Y`     | Monstro tipo 2                  |
| `Z`     | Boss final                      |

---

## Armas disponíveis

Na vila, o jogador deve conversar com o NPC para escolher uma arma.

### Espada

A espada ataca uma área de 3x2 células diretamente à frente do jogador.

### Arco

O arco ataca 4 células em linha reta na direção em que o jogador está olhando.

### Cajado

O cajado ataca todas as 8 células ao redor do jogador, independentemente da direção.

---

## Sistema de vidas

O jogador começa com **3 vidas**.

O jogador perde 1 vida quando:

* pisa em um espinho;
* encosta em um monstro;
* é tocado por um monstro;
* é tocado pelo boss.

Quando o jogador perde uma vida, a fase atual é reiniciada.

Se as 3 vidas acabarem, o jogo mostra a tela de **Game Over** e volta para o menu principal.

---

## Andares do jogo

### Vila

A vila é o ponto inicial do jogo.

Nela existe um NPC que permite ao jogador escolher uma arma. Depois disso, o jogador pode entrar na masmorra.

### Primeiro andar

O primeiro andar ensina as mecânicas básicas do jogo.

Ele possui:

* chave;
* porta fechada;
* caixas destrutíveis;
* escada para o próximo andar.

### Segundo andar

O segundo andar adiciona novos perigos e mecânicas.

Ele possui:

* duas chaves;
* duas portas fechadas;
* espinhos;
* botões;
* monstros do tipo X;
* escada para o terceiro andar.

O monstro do tipo X se movimenta de forma aleatória.

### Terceiro andar

O terceiro andar é o desafio final.

Ele possui:

* três chaves;
* três portas fechadas;
* espinhos;
* botões;
* caixas;
* monstros do tipo X;
* monstros do tipo Y;
* boss final.

O monstro do tipo Y persegue o jogador de forma simples, tentando reduzir a distância entre ele e o jogador.

O boss final possui 1 vida e tem um movimento diferente dos outros monstros: ele se move apenas a cada 2 turnos e alterna entre tentar andar na horizontal e na vertical.

---

## Condição de vitória

O jogador vence ao derrotar o boss final no terceiro andar.

Depois disso, o jogo mostra uma tela de vitória com o final da história.

---

## Como compilar e executar

Para compilar o jogo usando GCC:

```bash
gcc dungeon_crawler_final_limpo.c -o jogo
```

Para executar no Linux ou Mac:

```bash
./jogo
```

Para executar no Windows:

```bash
jogo.exe
```

---

## Tecnologias utilizadas

* Linguagem C
* Console
* Matrizes de caracteres
* Estruturas condicionais
* Laços de repetição
* Funções
* Leitura direta do teclado
* Geração de movimento aleatório para monstros

---

## Organização do código

O código foi dividido em funções para facilitar a leitura e a manutenção.

Algumas das principais funções são:

* `menuPrincipal()`
  Controla o menu inicial do jogo.

* `tutorial()`
  Mostra a história, os controles e os símbolos.

* `jogar()`
  Controla o loop principal da partida.

* `iniciarVila()`
  Monta o mapa da vila.

* `iniciarAndar1()`
  Monta o primeiro andar da masmorra.

* `iniciarAndar2()`
  Monta o segundo andar da masmorra.

* `iniciarAndar3()`
  Monta o terceiro andar da masmorra.

* `tentarMover()`
  Controla a movimentação do jogador.

* `interagir()`
  Controla a interação com NPC, chaves, portas, botões e escadas.

* `atacar()`
  Controla o ataque de acordo com a arma escolhida.

* `moverMonstros()`
  Controla o movimento dos monstros X e Y.

* `moverBoss()`
  Controla o movimento do boss final.

---

## Declaração sobre uso de IA generativa

Foi utilizada IA generativa, especificamente o ChatGPT, como ferramenta de apoio durante o desenvolvimento do projeto.

A IA foi usada para auxiliar na organização das ideias, estruturação do código, criação de funções, correção de erros e montagem deste README.


---

## Créditos

Projeto desenvolvido para a disciplina de programação, com o objetivo de aplicar conceitos básicos da linguagem C em um jogo funcional no console.
