<h1>Desafio de projeto do Felipão: Mario Kart.JS</h1>

  <table>
        <tr>
            <td>
                <img src="./docs/header.gif" alt="Mario Kart" width="200">
            </td>
            <td>
                <b>Objetivo:</b>
                <p>Mario Kart é uma série de jogos de corrida desenvolvida e publicada pela Nintendo. Nosso desafio será criar uma lógica de um jogo de vídeo game para simular corridas de Mario Kart, levando em consideração as regras e mecânicas abaixo.</p>
            </td>
        </tr>
    </table>

<h2>Players</h2>
      <table style="border-collapse: collapse; width: 800px; margin: 0 auto;">
        <tr>
            <td style="border: 1px solid black; text-align: center;">
                <p>Mario</p>
                <img src="./docs/mario.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 4</p>
                <p>Manobrabilidade: 3</p>
                <p>Poder: 3</p>
            </td>
             <td style="border: 1px solid black; text-align: center;">
                <p>Peach</p>
                <img src="./docs/peach.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 3</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 2</p>
            </td>
              <td style="border: 1px solid black; text-align: center;">
                <p>Yoshi</p>
                <img src="./docs/yoshi.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 2</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 3</p>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid black; text-align: center;">
                <p>Bowser</p>
                <img src="./docs/bowser.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 5</p>
                <p>Manobrabilidade: 2</p>
                <p>Poder: 5</p>
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Luigi</p>
                <img src="./docs/luigi.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 3</p>
                <p>Manobrabilidade: 4</p>
                <p>Poder: 4</p>
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Donkey Kong</p>
                <img src="./docs/dk.gif" alt="Mario Kart" width="60" height="60">
            </td>
            <td style="border: 1px solid black; text-align: center;">
                <p>Velocidade: 2</p>
                <p>Manobrabilidade: 2</p>
                <p>Poder: 5</p>
            </td>
        </tr>
    </table>

<p></p>

<h3>🕹️ Regras & mecânicas:</h3>

<b>Jogadores:</b>

<input type="checkbox" id="jogadores-item" />
<label for="jogadores-item">O Computador deve receber dois personagens para disputar a corrida em um objeto cada</label>

<b>Pistas:</b>

<ul>
  <li><input type="checkbox" id="pistas-1-item" /> <label for="pistas-1-item">Os personagens irão correr em uma pista aleatória de 5 rodadas</label></li>
  <li><input type="checkbox" id="pistas-2-item" /> <label for="pistas-2-item">A cada rodada, será sorteado um bloco da pista que pode ser uma reta, curva ou confronto</label>
    <ul>
      <li><input type="checkbox" id="pistas-2-1-item" /> <label for="pistas-2-1-item">Caso o bloco da pista seja uma RETA, o jogador deve jogar um dado de 6 lados e somar o atributo VELOCIDADE, quem vencer ganha um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-2-item" /> <label for="pistas-2-2-item">Caso o bloco da pista seja uma CURVA, o jogador deve jogar um dado de 6 lados e somar o atributo MANOBRABILIDADE, quem vencer ganha um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-3-item" /> <label for="pistas-2-3-item">Caso o bloco da pista seja um CONFRONTO, o jogador deve jogar um dado de 6 lados e somar o atributo PODER, quem perder, perde um ponto</label></li>
      <li><input type="checkbox" id="pistas-2-3-item" /> <label for="pistas-2-3-item">Nenhum jogador pode ter pontuação negativa (valores abaixo de 0)</label></li>
    </ul>
  </li>
</ul>

<b>Condição de vitória:</b>

<input type="checkbox" id="vitoria-item" />
<label for="vitoria-item">Ao final, vence quem acumulou mais pontos</label>

# Atualização do Jogo: Mecânicas de Confronto Aprimoradas

## Visão Geral
Esta atualização introduz mecânicas de confronto aprimoradas ao nosso jogo de corrida. Agora, os jogadores enfrentam desafios aleatórios usando "casco" ou "bomba" durante os confrontos, e há uma chance de ganhar um bônus de "turbo" por vencer esses confrontos.

## Novos Recursos

### Itens de Confronto
- **Casco:** Causa a perda de 1 ponto pelo jogador perdedor.
- **Bomba:** Causa a perda de 2 pontos pelo jogador perdedor.

Esses itens são atribuídos aleatoriamente a cada jogador durante um confronto. A escolha do item determina a penalidade que o jogador perdedor receberá.

### Bônus Turbo
Vencer um confronto agora oferece a chance de o jogador vencedor receber um bônus de turbo, que adiciona 1 ponto ao seu placar. Este bônus é concedido com uma probabilidade de 50%.

## Implementação

### Lógica de Confronto
A lógica de confronto está integrada na função `playRaceEngine`. Quando o bloco "CONFRONTO" é sorteado, cada jogador rola um dado, e seus respectivos atributos "PODER" são adicionados aos resultados. O jogador com o resultado mais alto vence o confronto.

Dependendo do item de confronto atribuído aleatoriamente, o jogador perdedor irá:
- Perder 1 ponto se atingido por um casco.
- Perder 2 pontos se atingido por uma bomba.

Se o resultado do jogador vencedor for maior, ele poderá receber um bônus de turbo, adicionando um ponto extra ao seu placar total.

### Seleção Aleatória dos Itens
Os itens (casco ou bomba) são selecionados aleatoriamente para cada jogador no início de cada confronto. Essa aleatoriedade adiciona um elemento de imprevisibilidade e estratégia ao jogo, pois os jogadores devem se adaptar a penalidades potencialmente maiores.

### Probabilidade do Bônus Turbo
Após vencer um confronto, há uma chance de 50% de que o jogador vencedor receba um bônus de turbo. Isso introduz outra camada de emoção e potencial para virar o jogo, especialmente em corridas acirradas.

## Conclusão
Essas atualizações tornam o jogo mais dinâmico e envolvente, oferecendo aos jogadores novos elementos estratégicos para considerar durante cada corrida. Aproveite os confrontos aprimorados e a emoção de potencialmente ganhar um impulso de turbo quando menos esperar!
