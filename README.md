# SIGA - Sistema Inteligente de Agricultura Familiar

O **SIGA** é um sistema embarcado com interface web desenvolvido para a **1ª Jornada de Inovação da Agricultura Familiar**, promovida pela Agência de Inovação e Empreendedorismo da Universidade Estadual do Maranhão - **Agência Marandu/UEMA**, em parceria com a **Secretaria de Estado da Agricultura Familiar - SAF** e com apoio da **FAPEMA**.

O projeto tem como objetivo auxiliar agricultores familiares no monitoramento ambiental de pequenas áreas produtivas, utilizando sensores para coletar dados de **umidade, temperatura e pressão atmosférica**. As informações são exibidas em tempo real por meio de uma **interface web**, permitindo que o usuário acompanhe as condições do ambiente de forma simples e acessível.

Além do monitoramento, o sistema conta com um **servo motor** que simula a ativação automática de um irrigador, representando uma solução de irrigação inteligente baseada nas condições detectadas pelos sensores.

## Objetivo do projeto

Desenvolver uma solução tecnológica de baixo custo, acessível e aplicável à agricultura familiar, capaz de monitorar variáveis ambientais e simular a tomada de decisão automática para irrigação.

O sistema busca contribuir para:

- Uso mais eficiente da água;
- Apoio à tomada de decisão no campo;
- Automação de processos agrícolas;
- Monitoramento ambiental em tempo real;
- Incentivo ao uso de tecnologias embarcadas na agricultura familiar.

## Funcionalidades

- Leitura de temperatura ambiente;
- Leitura de umidade do ar;
- Leitura de pressão atmosférica;
- Cálculo de temperatura média entre sensores;
- Exibição dos dados no terminal serial;
- Exibição dos dados em display OLED;
- Interface web para acompanhamento em tempo real;
- Funcionamento em modo Access Point com o Raspberry Pi Pico W;
- Simulação de irrigação automática com servo motor;
- Modo manual para controle do irrigador via interface web.

## Hardware utilizado

- Raspberry Pi Pico W;
- Sensor AHT10 para temperatura e umidade;
- Sensor BMP280 para temperatura e pressão atmosférica;
- Display OLED via I2C;
- Servo motor para simulação da irrigação;
- Jumpers e protoboard.

## Organização dos sensores e atuadores

| Componente | Função | Comunicação / Pino |
|---|---|---|
| AHT10 | Mede temperatura e umidade | I2C0 - SDA GPIO0 / SCL GPIO1 |
| BMP280 | Mede temperatura e pressão | I2C0 - SDA GPIO0 / SCL GPIO1 |
| Display OLED | Exibe os dados localmente | I2C1 - SDA GPIO14 / SCL GPIO15 |
| Servo motor | Simula o irrigador automático | PWM - GPIO16 |
| Pico W | Processamento e servidor web | Wi-Fi Access Point |

## Tecnologias utilizadas

- Linguagem C;
- Raspberry Pi Pico SDK;
- CMake;
- Wi-Fi em modo Access Point;
- Servidor web embarcado;
- Comunicação I2C;
- PWM para controle do servo motor;
- Display OLED SSD1306;
- Sensores AHT10 e BMP280.

## Estrutura do projeto

```text
SIGA/
├── MARANDU.c
├── CMakeLists.txt
├── include/
│   ├── aht10.h
│   ├── bmp280.h
│   ├── wifi_ap.h
│   ├── display_oled.h
│   ├── irrigador.h
│   └── servo_irrigador.h
├── src/
│   ├── aht10.c
│   ├── bmp280.c
│   ├── wifi_ap.c
│   ├── display_oled.c
│   ├── ssd1306_i2c.c
│   ├── irrigador.c
│   └── servo_irrigador.c
├── dhcpserver/
│   └── dhcpserver.c
└── dnsserver/
    └── dnsserver.c
