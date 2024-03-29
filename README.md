<h1>Fundamentos dos Microsserviços</h1>

> O conteúdo também foi organizado nos **commits**

<!--#region Sumário -->

<!--#region Fundamentos -->

<details><summary>Fundamentos</summary>

<ul>
    <li><a href="#ms-01">Apresentação</a></li>
    <li><a href="#ms-02">Agenda</a></li>
    <li><a href="#ms-03">Introdução</a></li>
    <li><a href="#ms-04">O que são microsserviços</a></li>
    <li><a href="#ms-05">Qual o tamanho ideal de um microsserviço</a></li>
    <li><a href="#ms-06">O que são serviços</a></li>
    <li><a href="#ms-07">Cultura</a></li>
    <li><a href="#ms-08">Monolíticos</a></li>
    <li><a href="#ms-09">Microsserviços e DDD</a></li>
    <li><a href="#ms-10">Microsserviços e Cultura</a></li>
    <li><a href="#ms-11">Armazenamento</a></li>
    <li><a href="#ms-12">Transações</a></li>
    <li><a href="#ms-13">Comunicação</a></li>
    <li><a href="#ms-14">Protocolos</a></li>
    <li><a href="#ms-15">APIs e Contratos</a></li>
    <li><a href="#ms-16">Distribuição</a></li>
    <li><a href="#ms-17">Circuit Breaker e Retry Pattern</a></li>
    <li><a href="#ms-18">Gateway</a></li>
    <li><a href="#ms-19">Segurança</a></li>
    <li><a href="#ms-20">Escala</a></li>
    <li><a href="#ms-21">Disponibilidade</a></li>
    <li><a href="#ms-22">Monitoramento - Parte 1</a></li>
    <li><a href="#ms-23">Monitoramento - Parte 2</a></li>
    <li><a href="#ms-24">Conclusão</a></li>
</ul>

</details>

<!--#endregion -->

<!--#endregion -->

<!--#region Fundamentos -->

<h2>Fundamentos</h2>

<!--#region Apresentação -->

<details id="ms-01"><summary>Apresentação</summary>

<br/>

Objetivos
- Não é sobre código
- Monolitos e Microsserviços
- Cultura
- Desafios
- Benefícios
- Drawbacks

</details>

<!--#endregion -->

<!--#region Agenda -->

<details id="ms-02"><summary>Agenda</summary>

<br/>

O que vamos debater...
- Monolíticos VS Microsserviços
- Organização e Cultura
- Armazenamento
- Serviços e Serviços Distribuídos
- Segurança
- Escala
- Disponibilidade
- Monitoramento
- Deploy

</details>

<!--#endregion -->

<!--#region Introdução -->

<details id="ms-03"><summary>Introdução</summary>

<br/>

Introdução:
- Se escreve microsserviços
- Arquitetura de microsserviços
- Microsserviço é um item de uma solução
- Não se trata apenas de código
- Não está limitado a tecnologia
    - "Microsserviços com ASP.NET Core" não existe
- Não tem exemplo de Microsserviços
- Implementação é diferente de design
- Estamos falando sobre sistemas realmente grandes
- Complexo e caro

</details>

<!--#endregion -->

<!--#region O que são microsserviços -->

<details id="ms-04"><summary>O que são microsserviços</summary>

<br/>

O que são?
- Determina um modelo de desenvolvimento
- Também é um conjunto de práticas
- Aumenta a velocidade do desenvolvimento
- Permite escalabilidade
- Agnóstico de tecnologias
- Princípios e padrões de arquitetura

</details>

<!--#endregion -->

<!--#region Qual tamanho ideal de um microsserviço -->

<details id="ms-05"><summary>Qual tamanho ideal de um microsserviço</summary>

<br/>

- Micro
    - Não dá para mensurar o tamanho
    - Não tem uma medida padrão
- Faz apenas uma coisa, e bem
- Micro se refere ao escopo e funcionalidades, não a quantidade de código
- Desenhado sob uma necessidade de negócio
- Que age totalmente independente
    - Incluindo o deploy
- Poder ser assimilado a um Bounded Context
- É o ato de divir um domínio em sub-domínios e finalmente em contextos delimitados

</details>

<!--#endregion -->

