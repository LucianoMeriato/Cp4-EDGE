# README do Projeto MQTT com ESP32


# Descrição
Este projeto utiliza um microcontrolador ESP32 para se conectar a uma rede Wi-Fi e interagir com um broker MQTT. Ele permite controlar um LED onboard e ler a luminosidade de um potenciômetro, enviando esses dados através de mensagens MQTT. Este exemplo é ideal para estudantes de eletrônica e programação que desejam aprender sobre IoT (Internet das Coisas) usando a linguagem C.

# Objetivos
Conectar o ESP32 a uma rede Wi-Fi.
Estabelecer comunicação com um broker MQTT.
Controlar um LED onboard com comandos recebidos via MQTT.
Ler o nível de luminosidade e publicar os dados no broker MQTT.

# Passos Iniciais
  1-Realizar o dowload do Firewall descomplicado
  
  2-Realizar o dowaload do Postman
  
  3-Criar um workspace
  
  4-Importar o arquivo do firewall descomplicado
  
  5-alterar a url do postman para a mesma usado no wokwi

  ![image](https://github.com/user-attachments/assets/3e25817d-e5cd-4f53-9b51-c9e6d1acd5b0)

# Estrutura do Código

# 1. Configurações Iniciais

O código define várias configurações essenciais, como:

	•	SSID e PASSWORD: As credenciais da rede Wi-Fi que o ESP32 irá utilizar.
	•	BROKER_MQTT e BROKER_PORT: Endereço IP e porta do broker MQTT para a comunicação.
	•	Tópicos MQTT: Definidos para assinatura e publicação de mensagens, divididos entre controle do LED e envio de dados de sensores.
	•	ID_MQTT: Identificação única do dispositivo no broker MQTT, essencial para evitar conflitos com outros dispositivos conectados ao mesmo broker.

# 2. Inicialização

setup()
Essa função é chamada uma vez quando o ESP32 é inicializado e realiza as seguintes tarefas:

	•	Inicializa os pinos de saída (LED e outros indicadores).
	•	Configura a comunicação serial para monitoramento.
	•	Conecta à rede Wi-Fi e ao broker MQTT.
	•	Publica o estado inicial do LED no broker, indicando que ele está desligado.

# 3. Loop Principal

loop()
Essa função é chamada repetidamente e tem as seguintes responsabilidades:

	•	Verificar as conexões Wi-Fi e MQTT, reconectando automaticamente em caso de perda.
	•	Enviar o estado atual do LED para o broker MQTT.
	•	Ler e publicar os valores de luminosidade de um potenciômetro e a leitura de um sensor de umidade/temperatura (DHT11).
	•	Controlar os LEDs indicadores de acordo com a luminosidade lida.

# 4. Conexão Wi-Fi e MQTT

As funções initWiFi(), reconectWiFi(), initMQTT() e reconnectMQTT() gerenciam a conexão com a rede Wi-Fi e o broker MQTT. Elas tentam se reconectar automaticamente sempre que uma conexão for perdida, garantindo que o dispositivo esteja sempre online.

# 5. Callback MQTT

mqtt_callback()
Essa função é acionada sempre que uma mensagem é recebida em um dos tópicos inscritos. Dependendo do conteúdo da mensagem recebida, ela pode ligar ou desligar o LED onboard.

	•	Mensagem “hosp7771@on|”: Liga o LED.
	•	Mensagem “hosp7771@off|”: Desliga o LED.

# 6. Monitoramento de Luminosidade

analogRead() e map()
O valor do potenciômetro é lido através da função analogRead(), e a luminosidade é normalizada para uma escala de 0% a 100%. Esse valor é então publicado em um tópico MQTT específico para monitoramento remoto.

# 7. Controle do LED

As funções InitOutput(), EnviaEstadoOutputMQTT() e VerificaConexoesWiFIEMQTT() controlam o LED onboard e garantem a comunicação com o broker. Elas publicam o estado do LED (ligado ou desligado) e garantem que as conexões Wi-Fi e MQTT estejam ativas.

# Execuçâo do Projeto 




https://github.com/user-attachments/assets/4fa16ba3-3a7f-4d2f-83b8-9541c3d373a8



# RM
  # eric 557082

  # Luciano 554546

  # Pietro 57283


