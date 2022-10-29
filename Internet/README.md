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
    		iface eth0 inet static

    		address 192.168.1.100
    		netmask 255.255.255.0
    		gateway 192.168.1.254
   
  	c. Editar o arquivo utilziando o seguinte comando:
     
     		nano /etc/resolv.conf
     
  	d. Coloque o seguinte conteúdo:
      
      		nameserver 8.8.8.8
      		nameserver 8.8.4.4
    
2. Habilitar a comunicação SSH

  	a. Instalar o seguinte pacote:
    
    		apt-get install openssh-client openssh-server
    
  	b. Editar o arquivo utilizando o seguinte comando:
    
    		nano /etc/ssh/sshd_config
    
  	c. Procurar essa linha:
    
    		PermitRootLogin
    
  	d. E alterar o que estiver nela para:
  
    		PermitRootLogin yes
    
3. Comunicação SSH

  	a. Na placa, utilizar o comando:
    
    		ifconfig
  
  	b. Ele retornará o IP:
  
    		eth0      Link encap:Ethernet  HWaddr b8:27:eb:93:a9:a3  
          		inet addr:192.168.0.16  Bcast:192.168.0.255  Mask:255.255.255.0
          		UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          		RX packets:9416 errors:0 dropped:0 overruns:0 frame:0
          		TX packets:1375 errors:0 dropped:0 overruns:0 carrier:0
          		collisions:0 txqueuelen:1000 
          		RX bytes:9652095 (9.2 MiB)  TX bytes:121830 (118.9 KiB)

  	c. No computador, utilizar o seguinte comando:
  
    		ssh root@192.168.0.16

    d. Caso não funcione, tente reiniciar o serviço:
        
        	service networking restart
