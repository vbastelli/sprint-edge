Aqui está tudo em um formato de fácil cópia e cola para o seu arquivo `README.md` no GitHub:


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

### **1. Configurar a Máquina Virtual no Azure**
- Criar uma máquina virtual no Azure.
- Instalar o Docker:
  ```bash
  sudo apt-get update
  sudo apt-get install docker.io
  ```
- Clonar o repositório **Fiware Descomplicado**:
  ```bash
  git clone https://github.com/fiware/fiware-descomplicado.git
  ```

### **2. Executar o Simulador Wokwi**
- No **Wokwi**, utilize o ESP32 conectado ao sensor **DHT22** e ao sensor de luminosidade.
- O código do ESP32 pode ser encontrado na pasta `/src`. Ele coleta dados dos sensores e os envia para o **Postman**.

### **3. Testar a Comunicação com o Postman**
- Abra o **Postman** e configure a Collection para visualizar os dados recebidos do ESP32.
- Verifique as leituras dos sensores sendo enviadas em tempo real.

## **Como Usar**

### **1. Executar a Plataforma**
- Após configurar a máquina virtual no Azure e instalar o Docker, rode os containers do FIWARE:
  ```bash
  docker-compose up
  ```

### **2. Executar a Simulação no Wokwi**
- Acesse a plataforma Wokwi e faça a simulação utilizando o código presente no projeto. Certifique-se de que a comunicação com o Postman está funcionando corretamente.
  
### **3. Visualização dos Dados**
- Utilize o Postman para monitorar os dados recebidos.
- Opcionalmente, crie dashboards personalizados para exibir as leituras de temperatura e luminosidade de forma visual.

## **Contribuições**
Contribuições são bem-vindas! Se você deseja colaborar com melhorias neste projeto, siga os passos abaixo:
1. Faça um fork do repositório.
2. Crie uma branch com a nova feature (`git checkout -b feature/nova-feature`).
3. Faça o commit das alterações (`git commit -m 'Add nova feature'`).
4. Envie o push para a branch (`git push origin feature/nova-feature`).
5. Abra um Pull Request.
