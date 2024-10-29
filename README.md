# Ponderada Semana3 Farol
 
## Video
&emsp;O vídeo se encontra no arquivo nesse repositório.

## Imagem

## Relato

&emsp;Seja por uma ideia boa ou por pura preguiça de conectar vários resistores no circuito, a ideia de utilizar apenas um veio do fato de que, nesse sistema, não há como queimar os leds com um resistor de 1k ohm conectado no ground, protegendo os leds.
&emsp;Cada led está conectado em um pino diferente e, pelo código, a função acenderLuz apaga a luz anterior, acende a nova e espera o tempo necessário até a próxima troca, seguindo o 

## Código

```cpp
int pinVerde = 4;
int pinVermelho = 2;
int pinAmarelo = 3;
int pins[3] = {pinVerde, pinVermelho, pinAmarelo};

void setup() {
  // put your setup code here, to run once:
  for (int i = 0; i <3; i++){
    pinMode(pins[i], OUTPUT);
    digitalWrite(pins[i], LOW);
  }
}

void loop() {
  acenderLuz(pinAmarelo, pinVermelho, 6000);
  acenderLuz(pinVermelho, pinAmarelo, 2000);
  acenderLuz(pinAmarelo, pinVerde, 4000);
  acenderLuz(pinVerde, pinAmarelo, 2000);
}

void acenderLuz(int pinoAntigo, int pinoNovo, int tempoMs){
  digitalWrite(pinoAntigo, LOW);
  digitalWrite(pinoNovo, HIGH);
  delay(tempoMs);
}
```