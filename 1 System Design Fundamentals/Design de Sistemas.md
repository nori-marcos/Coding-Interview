[⬅ Home](../README.md) <br>
[⬅ Mapa Conceitual](../README.md#Mapa%20Conceitual)

> **Sumário**
>
> - [Design de Sistemas](#design-de-sistemas)
> - [0. Introdução sobre as 4 áreas de conhecimento sobre design de sistemas](#0-introdução-sobre-as-4-áreas-de-conhecimento-sobre-design-de-sistemas)
> - [1. Client-Server Model](#1-client-server-model)
> - [2. Network Protocols](#2-network-protocols)
> - [3. Storage](#3-storage)
> - [4. Latency and Throughput](#4-latency-and-throughput)

# Design de Sistemas

## 0. Introdução sobre as 4 áreas de conhecimento sobre design de sistemas

Existe uma série de informações a respeito do design de sistemas,mas podemos dividir o conhecimento sobre o assunto em 4 categorias principais:

- **Conhecimento Base**: Conhecimento básico dos elementos de um sistema como servidores, bancos de dados, redes, etc.
- **Características Chaves**: Características que geram um trade-off entre os elementos do sistema, como escalabilidade, disponibilidade, resiliência, throughput, latência, confiabilidade, redundância, etc.
- **Componentes**: Componentes mais tangíveis do sistema, como por exemplo:
  - Load Balancer (Como opera a distribuição de carga entre instâncias de um sistema.)
  - Cache (Quais dados são armazenados em memória para acelerar leituras.)
  - Leader Election (Como um sistema decide qual instância é o líder.)
  - Rate Limiting (Como um sistema limita a quantidade de requisições que um cliente pode fazer.)
  - Proxy (Como um sistema atua como intermediário entre o cliente e o servidor. Como as requisições são roteadas.)
  - etc.
- **Tecnologias**: Tecnologias específicas que podem ser utilizadas para implementar os componentes do sistema, como zookeeper, redis, google cloud, aws, etc.

## 1. Client-Server Model

É um dos modelos mais comuns de arquitetura de sistemas. Aqui é importante entender, por exemplo, o que acontece quando coloco no navegador o endereço de um site. Aqui é necessário definir dois conceitos importantes:

- **Client**: O cliente é a máquina que "conversa" com um servidor. "Conversar" com o servidor significa enviar ou requisitar dados do servidor.
- **Server**: O servidor é a máquina que "escuta" as requisições de um cliente e "responde" a elas. "Escutar" significa que o servidor está sempre esperando por requisições de clientes. "Responder" significa que o servidor envia dados de volta para o cliente.

No caso de acessar um site, o cliente é o navegador e o servidor é a máquina que hospeda o site. Ainda sobre este exemplo, algumas etapas são importantes:

1. O cliente (navegador), na camada da aplicação da arquitetura de redes, faz uma requisição DNS (Domain Name System) para descobrir o endereço IP (Internet Protocol) do servidor.
   - O DNS é um sistema de catálogo de endereços IP. E o IP é o identificador único de uma máquina na rede.
   - O IP do site é o endereço que o navegador precisa para se conectar ao servidor que hospeda o site. No caso da cloud, se o site está hospedado na AWS, o IP é o endereço do servidor EC2 (Elastic Compute Cloud) que hospeda o site.
2. Após descobrir o endereço IP, o cliente, na camada da aplicação da arquitetura de redes, faz uma requisição HTTP para o servidor.

## 2. Network Protocols
O protocolo é um conjunto de regras que define a interação entre duas partes. No caso de network protocols, as regras são para interação entre duas máquinas:
- Qual o tipo de mensagem?
- Qual o formato da mensagem?
- Qual a ordem das mensagens?
- Uma máquina pode enviar uma mensagem a outra sem esperar por uma resposta?

Os tipos mais comuns de protocolos são:
- **IP**: Internet Protocol. É o protocolo mais básico da internet e define como os dados são enviados entre máquinas na rede de internet. Neste tipo de protocolo, os dados são enviados em pacotes, chamados em inglês de IP packets.Esses pacotes são compostos por bytes e tem duas partes principais:
  - Header: Contém informações sobre o pacote, como o endereço IP de origem e destino, o número do pacote, o tamanho do pacote, a versão do protocolo (IPV4 ou IPV6), etc. O header é bem pequeno e geralmente tem entre 20 e 60 bytes.
  - Data: Tem o tamanha do 2^16 bytes (2^6 * 2^10, respectivamente 64KB).


## 3. Storage

## 4. Latency and Throughput
Latency e Throughput são os conceitos mais importantes quando falamos da performance de um sistema.

**Latency**: Latência é o tempo que leva para um dado chegar de um ponto até outro dentro de um sistema. A latência pode ser avaliada em alguns contextos:
- Network Request Latency: Quanto tempo leva para uma requisição ir do cliente até o servidor e volt
com a resposta.
- Memory Latency: Quanto tempo leva para um sistema acessar um dado na memória.

A latência é medida em milissegundos (ms) ou microssegundos (µs).
- 1ms = 1000µs
- 1s = 1000ms = 1000000µs

Algumas latências comuns são:
- memória: 1MB de dados em 250µs (0.25ms)
- SSD: 1MB de dados em 1000µs (1ms)
- rede: 1MB de dados em uma banda de 1GBps leva 10000µs (sem considerar distância) (10ms)
- HDD: 1MB de dados em 20000µs (20ms)

**Throughput**: Throughput é a quantidade de requisições que o servidor consegue atender por unidade de tempo. Geralmente o throughput é medido por requisições por segundo (RPS) ou requisições por milissegundo (RPM).

Os dois aspectos são importantes para a performance de um sistema, mas não estão necessariamente correlacionados. Não é possível inferir a latência de um sistema apenas pelo throughput ou vice-versa. Por exemplo, um sistema pode ter uma parte com uma latência baixa, ou seja, consegue responder rapidamente as requisições, mas se outra parte tem um throughput baixo, o sistema pode não conseguir atender todas as requisições. Isso leva a um cancelamento de requisições, o que pode gerar uma latência maior do sistema.

