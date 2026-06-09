# GS-PROJETO-RASTREAMENTO-DE-DETRITOS
Sistema de segurança capaz de rastrear a órbita da Terra para obter informação sobre aproximação de detritos espaciais.

## Descrição do Projeto

O crescimento da quantidade de detritos espaciais em órbita terrestre representa uma ameaça constante para satélites, estações espaciais e futuras missões aeroespaciais. Pequenos fragmentos podem causar danos significativos quando colidem com equipamentos em alta velocidade.

Este projeto apresenta uma solução educacional baseada em Arduino para simular um sistema de monitoramento orbital capaz de detectar a proximidade de possíveis detritos espaciais e alertar operadores sobre diferentes níveis de risco.

A solução foi desenvolvida utilizando componentes eletrônicos simples e simulada na plataforma Wokwi, demonstrando conceitos de sensoriamento, monitoramento em tempo real e sistemas embarcados.

---

# Objetivo da Solução

Desenvolver um sistema capaz de:

- Monitorar continuamente a distância de objetos próximos.
- Simular a identificação de detritos espaciais em órbita.
- Classificar automaticamente o nível de risco.
- Informar o operador por meio de alertas visuais e sonoros.
- Demonstrar aplicações de IoT e Computação de Borda em sistemas críticos.

---

# Componentes Utilizados

| Componente | Quantidade |
|------------|------------|
| Half Breadboard | 1 |
| Arduino Uno | 1 |
| Sensor Ultrassônico HC-SR04 | 1 |
| Display LCD 16x2 com interface I2C | 1 |
| LED Verde | 1 |
| LED Laranja | 1 |
| LED Vermelho | 1 |
| Buzzer | 1 |
| Resistores | 3 |

---

# Funcionamento do Sistema

O sensor ultrassônico HC-SR04 mede continuamente a distância entre o sistema e um objeto.

Essa distância é utilizada para representar, de forma simulada, a proximidade entre um satélite e possíveis detritos espaciais.

Com base no valor medido, o sistema classifica a situação em três estados:

## 1) Órbita Segura

**Condição:**

Distância maior ou igual a 150 km (simulados)

**Ações:**

- LED verde ligado.
- LCD exibe:
  - "ORBITA SEGURA"
  - "Monitorando"
- Buzzer emite sinal breve e de baixa frequência.

---

## 2) Detrito Próximo

**Condição:**

Distância entre 50 km e 149 km (simulados)

**Ações:**

- LED laranja ligado.
- LCD exibe:
  - "DETRITO PROXIMO"
  - Distância detectada.
- Buzzer emite alerta intermitente.

---

## 3) Alerta de Colisão

**Condição:**

Distância menor que 50 km (simulados)

**Ações:**

- LED vermelho ligado.
- LCD exibe:
  - "ALERTA: COLISAO!"
  - Distância detectada.
- Buzzer permanece ativo com frequência elevada.

---

# Estrutura do Circuito

## Mapeamento de Pinos

| Componente | Pino Arduino |
|------------|-------------|
| HC-SR04 Trigger | 9 |
| HC-SR04 Echo | 10 |
| LED Vermelho | 12 |
| LED Verde | 13 |
| LED Laranja | 7 |
| Buzzer | 11 |
| LCD SDA | A4 |
| LCD SCL | A5 |
| Alimentação LCD | 5V |
| GND LCD | GND |

---

## Ligações dos LEDs

### LED Vermelho (LedR)
- Positivo → Pino 12
- Negativo → Resistor → GND

### LED Verde (LedG)
- Positivo → Pino 13
- Negativo → Resistor → GND

### LED Laranja (LedO)
- Positivo → Pino 7
- Negativo → Resistor → GND

---

## Ligações do Sensor HC-SR04

| HC-SR04 | Arduino |
|----------|----------|
| VCC | 5V |
| GND | GND |
| TRIG | 9 |
| ECHO | 10 |

---

## Ligações do LCD I2C

| LCD I2C | Arduino |
|----------|----------|
| VCC | 5V |
| GND | GND |
| SDA | A4 |
| SCL | A5 |

---

## Ligações do Buzzer

| Buzzer | Arduino |
|---------|----------|
| Positivo | 11 |
| Negativo | GND |

---

# Lógica Implementada

1. O Arduino envia um pulso ao sensor ultrassônico.
2. O sensor calcula a distância até o objeto.
3. O valor é convertido para uma distância simulada em quilômetros.
4. O sistema verifica a faixa de distância:
   - Menor que 50 → Colisão iminente.
   - Entre 50 e 150 → Atenção.
   - Maior que 150 → Situação segura.
5. LEDs, buzzer e display LCD são atualizados.
6. O ciclo se repete continuamente.

---

# Tecnologias Utilizadas

- Arduino Uno
- Linguagem C++
- Biblioteca LiquidCrystal_I2C
- Wokwi Simulator
- Computação Embarcada
- Sensoriamento Ultrassônico

---

# Instruções de Execução

## Executando no Wokwi

1. Abra o projeto no Wokwi. Link: https://wokwi.com/projects/465842634128269313
2. Inicie a simulação.
3. Altere a distância do objeto no sensor HC-SR04.
4. Observe:
   - Mudança dos LEDs.
   - Mensagens exibidas no LCD.
   - Alertas sonoros emitidos pelo buzzer.

---

# Aplicação Prática

Sistemas semelhantes são utilizados por agências espaciais e empresas privadas para monitoramento orbital, prevenção de colisões e gerenciamento de tráfego espacial.

A solução demonstra como sensores e sistemas embarcados podem auxiliar na tomada de decisão em ambientes críticos.

---

# Melhorias Futuras

- Integração com ESP32 para monitoramento remoto.
- Envio de alertas para aplicativos móveis.
- Armazenamento de eventos em banco de dados.
- Dashboard web para acompanhamento em tempo real.
- Integração com APIs de rastreamento orbital.
- Simulação de múltiplos detritos simultaneamente.

---

# Integrantes do Grupo

- Lucas Rodrigo Gomes Pinheiro RM572580
- Felipe Satio Machado Morita RM568859
- Felipe Medino Neves RM573287
- Raphael dos Santos Benevides RM573378

