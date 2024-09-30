# **IoT Data Collection and Edge Computing using ESP32 and FIWARE**

## **Project Description**
Este projeto faz parte do Sprint 3, focado no desenvolvimento de uma arquitetura para uma aplicação IoT. Ele demonstra como configurar uma arquitetura IoT para coletar dados de dispositivos conectados, como sensores de temperatura e luminosidade, processar esses dados utilizando o ESP32 e transmiti-los para uma plataforma de backend com visualização em dashboards.

A infraestrutura de **Edge Computing** é utilizada para o processamento de dados no dispositivo (ESP32) e posterior transmissão para a nuvem, oferecendo uma solução eficiente e escalável. A plataforma **FIWARE** foi empregada para gerenciamento e visualização dos dados, enquanto o hardware e código foram simulados no **Wokwi**.

## **Table of Contents**
1. [Motivação](#motivação)
2. [Tecnologias Utilizadas](#tecnologias-utilizadas)
3. [Instalação e Configuração](#instalação-e-configuração)
4. [Como Usar](#como-usar)
5. [Contribuições](#contribuições)
6. [Licença](#licença)
7. [Visualização de Dados com Dash](#visualização-de-dados-com-dash)

## **Motivação**
Este projeto visa explorar a aplicação prática da **Internet das Coisas (IoT)** em um ambiente de **Edge Computing**, demonstrando como dispositivos IoT podem coletar e processar dados localmente antes de enviá-los para a nuvem. A motivação é desenvolver uma solução eficiente, escalável e capaz de gerenciar grandes volumes de dados com a plataforma **FIWARE**.

## **Tecnologias Utilizadas**
- **ESP32**: Microcontrolador responsável por coletar dados dos sensores.
- **DHT22**: Sensor de temperatura e umidade.
- **Sensor de Luminosidade**: Responsável pela medição da intensidade da luz ambiente.
- **Wokwi**: Simulador de hardware para desenvolvimento de código IoT.
- **Postman**: Ferramenta para testar e monitorar as requisições de dados.
- **FIWARE**: Plataforma open-source para gerenciamento de dados IoT.
- **Azure**: Infraestrutura de nuvem utilizada para hospedar a máquina virtual (VM).
- **Docker**: Ferramenta para containerização, usada na VM para rodar o FIWARE.
- **Dash**: Framework para construir aplicações web interativas em Python.

## **Instalação e Configuração**

### **1. Configurar a Máquina Virtual no Azure**
1. Crie uma máquina virtual (VM) no Azure com o sistema operacional Ubuntu.
2. Instale o **Docker** para rodar o FIWARE:

### Comandos para instalar o Docker no Ubuntu:

```bash
# Atualizar pacotes existentes
sudo apt-get update

# Instalar pacotes necessários
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

# Adicionar chave GPG oficial do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Adicionar o repositório do Docker
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Atualizar pacotes novamente e instalar Docker
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

# Verificar se o Docker está funcionando
sudo systemctl status docker

# Adicionar seu usuário ao grupo Docker para evitar uso do 'sudo' (opcional)
sudo usermod -aG docker $USER
```

3. Teste a instalação do Docker com:
```bash
docker run hello-world
```

4. Clone o repositório **Fiware Descomplicado**:
```bash
git clone https://github.com/fiware/fiware-descomplicado.git
```

### **2. Executar o Simulador Wokwi**
- No **Wokwi**, simule o ESP32 conectado ao sensor **DHT22** e ao sensor de luminosidade.
- O código para o ESP32 está na pasta `/src`. Ele coleta dados dos sensores e os envia para o **Postman**.

### **3. Testar a Comunicação com o Postman**
- Abra o **Postman** e configure uma Collection para visualizar as requisições de dados do ESP32.
- Verifique se os dados dos sensores estão sendo recebidos em tempo real.

## **Como Usar**

### **1. Executar a Plataforma FIWARE**
- Após configurar a VM no Azure e instalar o Docker, rode os containers do FIWARE usando o comando:
```bash
docker-compose up
```

### **2. Simulação no Wokwi**
- Acesse o **Wokwi** e simule o funcionamento do ESP32 com o código fornecido no projeto. Verifique a comunicação correta com o **Postman** para o recebimento dos dados.

### **3. Visualizar os Dados**
- Monitore os dados no **Postman** e crie dashboards para exibir visualmente as leituras de temperatura e luminosidade.

## **Visualização de Dados com Dash**
O aplicativo Dash permite visualizar os dados de luminosidade coletados em tempo real. O código para a aplicação Dash é o seguinte:

 **arquivo:**
- dashboard.py

### **Explicação do Código:**
- O aplicativo Dash coleta dados de luminosidade da API e atualiza o gráfico a cada 10 segundos.
- Os dados são armazenados em um `dcc.Store`, que permite manter o estado da aplicação entre atualizações.
- Os timestamps são convertidos para o horário de Lisboa para melhor visualização.
