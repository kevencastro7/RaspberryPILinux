PROCEDIMENTO PARA A INSTALAÇÃO DO FILESYSTEM COM DEBOOTSTRAP

1. Instalação das dependências

  	a. Instalar os seguintes pacotes:
  
    		sudo apt-get install debootstrap qemu binfmt-support qemu-user-static
2. Utilização do debootstrap:

  	a. Formatar a partição 2 para ext4
  
  	b. Montar o SD Card
	
   			sudo mount /dev/mmcblk0p2 /mnt
  	c. Instalar o debootstrap:
  
    		sudo debootstrap --arch armel --foreign wheezy /mnt http://ftp.us.debian.org/debian/
3. Emulação do ARM:

  	a. Copiar o pacote para o filesystem:
  
    		sudo cp /usr/bin/qemu-arm-static /mnt/usr/bin/
    
  	b. Iniciar a emulação:
  
    		sudo chroot /mnt /usr/bin/qemu-arm-static /bin/sh -i
    
  	c. Terminar a instalção do debootstrap:
  
    		/debootstrap/debootstrap --second-stage
    
  	d. Troque a senha
  
    		passwd

4. Modo de Escredita e leitura

mount -o remount,rw /dev/hda2 /


