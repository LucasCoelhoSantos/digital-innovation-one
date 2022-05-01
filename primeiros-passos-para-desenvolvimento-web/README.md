# Primeiros passos para desenvolvimento web (professor Bruno Prado)

## O que é Internet

Criada em 1969 pelo departamento de defesa dos Estados Unidos, era chamada de Arpanet e tinha o intuito de interligar laboratórios (computadores).

> Em 1988 chegou nas universidades brasileiras.

## O que são redes

Uma rede consiste em dois ou mais computadores que estão conectados para compartilhar informações.

- Backbone (espinha dorsal): gerenciam o trafego da Internet, interligando em outros backbone.
- Provedor de acesso (empresas telefônicas): contratam o sinal do backbone e o repassam ao usuário final.
- Provedor de serviço: Dial-up, ADSL, fibra ótica, rádio, satélite, móvel, P2P (peer to peer).
- Caminho inverso: o DNS (Domain Name System) transforma o URL (www.google.com) em IP.

> IP localhost: 127.0.0.1

## TCP/IP e UDP

### TCP/IP - Protocolos de comunicação entre computadores

> Transmission Control Protocol: Protocolo de Controle de Transmissão.
>
> Internet Protocol: Protocolo de Internet.

Utiliza o modelo de camadas:

1. Física (ex.: placa de rede)
2. Rede (ex.: IP)
3. Transporte (ex.: TCP, UDP)
    - TCP: é voltado a conexão, handshake, integridade, ordem dos dados (ex.: aplicativo de mensagem de texto).
    - UDP: fornece conexão rápida, não confiável, isto é, não tem confirmação de envio e recebimento (ex.: livestream).
4. Aplicação (ex.: FTP, SMTP, HTTP)

## Portas

São portas (portos) por onde dados sairão e chegarão.

- 20: FTP
- 22: SSH (conexão segura entre dois computadores para executar comandos)
- 25: SMTP (envio de emails)
- 53: DNS
- 80: HTTP (requisição simples da internet)
- 443: HTTPS (requisição segura da internet)

## Roteadores, switches e modems

### Modem (**Mod**ulator-**dem**odulator)

- Hardware que converte dados de um formato que possa ser transmitido de um computador para outro e lidopor outro.

### Roteador

- Distribui internet para um ou mais dispositivos de uma rede.
- Pode fazer a comuinicação entre redes.
- Pode ser "burro" (distribui para todos que estão conectados ao roteador).

### Switch

- Distribui internet para um ou mais dispositivos de uma rede.
- Criado para ser "inteligente" (distribui só para quem fez a requisição).

## Dados móveis

**SMS** não tem custo para uma operadora de telefonia, pois o celular naturalmente já troca alguns bits com as torres de comunicação.

**MMS:** transmissão de mensagens multimídia (áudio, video) por meio de uma espécie de conexão de dados primitiva.

|Conexão         |Velocidade  |
|:--------------:|:----------:|
|1G (analógico)  |10 Kbps     |
|2G (digital GSM)|97 Kbps     |
|GPRS "2.5G"     |32-80 Kbps  |
|EGDE "2.75G"    |128-236 Kbps|
|3G              |7 Mbps      |
|4G              |22,1 Mbps   |
|5G              |10 Gbps     |

## Wi-Fi

IEEE - Institute of Electrical and Electronic Engineers (Instituto de Engenheiros Eletricistas e Eletrônicos)

|Padrão |Velocidade                |
|:-----:|:------------------------:|
|802.11 |2,4 GHz, 2 Mbps           |
|802.11a|5 GHz, 54 Mbps            |
|802.11b|2,4 GHz, 11 Mbps          |
|802.11g|2,4 GHz, 54 Mbps          |
|802.11n|2,4 GHz/5GHz, 150-600 Mbps|

### Segurança

- WEP: chave (senha) de 64 bits e 128 bits
- WPA: chave com mesmo tamanho do WEP, mas é trocada periodicamente.
- WPA2: traz mais segurança com uma camada de AES, e trabalha com o padrão 802.11i, porém requer mais processamento.

## Bluetooth

Conexão ponto-a-ponto sem depender da internet.

|Classe |Potência Máxima|Alcance|
|:-----:|:-------------:|:-----:|
|1      |100mW          |100m   |
|2      |2,5mW          |10m    |
|3      |1mW            |1m     |

|Versão |Taxa de transmissão|
|:-----:|:-----------------:|
|1.2    |1 Mbps             |
|2.0+EDR|3 Mbps             |
|3.0    |24 Mbps            |
|4.0    |25 Mbps            |
|5.0    |50 Mbps            |

## Browser

