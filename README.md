# Deslocamento de LEDs  

Até o momento, interagimos com os LEDs apenas por meio de somadores e contadores. Nesta atividade, exploraremos a **operação de deslocamento circular (shift circular)**.

## Deslocamento Circular  

Nesta atividade, utilizaremos o conceito de **deslocamento circular**, no qual:  

- O **bit mais significativo** de um registrador se torna o **menos significativo**.  
- O **menos significativo** passa a ocupar a posição do **segundo menos significativo**, e assim por diante.  

A imagem abaixo ilustra essa operação:  

![Circular shift](circular_shifft.png)  

## Atividade  

Seu objetivo é escrever um módulo Verilog chamado **LedShifter**, que deve:  

- Ter um **parâmetro** chamado `CLK_FREQ`, que representa a frequência do clock.  
- Ter como **entradas** os sinais `clk` (clock) e `rst_n` (reset ativo em nível baixo).  
- Ter como **saída** um sinal de 8 bits chamado `leds`.  

O comportamento esperado do módulo é semelhante ao da atividade anterior, com a diferença de que, em vez de incrementar um contador, será realizado um **deslocamento circular para a esquerda** em um registrador de 8 bits.  

- **Executar um deslocamento a cada 1 segundo**, utilizando `CLK_FREQ` como referência.  
- **Iniciar com o valor 0x1F (`8'b00011111`)** quando `rst_n` estiver acionado.  

### Código inicial  

Como ponto de partida, utilize o esqueleto de código abaixo:  

```verilog
module LedShifter #(
    parameter CLK_FREQ = 25_000_000
) (
    input  wire clk,
    input  wire rst_n,
    output wire [7:0] leds
);

endmodule
```

## Entrega

Primeiro, faça o *push* do seu código no repositório do **GitHub Classroom** para que o código seja carregado na placa. Veja o comportamento no site [embarcatechfpga.lsc.ic.unicamp.br](https://embarcatechfpga.lsc.ic.unicamp.br). Se tiver dúvidas de como utilizar a infraestrutura, veja este guia [aqui](guia_remoto.md).

Depois, confira o sistema de correção automática, que irá validar sua implementação e atribuir uma nota com base nos testes.

> **Dica:**  
Não altere os arquivos de correção! Para entender como os testes funcionam, consulte o script `run.sh` disponível no repositório.
