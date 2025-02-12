# Controle de Servomotor por PWM no RP2040

## Descrição
Este projeto implementa o controle de um servomotor utilizando PWM (Pulse Width Modulation) no microcontrolador RP2040. A lógica do sistema permite a movimentação do servomotor para posições definidas (0°, 90° e 180°) e a transição suave entre esses ângulos.

Além disso, um LED RGB (conectado à GPIO 12) é controlado junto com o servomotor, permitindo a observação do efeito do PWM na iluminação do LED.

## Componentes Necessários
- **BitDogLab** (com LED RGB e GPIOs configuráveis)
- **Microcontrolador RP2040**
- **Bibliotecas do Pico SDK** para controle de PWM
- **Simulador Wokwi** para testes

## Funcionamento
### Controle do Servomotor
- A GPIO 22 é configurada para gerar um sinal PWM de 50Hz (período de 20ms).
- O PWM controla a posição do servomotor de acordo com a largura do pulso:
  - **500µs** → **0°**
  - **1470µs** → **90°**
  - **2400µs** → **180°**

### Movimentação Periódica
- Após atingir as posições fixas, o código implementa um movimento gradual entre **0° e 180°**.
- O incremento do PWM é de **±5µs a cada 10ms**, garantindo um movimento fluido e contínuo.

### Interação com o LED RGB
- O LED RGB (GPIO 12) responde às variações do PWM.
- A intensidade do LED varia conforme o sinal PWM, criando um efeito de transição suave.

## Estrutura do Código
1. **Inicialização**: Configura os pinos GPIO, PWM e interrupções.
2. **Controle de Posições Fixas**: Define os pulsos PWM para 0°, 90° e 180°.
3. **Movimentação Suave**: Alterna o PWM de forma progressiva entre os ângulos.

## Autor
**Lucas Moreira da Silva**

Este projeto foi desenvolvido e testado utilizando a **BitDogLab** com o microcontrolador **RP2040**.
