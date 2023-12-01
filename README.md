<div align="center">
  <img src="https://github.com/Ka-Soares/animation/assets/145347801/3eb7de64-6d80-47ce-bbf0-9154aaf7fce5" width=60% />
</div>

# Global Solution - FIAP

O desafio proposto foi desenvolvido a pedido da Hapvida NotreDame Intermédica para ser realizado o desenvolvimento e ideação de uma solução para algum dos problemas que nos foram apresentados, no atual projeto, o monitoramento remoto da saúde de pacientes foi escolhido para ser solucionado. Nesse arquivo você encontrará a justificativa do projeto, os objetivos que ele propõe e a descrição do produto.

Este ainda é relacionado a matéria Edge Computing e Computer Systems, ministrada pelo Professor Yan Coelho.

# Descrição do Projeto

Bem-vindo ao Hapvida Away, um projeto dedicado a conscientizar sobre primeiros socorros e resposta a emergências. Este README fornece uma visão geral da estrutura do projeto e de seus principais componentes.

Esse código é um programa para Arduino que utiliza uma tela de LCD (LiquidCrystal) e um botão para simular uma situação em que uma ambulância está a caminho. Além disso, ele emite um som através de um buzzer quando o botão é pressionado. 

Cria um objeto LiquidCrystal chamado lcd com os pinos de conexão ao Arduino para o RS, E, D4, D5, D6 e D7 do display LCD.
```arduino
#define botao 10
```

Define o pino 10 como a constante botao para conectar o botão.
```arduino
int statusBotao;
```

Declara uma variável inteira chamada statusBotao para armazenar o estado do botão (HIGH ou LOW).
```arduino
const int buzzerPin = 6; 
```

Declara uma constante inteira chamada buzzerPin e atribui o valor 6 a ela, indicando que o buzzer está conectado ao pino 6 do Arduino.
```arduino
void setup()
{
  lcd.begin(16, 2);
  pinMode(botao, INPUT);
}
```

No bloco setup(), inicializa o display LCD com 16 colunas e 2 linhas. Define o pino do botão como entrada.
```arduino
void loop()
{
  statusBotao = digitalRead(botao); 
  
  if (statusBotao == HIGH)
  {
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Uma ambulancia");
    lcd.setCursor(0, 1);
    lcd.print("esta a caminho!");
    tone(buzzerPin, 500);
    delay(300);
    noTone(buzzerPin);
    delay(5000);
    lcd.clear();
  }
}
```

No bloco loop(), lê o estado do botão utilizando digitalRead(botao). Se o botão estiver pressionado (statusBotao == HIGH), o programa realiza as seguintes ações:

1- Limpa o display LCD.<p>
2- Define o cursor na posição (0, 0) e imprime "Uma ambulancia".<p>
3- Define o cursor na posição (0, 1) e imprime "esta a caminho!".<p>
4- Emite um tom no buzzer com frequência de 500 Hz por 300 milissegundos.<p>
5- Aguarda 5 segundos.<p>
6- Limpa o display LCD novamente.<p>

Essencialmente, quando o botão é pressionado, o programa exibe uma mensagem no LCD, emite um som no buzzer e aguarda 5 segundos antes de limpar o LCD. Isso simula a situação de uma ambulância a caminho.

# Componentes Necessários
Arduino Uno (ou compatível): Placa principal para o projeto.
LCD 16x2: Display para exibir mensagens.
Botão (Push Button): Dispositivo de entrada para acionar o alerta.
Buzzer: Emite um som quando a ambulância é alertada.

# Esquema de Ligação

Antes de executar o código, siga o esquema de ligação fornecido para conectar os componentes corretamente à placa Arduino. O diagrama pode ser encontrado em "esquema_ligacao.png".

  <img align="center" width="80%" src="https://github.com/Hapvida-Away/HapVida-Away-Edge/assets/145347801/06d98abb-8e7a-49d5-abe9-79429e66bf8f"/>

# Instalação e Configuração

Clone ou faça o download deste repositório para o seu ambiente Arduino.
Abra o arquivo ambulancia_alerta.ino no Arduino IDE.
Verifique se você tem a biblioteca LiquidCrystal instalada. Caso contrário, instale-a através do Gerenciador de Bibliotecas no Arduino IDE.

# Execução do Projeto

Carregue o código para a placa Arduino.
Pressione o botão para simular o alerta de ambulância.
O LCD exibirá a mensagem "Uma ambulância está a caminho!" acompanhada por um som do buzzer.
Após 5 segundos, o LCD será limpo.

## 👑 <a>Colaboradores do grupo Hapvida-Away</a>

<img align="left" width="85" src="https://github.com/Hapvida-Away/HapVida-Away/assets/145347801/5ab56ffa-8362-4043-bb79-35293e14dfb5" />

```java
NOME: EDUARDO BRITES
RM - 552943
```

<br>
<img align="left" width="85" src="https://github.com/Projeto-Dev-Aula/cp2-front-web-2sem/assets/145347801/addf3154-41e5-4227-ba6d-887d3ea737a1"/>

```java
NOME: KAROLINA SOARES
RM - 554187
```