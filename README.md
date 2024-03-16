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

<!--#endregion -->
