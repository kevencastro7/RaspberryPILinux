PROCEDIMENTO PARA A UTILIZAÇÃO DE INTERNET NO DEBIAN

1. Alterar a rede

  a. Editar o arquivo utilizando o seguinte comando:
    
    nano /etc/network/interfaces
    
  b. Coloque o seguinte conteúdo:
  
    # interfaces(5) file used by ifup(8) and ifdown(8)
    auto lo
    iface lo inet loopback

    allow-hotplug eth0
    auto eth0
    iface eth0 inet dhcp

    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.254
    
2. Habilitar a comunicação SSH

  a. Instalar o seguinte pacote:
    
    apt-get install openssh-client openssh-server
    
  b. Editar o arquivo utilizando o seguinte comando:
    
    nano /etc/ssh/sshd_config
    
  c.
