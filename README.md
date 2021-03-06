# Nimus: Aplicativo para facilitação do agendamento de consultas

## **Fatec Jessen Vidal - São José Dos Campos/SP**

## **Jéssica Isri Dias Cruz**

### **1. Introdução**

Um plano de saúde é um seguro de proteção de pessoas contra o risco de terem de vir a arcar com despesas médicas. 
Planos de saúde suplementar surgiram no Brasil há pouco mais de 60 anos e atualmente servem a cerca de 47,3 milhões de pessoas (22,7% da população brasileira), segundo dados da Agência Nacional de Saúde Suplementar (ANS).

Atualmente em todo o país existem cerca de 754 operadoras em funcionamento, oferecendo tipos diversos de planos (familiares, individuais e empresariais), com as principais modalidades sendo: Autogestão cooperativa médica, filantropia, medicina de grupo e seguradora de saúde. 
Contudo mais de 1,2 bilhões de consultas, exames e internações por ano.

Com o intuito de auxiliar os usuários de planos de saúde suplementar a as clínicas e profissionais que servem aos planos supracitados a realizarem o agendamento e gerenciamento de consultas, alguns softwares foram desenvolvidos, tais como  o *MediLab*, que visa a facilitação e encurtamento da burocracia envolvida no momento de se marcar uma consulta médica.

## 

### **2. Fundamentação Teórica**

### **2.1. Sistemas Mobile**