Programa que interpreta as linguagens de programação e as transformam em algo compreensivél para um humano.

- Sabe identificar várias linguagens de programação, linguagens de marcação e conteúdo multimedia.
- Possuem plug-ins que ajudam na navegação.
- Armazenam cache (armazena recursos da ágina da web no lado do cliente diminuindo o tempo de carregamento) e cookies (amazena a sessão de navegadores para rastrear as preferências do usuário).

### Página estática vs página dinâmica

Os sites estáticos usam apenas código HTML e CSS do lado do cliente (contendo um número fixo de páginas), enquanto os sites dinâmicos dependem tanto de linguagens de script do lado do cliente quanto do lado do servidor, como JavaScript, PHP ou ASP (permitindo que os usuários interajam com as informações listadas na página).

> Pesquisar como eram os sites antigamente: [Wayback Machine](https://web.archive.org/)

## Site, aplicativo, e-commerce

### Site

É uma página da Internet que possui diversos propósitos (entretenimento, colaborativa, pesquisa, etc) e podem ser feitas em diversas linguagens de programação.

### Aplicativo

> Aplicativo é um software que é executado no navegador.

Um aplicativo de celular muitas vezes nada mais é que uma espécie de navegador.

### E-commerce (Comércio eletrônico)

Site de compra e venda com sistema de pagamento, podendo ser exterior ao site, como: boleto, PagSeguro, etc.

## Web-server

### Web-server Estático

Servidor físico onde são armazenados arquivos, softwares e/ou banco de dados.

![Web-server físico](https://images.unsplash.com/photo-1506399309177-3b43e99fead2?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1468&q=80)

### Web-server Dinâmico

Softwares que estão presentes no servidor físico.

- Arquivos (file server)
- Aplicações (application server)
- Banco de dados (database)
- Todo junto e misturado

Um site, ou aplicativo precisa estar hospedado em um servidor para poder ser acessado, junto com seu banco de dados.

### Web-service

Interface disponível para fazer requisições e consultas em banco de dados inacessíveis (correios, governo).

## Stacks

### O que é

São pilhas de tecnologia, ou seja, um conjunto de softwares necessários e suficientes para executar um aplicativo/programa. Dentre eles:

- Sistemas, linguagens de programação, banco de dados, protocolos de comunicação;
- Ambientes e ferramentas de interação com o app/wb
- Capacidade e limitação de performance;
- Pontos fortes e fracos do app/wb.

Importante para:

- Os líderes de projeto terem informações das equipes de desenvolvimento;
- Os desenvolvedores saberem das limitações e capacidades das ferramentas e ambientes que têm disponíveis.
- As estratégias de negócios da empresa, contratações, plano de mitigação de riscos, aumento da capacidade, uso dos dados.

## Definição de front-end, back-end e fullstack

### Front-end

> "Parte da frente" do site, software, aplicativo, web service.

Interface (UI, UX), usam lógica de programação, HTML, CSS, jQuery/JS/AJAX, PHP, Bootstrap/outros framework.

### Back-end

> "Parte de trás" do site, software, aplicativo, web service.

Entre interface e banco de dados, regra de negócios, validações. Usam: MySQL, Oracle, protocolos de comuiniação, PHP, Java, node.js.

### Fullstack

Profissional que sabe trabalhar em todas as camadas das tecnologias de desenvolvimento/execução de um app/ws.

![Exemplo Stack Tecnológico](https://lh5.googleusercontent.com/0HmpKL6aAx-8txsW9qszajMEG27Z9Xb_wMlwJCLPkcvdLnflEssiok2USh7DCk11ENL_tl18Qw19svHZ4O0PO42EuKF4b9xQOXYgyjlz2AbmkX8_ARhuXqChTouk1wO8A5w1PPHG)

![Exemplo Stack Tecnológico](https://blog.alluxi.com/content/images/2020/10/1_H53H7hTwiUyr9M3IqeENcQ.png)

![Frameworks populares para front-end](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.qc1cY2xl_KFww1xxYwMGjQHaEo%26pid%3DApi&f=1)

## Construindo primeira aplicação

[XAMP (Apache + MariaDB + PHP + Perl)](https://www.apachefriends.org/index.html)

> Instalar XAMP na pasta (C:)

Configurar Apache:

- Config > Apache(httpd.conf)
- Procurar DocumentRoot
- Trocar o DocumentRoot e o Directory para "C:/projetos"

### Links

- [jQuery](code.jquery.com)
- [jQuery User Interface](jqueryu.com/accordion)
- [W3Schools Online Web Tutorials](w3schools.com)

> Construa um site utilizando alguma biblioteca visual jQuery (como Accordion).
