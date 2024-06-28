# EN-US (English) Version:
# Project AGV-CAR (Lince - Facens 2024)

Hardware + Recommended Versions:

* Raspberry Pi 3 B+ (NOT RECOMMENDED)
* Raspberry Pi 4 and later (RECOMMENDED)
* Jetson NANO and later (RECOMMENDED)

All boards need to have at least 4GB of RAM. Boards with less may face limitations!

The project was developed on version 20.04.6 LTS Desktop version:
https://releases.ubuntu.com/focal/

If using a Jetson, use SDK VERSION 5.1.2 (RECOMMENDED).
To use the ZED 1 or ZED 2 camera, the Jetson SDK is required up to version 5.1.2!

ZED SDK version 4.1.2 NOTE: Compatible with Jetson SDK only up to version 5.1.2!

Jetson SDK Installation:

You need a desktop with Ubuntu installed to download the Nvidia SDK and other files for installation on the Jetson:
https://developer.nvidia.com/sdk-manager

After installing the SDK Manager on the desktop, connect the Jetson via USB-C cable (front) to the desktop and start it in formatting mode (simultaneously pressing the Power and Force Restart buttons).

After that, the SDK Manager software on the desktop will recognize the Jetson model.
Select the desired version to install, confirm, and click NEXT Step!
Accept the terms and click install.

ATTENTION!!
There is a high chance that even if you select to install Jetson Tools and CUDA in Step 2, they may not be installed. The link below might help:
https://docs.nvidia.com/sdk-manager/install-with-sdkm-jetson/index.html

If CUDA is still not installed successfully, I recommend reformatting and installing the SDK on the Jetson without any additional components.
Then, after it starts, install manually with the command:

```Linux	
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install nvidia-jetpack
```
After the installation is complete, check the installed version:
```Linux
$ sudo apt show nvidia-jetpack
```
ROS2 - FOXY Installation:

FOLLOW THE STEP-BY-STEP GUIDE ON THIS ROS SITE:
https://docs.ros.org/en/foxy/Installation.html

The recommended version is:
https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html

NOTE: It is not necessary to use SUDO commands inside any folder!

Extra Components Installation:

It is mandatory to run all these commands after installing the Jetson SDK above!
```Linux
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install git
$ sudo apt install ros-foxy-xacro
$ sudo apt install python3-colcon-common-extensions
$ sudo apt install ros-foxy-ros2-control ros-foxy-ros2-controllers ros-foxy-gazebo-ros2-control
```
These commands should be run both on the DESKTOP and on the AGV!

Packages Installation:

To copy and download the robot’s packages and algorithms, create a folder on the Desktop and on the Robot (Jetson or Raspberry) with the following naming convention:

Examples:
Desktop - Desktop (pc_ws) It must contain _ws
Robot - Robot name (agv_ws) It must contain _ws

After creating the folder for the robot and desktop name_ws, it is necessary to create another folder inside it named (src) on both machines.
Inside the src folders (/Desktop/agv_ws/src), run the following commands:
```Linux
$ git clone Packages
$ git clone Packages
$ git clone Packages
```
And on the DESKTOP (PC RESPONSIBLE FOR THE STEERING WHEEL):
```Linux
$ git clone Packages
```


# Versão em Português (Brasil)
# Projeto AGV-CAR (Lince - Facens 2024)

Hardware + Versões recomendadas:

	•	Raspberry Pi 3 B+ (NÃO RECOMENDADO)
	•	Raspberry Pi 4 em diante (RECOMENDADO)
	•	Jetson NANO em diante (RECOMENDADO)

Todas as placas precisam ter no mínimo 4GB de RAM. Placas com menos podem ter limitações!

O projeto foi desenvolvido na versão 20.04.6 LTS versão Desktop:
https://releases.ubuntu.com/focal/

Caso seja utilizada uma Jetson, utilize a versão do SDK VERSÃO 5.1.2 (RECOMENDADO).
Para utilizar a câmera ZED 1 ou ZED 2, o SDK da Jetson é necessário no máximo até a versão 5.1.2!

SDK ZED versão 4.1.2 OBS: Compatível com o SDK da Jetson apenas na versão 5.1.2!

Instalação SDK Jetson:

É necessário um desktop com o Ubuntu instalado para efetuar o download do SDK Nvidia e seus demais arquivos para instalação na Jetson:
https://developer.nvidia.com/sdk-manager

Após instalar o SDK Manager no desktop, conecte a Jetson via cabo USB-C (frente) no desktop e inicie-a no modo de formatação (clicando ao mesmo tempo os botões de ligar e forçar reinicialização (botão Power e o do meio)).

Após isso, o software SDK Manager no desktop irá reconhecer o modelo da Jetson.
Logo abaixo, selecione para instalar a versão desejada, confirme e NEXT Step!
Aceite os termos e clique em instalar.

ATENÇÃO!!
Existe uma grande chance de que, mesmo selecionado para instalar o Jetson Tools e CUDA no Step 2, eles não sejam instalados. O link abaixo poderá ajudar:
https://docs.nvidia.com/sdk-manager/install-with-sdkm-jetson/index.html

Caso, mesmo assim, não seja instalado com sucesso o CUDA, recomendo formatar novamente e instalar o SDK na Jetson sem nenhum componente a mais!
Instale manualmente após ela iniciar, com o comando:
```Linux
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install nvidia-jetpack
```
Após terminar a instalação, verifique a versão instalada:
```Linux
$ sudo apt show nvidia-jetpack
```
Instalação do ROS2 - FOXY

SIGA O PASSO A PASSO NESTE SITE DO ROS:
https://docs.ros.org/en/foxy/Installation.html

A versão recomendada é:
https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html

OBS: Não é necessário dar os comandos SUDO dentro de alguma pasta!

Instalação de Componentes Extras:

É obrigatório executar toda esta lista de comandos após efetuar a instalação do SDK Jetson acima!

```Linux
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install git
$ sudo apt install ros-foxy-xacro
$ sudo apt install python3-colcon-common-extensions
$ sudo apt install ros-foxy-ros2-control ros-foxy-ros2-controllers ros-foxy-gazebo-ros2-control
```
Estes comandos devem ser dados tanto no DESKTOP quanto no AGV!

Instalação dos Pacotes:

Para efetuar a cópia e download dos pacotes e algoritmos do robô, crie uma pasta no Desktop e no Robô (Jetson ou Raspberry) com o seguinte nome:

Exemplos:
Desktop - Desktop (pc_ws) Obrigatório possuir _ws
Robô - Nome do Robô (agv_ws) Obrigatório possuir _ws

Após criar a pasta do robô e desktop name_ws, é necessário criar dentro dela outra pasta chamada (src). Isso deve ser feito em ambas as máquinas.
Dentro das pastas src (/Desktop/agv_ws/src), você precisará dar os seguintes comandos:
```Linux
$ git clone Pacotes
$ git clone Pacotes
$ git clone Pacotes
```
E no DESKTOP (PC RESPONSÁVEL PELO VOLANTE):
```Linux
$ git clone Pacotes
```
