# **IoT Data Collection and Edge Computing using ESP32 and FIWARE**

## **Project Description**
Este projeto faz parte do Sprint 3 de desenvolvimento da arquitetura para uma aplicação IoT. Ele demonstra como a arquitetura IoT pode ser configurada para coletar dados de dispositivos conectados (como sensores de temperatura e luminosidade), processá-los utilizando o ESP32 e transmitir esses dados para uma plataforma de backend, com visualização em dashboards. 

O projeto utiliza a infraestrutura de Edge Computing, permitindo o processamento de dados no próprio dispositivo (ESP32) e, posteriormente, transmitindo-os para a nuvem, garantindo uma solução eficiente e escalável. O **FIWARE** foi usado para gerenciar e visualizar os dados, e a aplicação foi simulada no **Wokwi**.

## **Table of Contents**
1. [Motivação](#motivação)
2. [Tecnologias Utilizadas](#tecnologias-utilizadas)
3. [Instalação e Configuração](#instalação-e-configuração)
4. [Como Usar](#como-usar)
5. [Contribuições](#contribuições)
6. [Licença](#licença)

## **Motivação**
Este projeto foi desenvolvido para demonstrar uma aplicação prática da Internet das Coisas (IoT) em um ambiente de Edge Computing. A ideia é mostrar como dispositivos IoT podem coletar dados, processá-los localmente e enviar informações para a nuvem utilizando o **FIWARE**. A motivação central é explorar o uso de uma plataforma IoT que seja eficiente e escalável.

## **Tecnologias Utilizadas**
- **ESP32**: Microcontrolador usado para coletar dados dos sensores.
- **DHT22**: Sensor de temperatura e umidade.
- **Sensor de Luminosidade**: Medição da intensidade de luz ambiente.
- **Wokwi**: Simulação de hardware para desenvolvimento de código de IoT.
- **Postman**: Ferramenta para testar e visualizar as requisições de dados enviadas pelo ESP32.
- **FIWARE**: Plataforma open-source para gerenciar dados de IoT.
- **Azure**: Infraestrutura de nuvem usada para hospedar a máquina virtual.
- **Docker**: Ferramenta para containerização, usada na VM para rodar o FIWARE.
- **Visual Studio Code**: Ambiente de desenvolvimento integrado (IDE).

## **Instalação e Configuração**

### **1. Clonar o Repositório**
```bash
git clone <URL do repositório>
cd <nome do projeto>