<!--#region O que são serviços -->

<details id="ms-06"><summary>O que são serviços</summary>

<br/>

- Um componente independente e "deployável" (publicável)
    - Baseado em um contexto delimitado
- Provê interoperabilidade
    - Através de comunicação via mensagens, requisição HTTP/S etc.
- SOA (Arquitetura Orientada a Serviços) Granularidade de serviços

> O servição não é necessariamente uma API

</details>

<!--#endregion -->

<!--#region Cultura -->

<details id="ms-07"><summary>Cultura</summary>

<br/>

**Impacto na cultura da empresa**
- Quanto maior o software, maior seu ciclo de vida
- Mais tempo o produto leva para ficar pronto
- Mais pessoas tem que trabalhar no time
- Mais complexo fica o projeto
- Mais difícil ficam as mudanças
- Mais engessado o projeto fica
    - Você pode experimentar tecnologias novas em projetos menores
    - Se não ficar bom, você perdeu pouco tempo

> Maior possibilidade de **NO GO**

</details>

<!--#endregion -->

<!--#region Monolíticos -->

<details id="ms-08"><summary>Monolíticos</summary>

<br/>

**Exemplo de eCommerce**
- Um usuário adiciona produtos a um carrinho
- O carrinho é salvo
- O usuário finaliza a compra
- É gerado um pedido
- É gerada a nota fiscal
- É feita a movimentação de estoque
- É realizada a entrega

![](./Assets/Images/ms001.png)

**Mesmo assim**
- Podemos escalar
    - Múltiplas instâncias
- Podemos expor APIs ou criar uma UI acoplada
- É um arquitetura amplamente usada
- Eficiente
- Mais por que mudar?

**Escaláveis**

![](./Assets/Images/ms002.png)

**Prós**

- Simples de desenvolver
    - Mesmo banco, tecnologia, time
- simples para *buildar*
- Simples para testar
- Simples para publicar (deploy)
- Simples de escalar

**Contras**

- Quanto maior mais difícil de ser produtivo
    - Novos membros demoram a se familizarizar
- Time fica grande
    - Precisa dividir os times
    - Ainda assim não conseguem agir independentes
- Código vira bagunça
- Engessa novas tecnologias
    - Visto que mudanças sempre causam dor
- Escala tudo ou nada
    - Black Friday
    - Quanto maior o App mais recurso usa, mais demora pra subir
- Banco de dados cresce junto

</details>

<!--#endregion -->

<!--#region Microsserviços e DDD -->

<details id="ms-09"><summary>Microsserviços e DDD</summary>

<br/>

**DDD e Microsserviços**

- Podemos correlacionar
- Domínio
    - Refere-se ao todo
- Sub-domínio
    - Uma parte do domínio
        - Usuário, pedido, produto, inventário
- Contexto delimitado
    - Capacidade de negócio
    - Um bom candidato a um microsserviço

Domínio: E-commerce

![](./Assets/Images/ms003.png)

**Dependências**

- Os microsserviços devem agir independentemente
- Porém, um pedido "pertence" a um usuário
- O DDD tem uma abordagem de replicação de entidade
- Com entidades separadas, podemos especializá-las
    - Usuário, no contexto
        - **User** tem foto, redes sociais etc.
        - **Order** só tem o e-mail

> Pode-se ter entidades com mesmo nome, em contextos diferentes, com significados diferentes

Focado em reutilização de código, sem duplicidade.

![](./Assets/Images/ms004.png)

</details>

<!--#endregion -->

<!--#region Microsserviços e Cultura -->

<details id="ms-10"><summary>Microsserviços e Cultura</summary>

<br/>

**Impacto na organização**

- Um time por sub-domínio
- Mais focado em uma coisa, mais especialista
- Tamanho do time varia de acordo com o tamanho do sub-domínio
- Responsável pelo ciclo de vida completo
    - Desenvolvimento ao **deploy**
- **Agile** e **DevOps** são fundamentais
- Não dispensa uma pessoa para cuidar de tudo
    - Orquestração dos times
- Cada time tem seu **wiki**, **codebase** etc.
- Versionamento é muito importante

> Não tem como entregar valor sem conhecer o negócio

</details>

<!--#endregion -->

<!--#region Armazenamento -->

