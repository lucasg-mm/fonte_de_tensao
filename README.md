# Projeto 1 da Disciplina SCC0180: Fonte de Tensão

## Autor
Lucas Gabriel Mendes Miranda, 10265892

## Objetivo
Projetar uma fonte de tensão que forneça, na saída, uma tensão entre 3V e 12V com capacidade de 100mA.

## Diagrama da Fonte

![Imagem do Circuito](https://i.imgur.com/FtfAlni.png)

## Lista de Componentes Utilizados

| Nome do Componente | Valor | Preço |
| --- | --- | --- |
| [Transformador Trafo](https://www.baudaeletronica.com.br/transformador-trafo-500ma-15v.html) | 15V 500mA | R$ 22,70 |
| [Diodo Zener 1N5242](https://www.baudaeletronica.com.br/diodo-zener-1n5242-12v-0-5w.html) | 12V 0,5W | R$ 0,12 |
| [Resistor](https://www.baudaeletronica.com.br/resistor-1k8-5-1-4w.html) | 1,8k 5% (1/4W) | R$ 0,08 |
| [Resistor](https://www.baudaeletronica.com.br/resistor-1k8-1-2w.html) | 1k 5% (1/2W) | R$ 0,14 |
| [Resistor](https://www.baudaeletronica.com.br/resistor-2k2-5-1-4w.html) | 2,2k 5% (1/4W) | R$ 0,08 |
| [Potenciômetro Linear](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html) | 5k (0,2W) | R$ 1,09 |
| [Capacitor Eletrolítico](https://www.baudaeletronica.com.br/capacitor-eletrolitico-470uf-25v.html) | 470 uF / 25V | R$ 0,33 |
| 4 [Diodos 1N4001](https://www.baudaeletronica.com.br/diodo-1n4001.html) (para a ponte) | 1A | R$ 0,14 (cada)|
| [LED difuso 5mm vermelho](https://www.baudaeletronica.com.br/led-difuso-5mm-vermelho.html) | 2V 20mA | R$ 0,24 |
| [Transistor NPN BC337](https://www.baudaeletronica.com.br/transistor-npn-bc337.html) | VCEO = 45V, IC = 500mA | R$ 0,17 |

## Partes do Circuito e Justificativa dos Componentes

### Fonte de Tensão AC de 127V
A fonte foi projetada para funcionar com o fornecimento de uma tensão de 127V (RMS) em corrente alternada (AC). O simulador usado (Falstad) permite apenas definir a tensão máxima (peak) de uma fonte AC. Mas, sabemos que:

![1](http://www.sciweavers.org/upload/Tex2Img_1593462823/render.png)

Então a tensão máxima dessa fonte foi ajustada para 179.6V no simulador. 

### Transformador
O transformador tem como objetivo diminuir o valor da tensão de 127V. Para determinar o valor do transformador necessário, foi preciso realizar alguns cálculos:

* Sabemos que a nossa fonte precisa fornecer no máximo **12V**

* Cada diodo tem uma queda de **0.7V**

* O circuito regulador precisa de aproximadamente **8.46V** para funcionar (quando a fonte fornece *12V*)

Somando os valores em negrito, temos uma tensão de pico de aproximadamente 21.16V, por isso, precisamos de um transformador de, no mínimo, 15V RMS, capaz de fornecer 500 mA.

### Ponte de Diodos (Rectifier)
A ponte de diodos converte a tensão AC do transformador numa tensão DC pulsante. 

### Capacitor (Filtro)
O capacitor diminui os pulsos da tensão fornecida pela ponte de diodos. O capacitor está submetido a uma tensão de aproximadamente 20V, porém, foi listado na lista de materiais com 25V para evitar queimar o dispositivo (temos uma margem de segurança de 5V).

### LED
Apenas para indicar qua a fonte está ligada. Possui um resistor de 1k conectado em série para não queimar o diodo.

### Circuito Regulador
Esse circuito elimina o ripple da tensão fornecida pelo filtro, resultando na tensão DC entre 3V e 12V desejada (ela é definida manipulando o potenciômetro).

### Saída
Representamos o dispositivo a ser alimentado por um resistor de 120 ohms.

## Link para o Circuito no Falstad
http://tinyurl.com/ycgv9rr6

## Esquemático Feito no EAGLE
Corresponde ao arquivo `fonte.sch`

![Imagem do Esquemático](https://i.imgur.com/X917XMZ.png)

## PCB Feito no EAGLE
Corresponde ao arquivo `fonte.brd`

![Imagem do PCB](https://i.imgur.com/UE5hJaU.png)

## Vídeo

https://www.youtube.com/watch?v=4Xhk5OuTBfk
