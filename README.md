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
O código define várias configurações editáveis no início, como:

SSID e PASSWORD: Credenciais da rede Wi-Fi.
BROKER_MQTT e BROKER_PORT: Endereço IP e porta do broker MQTT.
Tópicos: Tópicos para assinatura e publicação de mensagens.
ID_MQTT: Identificador do dispositivo MQTT.

# 2. Inicialização
setup()
A função setup() é chamada uma vez ao iniciar o dispositivo. Ela inicializa o LED, a comunicação serial, a conexão Wi-Fi e a configuração do MQTT. Após um atraso, o estado inicial do LED é enviado ao broker.

# 3. Loop Principal
loop()
A função loop() é executada repetidamente e verifica as conexões Wi-Fi e MQTT, envia o estado do LED e processa as mensagens recebidas.

# 4. Conexões Wi-Fi e MQTT
initWiFi() e reconectWiFi()
Essas funções gerenciam a conexão com a rede Wi-Fi, tentando se reconectar se a conexão for perdida.

initMQTT() e reconnectMQTT()
Essas funções configuram a conexão com o broker MQTT e tentam reconectar quando necessário.

# 5. Callback MQTT
mqtt_callback()
Essa função é chamada quando uma nova mensagem é recebida em um tópico inscrito. Dependendo do conteúdo da mensagem, o LED é ligado ou desligado.

# 6. Monitoramento de Luminosidade
handleLuminosity()
Esta função lê o valor de um potenciômetro conectado ao pino 34 e publica o nível de luminosidade em um tópico específico.

# 7. Controle do LED
InitOutput(), VerificaConexoesWiFIEMQTT(), e EnviaEstadoOutputMQTT()
Essas funções inicializam o pino do LED, verificam as conexões e enviam o estado atual do LED para o broker.

# Compilação e Execução
Instalar a IDE: Certifique-se de ter a Arduino IDE instalada com suporte para ESP32.

Bibliotecas: Instale as bibliotecas necessárias:

WiFi
PubSubClient

Carregar o Código: Copie e cole o código acima na IDE, fazendo as modificações necessárias nas configurações.

Conectar ao ESP32: Selecione a porta correta e faça o upload do código para o ESP32.

Monitor Serial: Abra o Monitor Serial para acompanhar a saída e as mensagens.


# Conclusão
Este projeto demonstrou como integrar o microcontrolador ESP32 a uma rede Wi-Fi e a um broker MQTT, possibilitando a comunicação em tempo real e o controle de dispositivos. Ao implementar o controle de um LED e a leitura de luminosidade através de um potenciômetro, aprendemos sobre os conceitos fundamentais de IoT e a aplicação prática de protocolos de comunicação como o MQTT.

Durante o desenvolvimento, foram abordados aspectos importantes, como a configuração de conexões, a manipulação de mensagens e a interação com sensores e atuadores. Este projeto não só fornece uma base sólida para entender a comunicação entre dispositivos, mas também incentiva a exploração de novas funcionalidades, como a adição de mais sensores ou o desenvolvimento de uma interface de usuário.


# Execuçâo do Projeto 