<details id="ms-11"><summary>Armazenamento</summary>

<br/>

**Armazenamento**:

- Monolítico fica tudo em um banco, microsserviços não
- Armazenamento independente
- Cada um com suas necessidades
    - NoSQL, relacional, GraphQL etc.
- Mudar a fonte de dados não deve afetar outros serviços

**Transação e sincronização**:

Não é possível acessar dados de outros serviços. 
A não ser por APIs.

![](./Assets/Images/ms005.png)

**Microsserviços e dados**

**Desafios**:

- Sincronização
- Não tem transação distribuída
- Não tem persistência distribuída entre sub-domínios
- Não tem consistência imediata
- Precisa de consistência eventual
    - Um serviço publica um evento quando há uma mudança
    - Outros serviços consomem e atualizam os dados
- As mudanças de dados são sempre
- **Event Sourcing** é uma boa ideia neste cenário
- Em certo ponto do tempo, as informações podem estar diferentes entre sub-domínios
- Recomendações
    - Kafka, RabbitMQ

</details>

<!--#endregion -->

<!--#region Transações -->

<details id="ms-12"><summary>Transações</summary>

<br/>

### Transação e sincronização

> Barramento de eventos

![](./Assets/Images/ms006.png)

### Transação de longa duração

> SAGA

![](./Assets/Images/ms007.png)

![](./Assets/Images/ms008.png)

### Mensageria

**Caminho feliz**:
- GRP001 - Batch iniciado
    - EV001 - Usuário autenticou
    - EV002 - Usuário finalizou a compra
    - EV003 - Pedido realizado
    - EV004 - Pagamento realizado com sucesso
    - EV005 - Reveservando voo 1234
    - EV006 - Voo 1234 reservado com sucesso
    - EV007 - Reservando hotel XPTO
    - EV008 - Hotel XPTO reservado com sucesso
    - EV009 - Usuário notificado com sucesso
- GRP001 - Batch finalizado com sucesso

**Caminho triste**:
- GRP001 - Batch iniciado
    - EV001 - Usuário autenticou
    - EV002 - Usuário finalizou a compra
    - EV003 - Pedido realizado
    - EV004 - Pagamento realizado com sucesso
    - EV005 - Reservando voo 1234
    - EV006 - Voo 1234 reservado com sucesso
    - EV007 - Reservando hotel XPTO
    - EV008 - FALHA AO RESERVAR HOTEL
    - EV009 - Cancelamento voo 1234
    - EV010 - Estonando o pagamento
    - EV011 - Notificando o usuário
- GRP001 - Batch finalizado com sucesso

</details>

<!--#endregion -->

<!--#region Comunicação -->

<details id="ms-13"><summary>Comunicação</summary>

<br/>

- Devem expor uma API
    - Escolher um protocolo de comunicação
- RPC/gRPC
    - Request/Reply
    - Sync ou Async (Notificações)
- REST
- SOAP
- Messaging ou Events
    - Kafka, RabbitMQ

![](./Assets/Images/ms009.png)

</details>

<!--#endregion -->

<!--#region Protocolos -->

<details id="ms-14"><summary>Protocolos</summary>

<br/>

**Comunicação**:

- gRPC ou HTTP?
- Texto/Binário
- XML, JSON, YAML
    - Mais fácil de entender
    - Mais verboso/pesado
- Binário
    - Mais complexo
    - Mais leve

![](./Assets/Images/ms010.png)

</details>

<!--#endregion -->

<!--#region APIs e Contratos -->

<details id="ms-15"><summary>APIs e Contratos</summary>

<br/>

- Contrato define o que a API expoe
- Contratos definem o formato dos dados
    - SOAP/REST/gRPC => WSDL, Swagger,IDL
- Podemos ter APIs específicas para um tipo de dispositivo
    - Mobile, Desktop
- Versionamento é super importante

![](./Assets/Images/ms011.png)

</details>

<!--#endregion -->

<!--#region Distribuição -->

<details id="ms-16"><summary>Distribuição</summary>

<br/>

- A localização (IP ou DNS) pode mudar
- Utilizamos um **Service Registry** para saber onde está cada serviço
- Os serviços devem ser capaz de seu auto-registrar
- Primeiro descobrimos onde estão os serviços
- Depois o invocamos
- Cuidado com **CORS**
    - **Same-origin** => Protocolo (HTTP/S), servidor e porta
