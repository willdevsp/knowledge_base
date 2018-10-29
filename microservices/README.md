* [Microsserviços](#microsservicos)  
* [Vantagens e desvantagens](#vantagens-desvantagens)
* [Arquitetura](#arquitetura)

---

## Microsserviços

A arquitetura de microsserviços é uma aplicação como um conjunto de pequenos serviços, cada um executando em seu próprio processo. Os serviços podem ser construídos de forma modular, com base na capacidade de negócio da organização.

Pelo fato dos serviços serem construídos de forma independente, a implantação e a escalabilidade podem ser tratadas de acordo com a demanda. Essa independência também permite que os serviços sejam escritos em diferentes linguagens de programação e diferentes tecnologias, visando atender a necessidades específicas da melhor maneira. Outro ponto importante é que cada serviço pode ser gerenciado por diferentes times de desenvolvimento, possibilitando a formação de equipes especializadas.

---

## Vantagens e desvantagens

Dentre as vantagens, podemos citar:

· Fácil entendimento e desenvolvimento do projeto;
· Fácil e rápida implantação (build e deploy);
· Redução do tempo de startup, pois os microsserviços são menores que aplicações monolíticas em termos de código;
· Possibilidade de aplicar a melhor ferramenta para um determinado trabalho.

Dentre as desvantagens, podemos citar:

· Dificuldade em implantar e operar sistemas distribuídos;
· Como cada microsserviço geralmente tem sua própria base de dados, o gerenciamento de transação se torna mais difícil (múltiplas bases de dados);
· Implantar uma alteração em um serviço utilizado por muitos sistemas demanda coordenação e cautela.

---

## Arquitetura

Para a arquitetura de microsserviços estamos usando como base o [Spring Cloud Netflix](https://cloud.spring.io/spring-cloud-netflix/), que contém os seguintes projetos.

  * [Config Server](#servidordeconfiguracao)
  * [Eureka](#eureka)
  * [Zuul](#zuul)
  * [Microserviços](#microservices)


### Config Server

  Serviço que fornece as configurações para todos os microsserviços utilizando REST e mensageria.

  Para acessar o projeto basta clicar em [config-ms](https://gitlab.infracommerce.com.br/microservices/discovery/config-ms) ou [spring-cloud-config] (https://cloud.spring.io/spring-cloud-config/) para mais informações.

### Eureka

  Serviço que disponibiliza o status de todos os microsserviços registrados.

  Para acessar o projeto basta clicar em [eureka-ms](https://gitlab.infracommerce.com.br/microservices/discovery/eureka-ms) ou [spring-cloud-netflix-eureka] (https://www.baeldung.com/spring-cloud-netflix-eureka) para mais informações.


### Zuul

  Serviço de roteamento e load balancer da Netflix

  Para acessar o projeto basta clicar em [zuul-ms](https://gitlab.infracommerce.com.br/microservices/discovery/zuul-ms) ou [zuul-proxy] (https://www.baeldung.com/spring-rest-with-zuul-proxy) para mais informações.



Abaixo segue uma ilustração da arquitetura de microserviços com [Spring Cloud Netflix](https://cloud.spring.io/spring-cloud-netflix/).

![arquitetura-microsserviços](./readme-complement/arquitetura-microservices.png)

Quando um microserviço é iniciado ele vai buscar suas configurações através do [Config Server](#servidordeconfiguracao) e depois ele se registra no [Eureka](#eureka). Quando ocorre uma solicitação do serviço o [Zuul](#zuul) irá verificar através do [Eureka](#eureka) uma registro disponível e irá encaminhar a solicitação para o serviço responsável.
 