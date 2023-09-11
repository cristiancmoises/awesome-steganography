# Esteganografia incrível
<p align="center">
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/15b81a67-2409-45ff-82a3-b5c825b81079" width=20% height=20% class="center"/>
<p/>
  
## Ferramentas incríveis para esteganografia 🕵️

# Índice

* [`Introdução`](#Esteganografia?)
* [`Oculto com GUI`](#Stegoshare)
* [`Oculto com TCP`](#Steganoroute)
* [`Tamanho de arquivo baixo`](#Snow)
* [`Ferramenta Popular`](#Steghide)
  
## Esteganografia?
> A esteganografia é a arte e a ciência de escrever mensagens ocultas de tal forma que ninguém, exceto o remetente e o destinatário pretendido, perceba que há uma mensagem oculta. Por outro lado, a criptografia obscurece o significado de uma mensagem, mas não oculta o fato de que há uma mensagem. Hoje, o termo esteganografia inclui a ocultação de informações digitais em arquivos de computador. Por exemplo, o remetente pode começar com um arquivo de imagem de aparência comum e, em seguida, ajustar a cor de cada 100 pixels para corresponder a uma letra do alfabeto – uma mudança tão sutil que é improvável que alguém que não esteja procurando ativamente por ela perceba isto.
Quanto maior for a mensagem de cobertura (em termos de conteúdo de dados – número de bits) em relação à mensagem oculta, mais fácil será ocultar a carta.
Dito de forma um pouco mais formal, o objetivo de dificultar a detecção da codificação esteganográfica é garantir que as alterações na portadora (o sinal original) devido à injeção da carga útil (o sinal a ser incorporado secretamente) sejam visualmente (e idealmente, estatisticamente) insignificante; isto é, as alterações são indistinguíveis do nível de ruído da portadora.
Por esta razão, imagens digitais (que contêm grandes quantidades de dados) são utilizadas para ocultar mensagens na Internet e em outros meios de comunicação. Por exemplo: um bitmap de 24 bits terá 8 bits representando cada um dos três valores de cores (vermelho, verde e azul) em cada pixel. Se considerarmos apenas o azul, haverá 28 valores diferentes de azul. A diferença entre 11111111 e 11111110 no valor da intensidade do azul provavelmente será indetectável pelo olho humano. Portanto, o bit menos significativo pode ser usado (de forma mais ou menos indetectável) para outra coisa que não seja informação de cor. Se fizermos isso também com o verde e o vermelho, poderemos obter uma letra de texto ASCII para cada três pixels.



# Stegoshare:
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/1734d34c-541d-4696-8f05-4fb8fc88690e" width=45% height="45%">

O programa usa 3 bits menos significativos (LSB) para os canais vermelho e azul e 2 LSB para o canal verde. Usando compactação sem perdas (PNG), o StegoShare fornece cerca de 40% da capacidade (nas imagens de 250Mb você pode ocultar o arquivo de 100Mb). Visualmente as imagens parecem que não há arquivos incorporados, o olho humano não consegue detectar a diferença. A criptografia de 128 bits torna mais difícil a detecção de arquivos ocultos.

| Recursos                                                                     |
|------------------------------------------------------------------------------|
| Simples e fácil de usar                                                      |
| Funciona em qualquer plataforma que execute Java                             |


> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Em execução:

     apt install wget openjdk-8-jdk openjdk-8-jre
     wget http://downloads.sourceforge.net/stegoshare/StegoShare.jar
     java -jar StegoShare.jar

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> No Gentoo:

     emerge openjdk
     emerge jre
     wget http://downloads.sourceforge.net/stegoshare/StegoShare.jar
     java -jar StegoShare.jar

# Esteganorouter:
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/6438b4f4-0c4b-4c65-99cb-f5e588617fb9" width=45% height="45%">

É uma ferramenta para enviar mensagens de texto esteganografadas para outro computador pela rede. 
O receptor deve traçar uma rota até o remetente usando o programa mtr (e pressionando d uma vez para mudar o modo de exibição para o gráfico contínuo). 
Essa ferramenta, o remetente, cria vários saltos falsos e faz com que eles respondam (ou não) aos pacotes ICMP para escrever as letras uma por uma na tela do cliente mtr.

| Recursos                                                                                                         |
|------------------------------------------------------------------------------------------------------------------|
| Pode imprimir letras maiúsculas e minúsculas.                                                                    |
| Pode imprimir no modo normal ou inverso de cores.                                                                |
| Pode ficar em loop para sempre.                                                                                  |
| Deve funcionar no seu próprio computador localhost, na sua LAN e na Internet.                                    |
| Ele usa a fonte Sinclair ZX Spectrum (1982).                                                                     |
| Você pode selecionar o valor TTL sob demanda e, portanto, 'mover' o texto para cima e para baixo no gráfico mtr. |

#### Aviso! _Você pode filtrar o endereço IP que deve receber o traceroute. Se você não filtrá-lo, cada traceroute que sai do servidor adicionará misteriosamente saltos falsos a qualquer destino! Você pode sentir a sensação de ser alvo pelas principais organizações de inteligência do mundo usando o modo paranoico :D !_

> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Em execução:
     
     apt install git mtr python3 python-scapy
     git clone https://github.com/stratosphereips/steganoroute.git
     cd./steganoroute
     iptables -I INPUT -p icmp --icmp-type 8 -j DROP
     python3 ./steganoroute.py -i lo -m "MATRIX tem você!" -eu
     mtr -t seuipnaLAN
_*Comando MTR usado para listar a mensagem_

> <img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> No Gentoo:

     emerge mtr
     emerge python
     emerge scapy
     git clone https://github.com/stratosphereips/steganoroute.git
     cd./steganoroute
     iptables -I INPUT -p icmp --icmp-type 8 -j DROP
     python3 ./steganoroute.py -i lo -m "MATRIX tem você!" -eu
     mtr -t seuipnaLAN
_*Comando MTR usado para listar a mensagem_

# Snow:
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/27980d7d-37cb-47ee-a686-64e246f8fc8d" width=50% height=50% >

Uma ferramenta leve que usa espaços em branco e tabulações para ocultar informações dentro de arquivos de texto. Ao contrário de outras ferramentas esteganográficas, o snow não depende de formatos binários para codificar dados secretos. Isso pode ser extremamente útil nos casos em que não é possível compartilhar arquivos binários grandes.

| Recursos                                                                      |
|-------------------------------------------------------------------------------|
| Produz pequenos arquivos                                                      |
| O texto de saída pode ser usado em qualquer programa que aceite texto simples |

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Em execução:
     
     apt instalar o Stegsnow
     stegsnow -C -m "Mensagem criptografada aqui" -p "senhabraba" infile outfile
     stegsnow -C -p "angrypassword" outfile
    
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> No Gentoo:

     wget https://darkside.com.au/snow/snow.zip
     unzip neve.zip
     cd snow
     make
     cp snow /bin/
     snow -C -m "Mensagem criptografada aqui" -p "senhabraba" infile outfile
     snow -C -p "senhabraba" outfile

# Steghide

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/43aa8701-9aa3-4fbf-ab64-44e1757d81aa" largura=45% altura=45%>

Uma das ferramentas esteganográficas mais populares da atualidade. 
É um programa simples de linha de comando que codifica texto dentro de imagens. 
Steghide funciona criando uma lista aleatória de bits dentro de seu arquivo fictício e insere seus dados secretos entre esses bits.

| Recursos                                                        |
|-----------------------------------------------------------------|
| Rápido e fácil de usar                                          |
| Usa somas de verificação para verificar a integridade dos dados |

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/565f2738-dc37-4989-8e2c-685a857d8798" width=2% height=2%> Em execução:

     apt install steghide
     steghide embed -ef arquivosecreto.txt -cf foto.jpg -sf fotoX.jpg
     steghide extract –sf photoX.jpg

<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/069d520a-d797-4151-85a7-88280d0c5e33" width=2% height=2%> No Gentoo:

     ./configure
     make
     make check
     make install
     steghide embed -ef arquivosecreto.txt -cf foto.jpg -sf fotoX.jpg
     steghide extract –sf photoX.jpg
     
<p align="center">
<img src="https://github.com/cristiancmoises/awesome-steganography/assets/86272521/403986bb-44f1-4771-bfaf-12667d6872e3" width=160% height=100% >


