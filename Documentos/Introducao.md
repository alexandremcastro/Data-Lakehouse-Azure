+ [Introdução](#Introducao)
    + [Arquitetura do projeto](#Arquitetura)
    + [Criando grupo de recursos](#GrupoRecursos)
    + [Criando o recursos](#Recursos)
        + [Conta de armazenamento](#ContaArmazenamento)
        + [Data Factory](#DataFactory)

<a name = "Introducao"></a>
## Introdução

<a name = "Arquitetura"></a>
**Arquitetura do projeto**

Modelo de arquitetura que será seguido

![Group 1 (3).jpg](/Imagens/Group_1_(3).jpg)

<br/>

<a name = "GrupoRecursos"></a>
**Criando grupo de recursos**

Para criar um grupo de recursos, vá na página inicial da [Microsoft Azure](https://portal.azure.com/#home).

Em pesquisar recursos, serviços e documentos, procure por`Grupos de recursos`

![Untitled](/Imagens/Untitled.png)

Ao entrar no grupo de recursos, clique em `Criar grupo de recursos`

![Untitled](/Imagens/Untitled%201.png)

Em `Grupo de recursos`, digite um nome identificador do nome do grupo de recursos.

![Untitled](/Imagens/Untitled%202.png)

Para finalizar a criação do grupo de recurso, clique em `Revisar + criar`

Verifique se as opções estão configuradas corretamente.

![Untitled](/Imagens/Untitled%203.png)

Após verificar, clique em `Criar`.

<br/>

<a name = "Recursos"></a>
**Criando o recursos**

Para criar um recurso, vá na página inicial da [Microsoft Azure](https://portal.azure.com/#home).

Em pesquisar recursos, serviços e documentos, procure por `Grupos de recursos`

![Untitled](/Imagens/Untitled.png)

Em `Grupos de recursos`, entre no grupo criado na etapa de `Criando grupo de recursos`

Para criar um recurso do grupo, clique em `Criar`

![Untitled](/Imagens/Untitled%204.png)

>💡 Os passos a seguir, visam o baixo custo para o projeto, já que é uma simulação de um projeto real, mas em casos reais, são feitas outras configurações de acordo com a realidade do cliente/empresa.

<br/>
<a name = "ContaArmazenamento"></a>
**Conta de armazenamento**

Em `Pesquisar no Marketplace`, digite `Conta de armazenamento`

No serviço `Conta de armazenamento`, clique em `Criar`

![Untitled](/Imagens/Untitled%205.png)

Dentro da criação do recurso, em `Detalhes do projeto`, mantenha as configurações por padrão.

![Untitled](/Imagens/Untitled%206.png)

Dentro da criação do recurso, em `Detalhes da instância`:

Dê um nome único para a conta de armazenamento, no meu caso `lakehousedata`;

Em `Região`, selecione a `(South America) Brazil South`;

Em `Desempenho`, mantenha em `Standard`;

Em Redundância, selecione `LRS (armazenamento com redundância local)`.

![Untitled](/Imagens/Untitled%207.png)

Acesse a aba `Proteção de dados`

![Untitled](/Imagens/Untitled%208.png)

Em `Recuperação`, desmarque todas as opções, nas outras opções, mantenha por padrão desmarcadas também e clique em `Review`.

Verifique se todas as configurações estão corretas e então, clique em `Criar`

![Untitled](/Imagens/Untitled%209.png)

Aguarde alguns segundos até que a implantação seja concluída

![Untitled](/Imagens/Untitled%2010.png)

Após concluída, clique em `Ir para o recurso`

No `Propriedades`do recurso, clique em `Serviço Blob`

![Untitled](/Imagens/Untitled%2011.png)

No `Serviço Blob`, clique em `+Contêiner`

![Untitled](/Imagens/Untitled%2012.png)

Dê um nome ao contêiner e mantenha o `Nível de acesso público` em `Privado`, após, clique em `Criar`

![Untitled](/Imagens/Untitled%2013.png)

<br/>

<a name = "DataFactory"></a>
**Data Factory**

Em `Pesquisar no Marketplace`, digite `Data Factory`

No serviço `Data Factory`, clique em `Criar`

![Untitled](/Imagens/Untitled%2014.png)

Na aba, Básico, em `Detalhes do projeto`, mantenha as configurações por padrão.

![Untitled](/Imagens/Untitled%2015.png)

Na aba, Básico, em `Detalhes da instância`:

Em `Nome`, digite um nome único para o recurso;

Em `Região`, selecione `Brazil South`;

Em `Versão`, mantenha `V2`

![Untitled](/Imagens/Untitled%2016.png)

Clique em `Examinar + criar`

Verifique se esta configurado corretamente

![Untitled](/Imagens/Untitled%2017.png)

Clique em `Criar`