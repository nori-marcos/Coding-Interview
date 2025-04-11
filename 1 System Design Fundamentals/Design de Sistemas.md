[⬅ Home](../README.md) <br>
[⬅ Mapa Conceitual](../README.md#Mapa%20Conceitual)

> **Sumário**
>
> - [Design de Sistemas](#design-de-sistemas)
> - [0. Introdução sobre as 4 áreas de conhecimento sobre design de sistemas](#0-introdução-sobre-as-4-áreas-de-conhecimento-sobre-design-de-sistemas)
> - [1. Client-Server Model](#1-client-server-model)
> - [2. Network Protocols](#2-network-protocols)

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

## 3. Storage