De acordo com a IBM, a tecnologia móvel é aquela capaz de acompanhar o usuário independente do local onde o mesmo se encontra. Ela é constituída por dispositivos portáteis de comunicação bidirecional, dispositivos de computação e a tecnologia de rede que as conectam.
A tecnologia móvel é caracterizada por dispositivos habilitados para o uso conjunto com a internet, como por exemplo: smartphones, tablets e relógios. [IBM - Mobile Technology](https://www.ibm.com/topics/mobile-technology).

A tecnologia móvel atualmente se encontra em rápida acensão, sendo que o número de usuários já ultrapassa os 3 bilhões.

##

### **2.2. Flutter**

O Flutter é um kit de desenvolvimento de interface de usuário de código aberto desenvolvido pelo Google, que possui como vantagem apresentar um codigo unico para diversas plataformas (Android, IOS, Windowns, Linux e Web), tendo o Dart como principal linguagem de desenvolvimento.

O Flutter possui uma porção de widgets que permite criar o layout dos aplicativos com uma maior facilidade em comparação com linguagem nativas, tendo sido projetado como um sistema extensível em camadas. Ele existe como uma série de bibliotecas independentes em que cada uma depende da camada subjacente. [Flutter - Architectural Overview](https://flutter.dev/docs/resources/architectural-overview)

![Architectural diagram](https://flutter.dev/images/arch-overview/archdiagram.png) 
    > _Figura 1. Arquitetura do funcionamento do Flutter_

Geralmente os desenvolvedores integram com o Flutter por meio da estrutura Flutter, que fornece uma estrutura reativa moderna escrita na lingragem Dart. Incluindo um rico conjunto de plataformas, layout e bibliotecas básicas, composta de uma série de camadas trabalhando de baixo para cima, teremos:

 - Foundation: Classes básicas de serviços de bloco de construção, como animações, pintura e gestos que oferecem abstrações comumente usadas sobre a base subjacente.
 - Rendering Layer: Fornece um conjunto de abstrações para se trabalhar com layout, podendo construir uma árvoe de objetos renderizáveis, podendo ser manipulados dinamicamente.
 - Widget Layer: É uma abstração de composição, onde cada objeto de renderização tem uma classe correspondente na camada de widgets.
 - Material e Cupertino: São bibliotecas que oferecem conjuntos de controles que usam os primitivos de composição da camada de widget para implementar o Material ou linguagens de design do iOS.

### **2.3. CloudSQL**
O CloudSql é um serviço de banco de dados relacional totalmente gerenciado com suporte ao MySQL, PostgreSQL e SQL Server, tendo como vantagens a redução de custo de manutenção com banco de dados relacionais gerenciados na nuvem, confiabilidade, observabilidade do database, integração facilitada com os serviços do Google Cloud. [Google Cloud:](https://cloud.google.com/sql).

### **2.4. App Engine**
De acordo com Rick Kazman, Philip Bianco, James Ivers e John Klein quando pensamos em arquitetura e natual pensarmos em equipamentos físicos e palpaveis quando pensamos em um ambiente de execução de software, porém assim como um carro o hardware se desgasta gerando maiores gastos com manutenção, diferente de um software que não sofre desgaste e/ou alterações.[Kazman, Rick; Bianco, Philip; Ivers, James; & Klein, John. Maintainability. CMU/SEI-2020-TR-006. Software Engineering Institute, Carnegie Mellon University. 2020. http://resources.sei.cmu.edu/library/asset-view.cfm?AssetID=650480]


 O App Engine é um serviço que tem como principal objetivo permitir a publicação de aplicativos com o minimo de configuração possível [TreinaWeb:](https://www.treinaweb.com.br/blog/o-que-e-o-app-engine-e-como-publicar-uma-aplicacao-nele), sendo assim se categorizando como um serviço do nivel **PaaS**(Plataforma como serviço). Dessa maneira sendo responsavél por:
 
 - Manter o ambiente onde a aplicação será executada;
 - Fornecer a segurança do ambiente;
 - Manter o sistema operacional;
 - Alocação do hardware necessário;
 
Esse tipo de serviço é ideal para aplicações que trabalham com o modelo de microservices, disponibilizando dois tipos de ambientes.
**Ambiente Padrão**
As instâncias do aplicativo são executadas em um [sandbox](https://en.wikipedia.org/wiki/Sandbox_(computer_security)) (em inglês), usando o ambiente de execução de uma das linguagens compatíveis, que estão listadas abaixo.
Aplicativos que precisam lidar com escalonamento rápido.
O ambiente padrão é ideal para aplicativos com as seguintes características:
 -   O código-fonte é escrito em  **versões específicas das linguagens de programação compatíveis**:
    -   Python 2.7, Python 3.7, Python 3.8 e Python 3.9
    -   Java 8 e Java 11
    -   Node.js 8, Node.js 10, Node.js 12 e Node.js 14
    -   PHP 5.5, PHP 7.2, PHP 7.3 e PHP 7.4
    -   Ruby 2.5, Ruby 2.6 e Ruby 2.7
    -   Go 1.11, Go 1.12, Go 1.13, Go 1.14 e Go 1.15
-   Destina-se a ser  **executado gratuitamente ou a um custo muito baixo**, em que você paga apenas pelo que precisa e quando precisa. Por exemplo, o aplicativo pode ser escalonado para 0 instâncias quando não há tráfego.
-   Passa por  **picos súbitos e extremos de tráfego**  que exigem escalonamento imediato.

**Ambiente Flexível**
As instâncias do aplicativo são executadas em contêineres do Docker em máquinas virtuais (VM, na sigla em inglês) do Compute Engine.

Aplicativos que recebem tráfego consistente, passam por flutuações de tráfego regulares ou atendem aos parâmetros para aumentar e diminuir gradualmente a escala.

O ambiente flexível é ideal para aplicativos com as seguintes características:

-   Código-fonte escrito em uma versão de qualquer uma das linguagens de programação compatíveis:  
    **Python**,  **Java**,  **Node.js**,  **Go**,  **Ruby**,  **PHP**  ou  **.NET**
-   Executado em um contêiner do Docker que inclui um ambiente de execução personalizado ou código-fonte escrito em  **outras linguagens de programação**.
-   Usa ou depende de frameworks que incluem  **código nativo**.
-   Acessa os recursos ou serviços do projeto do Google Cloud que estejam na  **rede do Compute Engine**.

**Fonte:** https://cloud.google.com/appengine/docs/the-appengine-environments

##
### **3. Metodologia e Métodos**
### **3.1 Login do Paciente**
![image](https://user-images.githubusercontent.com/65822756/120411696-9a9e2e80-c32b-11eb-90c1-07aba14953c0.png)
### **3.2 Pré Agendamento de uma consulta**
![image](https://user-images.githubusercontent.com/65822756/120412966-dd610600-c32d-11eb-90a4-b1bda26baadd.png)
### **3.3 Confirmação do agendamento**
![Diagrama em branco - Página 3](https://user-images.githubusercontent.com/65822756/120414741-d38cd200-c330-11eb-9834-bd66b3546ef5.png)

##
### **4. Interface do protótipo**
##
### **4.1 Protótipo funcional**
Essa seção destina se a demonstração de uma visão inicial do layout da aplicação em sua versão mobile. É possivel acessar o prototipo funcional a partir do link:
https://www.figma.com/proto/yXqbY2dx9npPW6SVrBLnXq/Nimus?page-id=1:2&node-id=203:98&viewport=404,475,0.2098381668329239&scaling=scale-down
### **4.2 Cadastro**
![Nimus-Cadastro](https://user-images.githubusercontent.com/65822756/120557285-118f0200-c3d4-11eb-8e18-63a5af8674bb.png)
### **4.3 Login**
![Nimus-Login](https://user-images.githubusercontent.com/65822756/120557357-28cdef80-c3d4-11eb-9993-4394e8d8ad76.png)
### **4.4 Área do Cliente**
![Nimus-╡rea-do-Cliente](https://user-images.githubusercontent.com/65822756/120557476-5f0b6f00-c3d4-11eb-9eab-60781f5af6af.png)

### **4.5 Buscar Profissional**
![Nimus-Visualizar-Médicos](https://user-images.githubusercontent.com/65822756/120557592-8bbf8680-c3d4-11eb-98a8-1605b43ebdfa.png)
![Nimus-Visualizar-Médicos-1](https://user-images.githubusercontent.com/65822756/120557670-a7c32800-c3d4-11eb-9b87-585b58337221.png)


### **4.6 Agendamento de Consulta**
![Nimus-Marcar-Consulta](https://user-images.githubusercontent.com/65822756/120557423-44d19100-c3d4-11eb-8ee9-e55f38ae1c51.png)
![Nimus-Overlay-Marcada](https://user-images.githubusercontent.com/65822756/120557635-9bd76600-c3d4-11eb-92ec-bc59052a38f3.png)

### **4.7 Configurações**
![Nimus-ConfiguraçΣes](https://user-images.githubusercontent.com/65822756/120557972-1dc78f00-c3d5-11eb-9980-1d5ce42c6ea1.png)

##
### **5. Conclusão**
Logo, após o desenvolvimento do software é esperado uma maior facilidade para realizar contato com clinicas e profissionais da area da saúde, economizando tempo e custo em chamadas, além de abrir espaço para novas implementações, como por exemplo o aviso da proximidade de uma consulta agendada, remarcar consultas, e realização de consultas online caso seja possivel.
O uso de uma arquitetura em cloud também irá trazer a escalabilidade necessaria para atender tanto a profisisonais quanto pacientes e a facilitação da implementação e manutenção de servidores e ambientes necessarios para o funcionamento da aplicação.
