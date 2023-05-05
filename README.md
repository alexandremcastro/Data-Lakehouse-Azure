# Data Warehouse Cloud Azure
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/alexandremcastro/Data-Warehouse-Cloud-Azure/blob/main/LICENSE)

> **📝 Nota**: Eu não sou responsável pelos custos do projeto, isso significa que qualquer gasto que ocorra durante a realização do projeto, como utilização de serviços, não é de minha responsabilidade. É importante que você esteja ciente desses custos e os gerencie adequadamente.

Um projeto de Data Lakehouse utilizando os serviços em nuvem da Microsoft Azure pode ser uma solução eficiente e escalável para armazenamento, processamento e análise de dados estruturados e não estruturados.

O primeiro passo seria configurar um armazenamento de dados em nuvem com o Azure Data Lake Storage Gen2. Esse serviço permite o armazenamento de grandes quantidades de dados em formato de arquivo e oferece recursos avançados de segurança, controle de acesso e gerenciamento de custos.

Para a integração com outras ferramentas e serviços, seria recomendado utilizar o Azure Data Factory, que permite a orquestração de pipelines de dados em diferentes plataformas e sistemas. O Data Factory também oferece recursos avançados de monitoramento, diagnóstico e gerenciamento de erros.


Essa será a arquitetura a ser seguida no projeto:
![Group 1 (3).jpg](/Imagens/Group_1_(3).jpg)

## Ferramenta utilizada

> **📝 Nota**: 💡 Este projeto foi executado em Março de 2023, e é importante ressaltar que alguns dos requisitos abordados podem sofrer alterações ao longo do tempo. Como em qualquer área de tecnologia, novas soluções e tecnologias surgem constantemente, o que pode tornar algumas das abordagens e soluções apresentadas neste projeto desatualizadas em algum momento. <br/>

[Azure Data Factory](https://azure.microsoft.com/pt-br/products/data-factory): O Azure Data Factory é um serviço de integração de dados baseado na nuvem, desenvolvido pela Microsoft. Ele permite orquestrar e automatizar fluxos de dados entre diferentes fontes e destinos, transformando e processando dados em larga escala, em ambientes híbridos ou totalmente em nuvem.

## Motivação

Implemente esse texto: Este projeto experimental é o resultado das minhas experiências com Data Lakehouse. Durante o processo de criação, tive a oportunidade de explorar diversas ferramentas e serviços em nuvem, incluindo o Microsoft Azure Data Lake Storage Gen2 e Azure Data Factory.

Ao longo do projeto, fui capaz de armazenar e processar de dados de diferentes fontes, realizando tarefas de extração, transformação e carga (ETL), além de criar pipelines de processamento automatizados seguindo o conceito de arquitetura medalhão.

## Sumário

+ [Introdução](/Documentos/Introducao.md)
    + [Arquitetura do projeto](/Documentos/Introducao.md#Arquitetura)
    + [Criando grupo de recursos](/Documentos/Introducao.md#GrupoRecursos)
    + [Criando o recursos](/Documentos/Introducao.md#Recursos)
+ [Conjunto de dados](/Documentos/ConjuntoDados.md)
    + [Importando os dados do CDC](/Documentos/ConjuntoDados.md#ImportandoDados)
    + [Conjunto de dados (Bronze)](/Documentos/ConjuntoDados.md#ConjuntoBronze)
    + [Conjunto de dados (Silver)](/Documentos/ConjuntoDados.md#ConjuntoSilver)
    + [Conjunto de dados (Gold)](/Documentos/ConjuntoDados.md#ConjuntoGold)
+ [Populando as camadas](/Documentos/Populando.md#Populando)
    + [Populando camada (Bronze)](/Documentos/Populando.md#PopulandoBronze)
    + [Populando camada (Silver)](/Documentos/Populando.md#PopulandoSilver)
    + [Populando camada (Gold)](/Documentos/Populando.md#PopulandoGold)

## Pré-requisitos

* **Cadastro:** 
    É preciso possuir uma conta na Microsoft Azure. Se você ainda não possui uma, pode criar uma facilmente no site oficial da plataforma. Basta fornecer algumas informações básicas e escolher o plano que melhor atenda às suas necessidades. 

    Além disso, é importante estar familiarizado com os conceitos básicos de computação em nuvem e ter conhecimento sobre a arquitetura dos serviços que deseja utilizar. A Microsoft Azure oferece uma vasta documentação e tutoriais para ajudar seus usuários a entenderem esses conceitos e a aproveitarem ao máximo seus serviços.

* **Rede:** A Microsoft Azure requer uma rede adequada para comunicação com a Nuvem. Verifique se a rede suporta entrar em conexão com a Web sem maiores problemas.

## Tarefas

**Tarefas concluídas:**

- [x] Descrever sobre a finalidade do Data Lakehouse
- [x] Criar uma conta na Microsoft Azure
- [x] Criar o grupo de recursos
- [x] Criar o recurso conta de armazenamento
- [x] Criar o recurso Data Factory
- [x] Importar os dados do CDC (NNDSS)
- [x] Criar os Datasets (Bronze, Silver e Gold)
- [x] Criar os Pipelines (Copia e fluxo de dados)
- [x] Criar os Data flows (Bronze, Silver e Gold)

**Futuras implementações:**

- [ ] Automatizar a coleta semanal dos dados
- [ ] Automatizar a criação de snapshots semanais
- [ ] Automatizar a criação de relatórios no PowerBI diretamente da camada Gold

## Links

**Projeto:** 

* [Projeto no site]()

* [Projeto no Notion]()

* [Projeto no GitLab]()

* [Projeto no GitHub]()

**Artigos orientados:** 

* [What's a Data Lakehouse -  Databricks](https://www.databricks.com/glossary/data-lakehouse)

* [O que é uma Data Lakehouse? - Oracle](https://www.oracle.com/br/big-data/what-is-data-lakehouse/)

* [O que é arquitetura medalhão no Lakehouse? - Microsoft](https://learn.microsoft.com/pt-br/azure/databricks/lakehouse/medallion)

* [Implementing Data Lakehouse in an Enterprise - Medium](https://medium.com/@lackshub/implementing-data-lakehouse-in-an-enterprise-1cb559df714d)

## Conclusão
Em resumo, um projeto de data lakehouse utilizando os serviços em nuvem da Microsoft Azure pode ser uma solução escalável e eficiente para o armazenamento, processamento e análise de dados em larga escala, com recursos avançados de segurança, integração e gerenciamento de custos.