- Ferramentas
    - **Eureka**

</details>

<!--#endregion -->

<!--#region Circuit Breaker e Retry Pattern -->

<details id="ms-17"><summary>Circuit Breaker e Retry Pattern</summary>

<br/>

Circuit Breaker

- Reduzindo falhas
    - O serviço precisa estar disponível, senão...
        - Falha de rede
        - Serviço sobrecarregado
    - Pode causar erro em outros serviços
        - Efeito dominó
    - Circuit Breaker ajuda nisso
        - Invoca um serviço por um proxy e desvia a chamada caso precise
        - Retorna ao normal assim que o serviço volta
    - Ferramentas
        - IHttpClienteFactory/Polly

![](./Assets/Images/ms012.png)        

</details>

<!--#endregion -->

<!--#region Gateway -->

<details id="ms-18"><summary>Gateway</summary>

<br/>

**Um único ponto de acesso**

- Agrega todos os microsserviços
    - Concentra itens de **cross-cutting** (autenticação, **service registry**, **API translation**)
- Prove uma interface unificada

- Ferramentas
    - **Azure API Management**

![](./Assets/Images/ms013.png)

</details>

<!--#endregion -->

<!--#region Segurança -->

<details id="ms-19"><summary>Segurança</summary>

<br/>

Não é específico dos microsserviços, mas ...

- Autenticação
    - Diz quem você é
- Autorização
    - Diz o que você pode fazer
- IAM
    - Identity and Access Management
    - SSO
- Concentra a autenticação e autorização
- OAuth/ Open ID

- Ferramentas
    - Identity Server, Keycloak

![](./Assets/Images/ms014.png)

Não é específico dos microsserviços, mas ...

- AccessToken ou Cookies
    - JWT
- São passados de um serviço para outro
- Retém as informações do usuário
- É validado no IAM a cada requisição

</details>

<!--#endregion -->

<!--#region Escala -->

<details id="ms-20"><summary>Escala</summary>

<br/>

Demanda aumenta ...

- Escala vertical
- Escala horizontal
- Cada um funciona de um jeito, para um caso e um serviço
- Load Balancer
- Service Register

</details>

<!--#endregion -->

<!--#region Disponibilidade -->

<details id="ms-21"><summary>Disponibilidade</summary>

<br/>

Demanda aumenta ...

- Downtime Per Year
- SPOF
    - Se falhar para tudo
    - Por exemplo, o Gateway, IAM, Mensageria
    - Um forte candidato a escala horizontal

</details>

<!--#endregion -->

<!--#region Monitoramento - Parte 1 -->

<details id="ms-22"><summary>Monitoramento - Parte 1</summary>

<br/>

Muitas coisas para monitorar ...

- Dashboard
- Centralizado
    - Não dá para conectar em cada máquina e ver o log
- Ferramentas
    - Kibana, Grafana
- Health Check
    - Endpoint que retorna a saúde do serviço
    - É pingado de tempos em tempos para ver como andam as coisas
- Log
    - Mantenham no mesmo formato
    - Centralize tudo
- Ferramentas
    - Splunk
- Exceptions
    - Mantenha separadas dos logs
    - Centralizado

</details>

<!--#endregion -->

<!--#region Monitoramento - Parte 2 -->

<details id="ms-23"><summary>Monitoramento - Parte 2</summary>

<br/>

Muitas coisas para monitorar ...

- Métricas
    - Issues de performance
    - Qual endpoint está lento?
    - O que pode dar ruim?

> Se não é medido, não é possível gerenciar

- Ferramentas
    - Application Insights, Prometheus

- Rate Limit
- Criação de produtos
- Defende contra DDoS
- Limita o tráfico
- Limita o uso por cliente
- Limita o uso por tempo
- Monetiza
- Ferramentas
    - Azure API Management
- Alertas
- Ferramentas
    - Azure Alerts

</details>

<!--#endregion -->

<!--#region Conclusão -->

<details id="ms-24"><summary>Conclusão</summary>

<br/>

</details>

<!--#endregion -->

<!--#endregion -->
