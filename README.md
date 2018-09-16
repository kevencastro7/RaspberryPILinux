PROCEDIMENTO PARA A UTILIZAÇO DO BUILDROOT
 
1. Instalação das dependências


	a. Instalar os seguintes pacotes:
  
		sudo apt-get install sed make binutils build-essential gcc g++ bash patch gzip bzip2 perl tar cpio python unzip rsync file file bc wget libncurses5-dev libncursesw5-dev g++-multilib gcc-multilib 

2. Instalação do Buidroot
	a. Baixar buildroot
  
	b. https://buildroot.org/download.html
	
	c. Abrir o terminal na pasta do buildroot-xxxx.xx.x.tar.gz
  
	d. Descompactar:
  
		tar -vzxf buildroot-xxxx.xx.x.tar.tar.gz

3. Escolha da configuração padrão

	a. Veja quais configurações padrões estão disponíveis:
  
		make list-defconfigs
    
	b. Escolha a que se encaixa com seu projeto. Ex:
  
		make beaglebone_defconfig

4. Configuração do Buildroot

	a. Entrar no menu de configuração:
  
		make menuconfig
    
	b. Verificar a arquitetura do processador em Target options
  
	c. Configurar as opções de build em Build options
  
	d. Escolher as ferramentas de desenvolvimento em Toolchain options
  
	e. Configurar o sistema em System configuration
  
	d. Configurar o Kernel
  
	e. Escolher os pacotes necessários em Target packages

5. Configuração do linux

	a. Entrar no menu de configuração:
  
		make linux-menuconfig
    
	b. Decidir o que vai ser utilizado on linux
  
	c. Configurar o próprio Linux

6. Construção da imagem

	a. Baixar os pacotes necessários:
  
		make source
    
	b. Começar o processo de construção da imagem:
  
		make

7. Gravar a imagem no SD Card

	a. Procurar a imagem gerada:
  
		output/images/sdcard.img
    
	b. Gravar no SD utilizando o gnome-disk-utils
 
