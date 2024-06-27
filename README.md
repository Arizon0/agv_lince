# Versão PT-BR:
# Projeto AGV-CAR (Lince - Facens 2024)

#Hardware + Versões recomendadas:

Raspberry Pi 3 B+ (NÃO RECOMENDADO)
Raspberry Pi 4 em diante (RECOMENDADO)
Jetson NANO em diante (RECOMENDADO)

Todas placas precisam ter no minimo 4GB Ram, placas com menos poderá existir limitações!

O projeto foi desenvolvido na versão 20.04.6 LTS versão Desktop:
https://releases.ubuntu.com/focal/

Caso seja utilizado uma Jetson utilize a versão do SDK VERSÃO 5.1.2 (RECOMENDADO)
Para efetuar a utilização da camera ZED 1 ou ZED 2 o SDK da Jetson é necessario no maximo a Versão 5.1.2!!

SDK ZED versão 4.1.2 OBS: Compativel com SDK da Jetson apenas na versão 5.1.2!


#Instalação SDK Jetson:

É necessario um Desktop com o Ubuntu instalado para que efetue o downloads do SDK Nvidia e seus demais arquivos para instalação na Jetson
https://developer.nvidia.com/sdk-manager

Ápos instalar o SDK Manager no Desktop, conecte a Jetson via cabo USB-C (Frente) no Desktop e inicie ela no modo de formatação (Clicando ao mesmo tempo os Botões de Ligar e Forçcar Reinicialização (Botão Power e o do Meio))

Ápos isso o software SDK Manager no Desktop ira reconhecer o modelo da Jeton.
Logo abaixo selecione para instalar a versão desejada, confirme e NEXT Step!
Aceite os termos e clique em instalar.

ATENÇÃO!!
Existe uma grande chance de que mesmo selecionado para instalar o Jetson Tools e CUDA no Step 2 eles não sejam instalados, o link abaixo podera ajudar!
https://docs.nvidia.com/sdk-manager/install-with-sdkm-jetson/index.html

Caso mesmo assim não seja instalado com sucesso o CUDA, recomendo formatar novamente e instalar o SDK na Jetson sem nenhum Componente a mais!
e Instalar após ela iniciar, manualmente com o comando:

$ sudo apt update 
$ sudo apt upgrade
$ sudo apt install nvidia-jetpack

Após terminar a instalação verifique a versão instalada:
$ sudo apt show nvidia-jetpack

#Intalação do ROS2 - FOXY
SIGA O PASSO A PASSO NESTE SITE DO ROS:
https://docs.ros.org/en/foxy/Installation.html

Versão recomendada é 
https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html

OBS: Não é necessario dar os comandos SUDO dentro de alguma pasta!

#Instalação Componentes extras:
Fica obrigatório executar toda está lista de comandos após efetuar a instalação do SDK Jetson a cima!

$ sudo apt update
$ sudo apt upgrade
$ sudo apt install git
$ sudo apt install ros-foxy-xacro
$ sudo apt install python3-colcon-common-extensions
$ sudo apt install ros-foxy-ros2-control ros-foxy-ros2-controllers ros-foxy-gazebo-ros2-control

Estes comandos devem ser dado tando no DESKTOP quanto no AGV!

#Instalação dos Pacotes:
Para efetuar a copia e downloads dos pacotes e algoritimo do Robo crie uma pasta no Desktop e no Robo (Jetson ou Raspberry) cujo nome deve ser:

Exemplos
Desktop - Desktop (pc_ws) Obrigatorio possuir _ws 
Robo - Robo name (agv_ws) Obrigatorio possuir _ws 

Após criar a pasta do robo e desktop name_ws é necessario criar dentro dela outra pasta cujo nome precisa ser (src) deve se criar em ambas maquinas.
dentro das pastas src (/Desktop/agv_ws/src) precisara dar o seguinte comandos:

$ git clone Pacotes
$ git clone Pacotes
$ git clone Pacotes

e no DESKTOP (PC RESPONSAVEL PELO VOLANTE)

$ git clone Pacotes