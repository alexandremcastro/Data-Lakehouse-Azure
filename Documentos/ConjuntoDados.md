+ [Importando dados](#ConjuntoDados)
    + [Importando os dados do CDC](#ImportandoDadosCDC)
    + [Importando os dados de Data](#ImportandoDadosData)
+ [Conjunto de dados (Bronze)](#ConjuntoBronze)
    + [Semanal](#BronzeSemanal)
    + [Data](#BronzeData)
+ [Conjunto de dados (Silver)](#ConjuntoSilver)
    + [Semanal](#SilverSemanal)
    + [Geografia](#SilverGeografia)
    + [Data](#SilverData)
+ [Conjunto de dados (Gold)](#ConjuntoGold)
    + [Data](#GoldData)
    + [Geografia](#GoldGeografia)
    + [Semanal](#GoldSemanal)

<a name = "ConjuntoDados"></a>
## Importando dados

Primeira etapa do Data Lakehouse, importar os dados referentes a camada `Source`

![Untitled](/Imagens/Untitled%2018.png)

Acesse o recurso Data Factory, clique em `Iniciar estúdio`

![Untitled](/Imagens/Untitled%2019.png)

Clique em `Novo` `Conjunto de Dados`

![Untitled](/Imagens/Untitled%2020.png)

Selecione o `HTTP` e clique em `Continuar`

![Untitled](/Imagens/Untitled%2021.png)

Em formato selecione `CSV` e clique em `Continuar`

![Untitled](/Imagens/Untitled%2022.png)

<br/>

<a name = "ImportandoDadosCDC"></a>
**Importando os dados do CDC**

Em `Definir as propriedades`, de um nome para o arquivo, selecione a opção`Primeira linha como cabeçalho`

![Untitled](/Imagens/Untitled%2023.png)

Em serviço vinculado, selecione `+ Novo`

Dê um nome para o serviço e insira o link de download do CSV

[](https://data.cdc.gov/api/views/x9gk-5huc/rows.csv?accessType=DOWNLOAD)

Em `Tipo de Autenticação`, selecione `Anônimo`e clique em `Criar`

![Untitled](/Imagens/Untitled%2024.png)

Em seguida clique em `OK`

Para testar a configuração, clique em `Testar conexão`, na aba Conexão

![Untitled](/Imagens/Untitled%2025.png)

Para verificar o schema, clique em `Importar esquema`, na aba Esquema

![Untitled](/Imagens/Untitled%2026.png)

<br/>

<a name = "ImportandoDadosData"></a>
**Importando os dados de Data**

Em `Definir as propriedades`, de um nome para o arquivo, selecione a opção`Primeira linha como cabeçalho`

![Untitled](/Imagens/Untitled%2027.png)

Em serviço vinculado, selecione `+ Novo`

Dê um nome para o serviço e insira o link de download do CSV

[Link](https://raw.githubusercontent.com/alexandremcastro/Data-Lakehouse-Azure/main/data.csv)

Em `Tipo de Autenticação`, selecione `Anônimo`e clique em `Criar`

![Untitled](/Imagens/Untitled%2028.png)

Em seguida clique em `OK`

Para testar a configuração, clique em `Testar conexão`, na aba Conexão

![Untitled](/Imagens/Untitled%2029.png)

Para verificar o schema, clique em `Importar esquema`, na aba Esquema

![Untitled](/Imagens/Untitled%2030.png)

<br/>

<a name = "ConjuntoBronze"></a>
**Conjunto de dados (Bronze)**

>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

![Untitled](/Imagens/Untitled%2031.png)

>💡 Os seguintes passos relacionados à clonagem têm como objetivo simplificar e acelerar o processo de implementação.

<a name = "BronzeSemanal"></a>
**Semanal**

No estúdio do recurso Data Factory, importe um novo conjunto de dados, selecione o `Azure Data Lake Storage Gen2`

![Untitled](/Imagens/Untitled%2032.png)

Clique em `Continuar`

Seleciona o formato `CSV`

![Untitled](/Imagens/Untitled%2033.png)

Clique em `Continuar`

Dê um nome

Em `Definir as propriedades`, de um nome para o arquivo, selecione a opção`Primeira linha como cabeçalho`

![Untitled](/Imagens/Untitled%2034.png)

Em serviço vinculado, selecione `+ Novo`

Em Assinatura do Azure, selecione a sua assinatura da Azure

Em Nome da conta de armazenamento, selecione o nome do recurso `Conta de armazenamento` criado

![Untitled](/Imagens/Untitled%2035.png)

Clique em `Criar`

Em `Definir as propriedades`, insira o diretório do `contêiner`

![Untitled](/Imagens/Untitled%2036.png)

Clique em `OK`

Em caminho do arquivo, siga o padrão `contêiner/Bronze/arquivo.csv`

![Untitled](/Imagens/Untitled%2037.png)

No caso ficou `lakehouse/Bronze/CDC_Semanal.csv`

<a name = "BronzeData"></a>
**Data**

Repita o mesmo processo do semanal, só que para o arquivo de data

![Untitled](/Imagens/Untitled%2038.png)

![Untitled](/Imagens/Untitled%2039.png)

<br/>

<a name = "ConjuntoSilver"></a>
**Conjunto de dados (Silver)**

>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

![Untitled](/Imagens/Untitled%2040.png)

>💡 Os seguintes passos relacionados à clonagem têm como objetivo simplificar e acelerar o processo de implementação.

<a name = "SilverSemanal"></a>
**Semanal**

No estúdio do recurso Data Factory, importe um novo conjunto de dados

![Untitled](/Imagens/Untitled%2041.png)

Selecione o `Azure Data Lake Storage Gen2`

![Untitled](/Imagens/Untitled%2042.png)

Clique em `Continuar`

Seleciona o formato `CSV`

![Untitled](/Imagens/Untitled%2043.png)

Clique em `Continuar`

Em `Definir as propriedades`, de um nome para o conjunto de dados, selecione o serviço vinculado e no primeiro campo do caminho do arquivo, escreva o nome do contêiner.

![Untitled](/Imagens/Untitled%2044.png)

Clique em `OK`

No campo do meio do caminho do arquivo, escreva Silver

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2045.png)

<a name = "SilverGeografia"></a>
**Geografia**

Clone o `Silver_CDC_Semanal`

![Untitled](/Imagens/Untitled%2046.png)

Altere o nome para `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%2047.png)

No campo do meio do caminho do arquivo, escreva `Silver`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2048.png)

<a name = "SilverData"></a>
**Data**

Clone o `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%2049.png)

Altere o nome para `Silver_Data`

![Untitled](/Imagens/Untitled%2050.png)

No campo do meio do caminho do arquivo, escreva `Silver`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2051.png)

<br/>

<a name = "ConjuntoGold"></a>
**Conjunto de dados (Gold)**

>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

![Untitled](/Imagens/Untitled%2052.png)

>💡 Os seguintes passos relacionados à clonagem têm como objetivo simplificar e acelerar o processo de implementação.

<a name = "GoldData"></a>
**Data**

Clone o `Silver_Data`

![Untitled](/Imagens/Untitled%2053.png)

Altere o nome para `Gold_Data`

![Untitled](/Imagens/Untitled%2054.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2055.png)

<a name = "GoldGeografia"></a>
**Geografia**

Clone o `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%2056.png)

Altere o nome para `Gold_CDC_Geografia_Estado`

![Untitled](/Imagens/Untitled%2057.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2058.png)

Clone o `Gold_CDC_Geografia_Estado`

![Untitled](/Imagens/Untitled%2059.png)

Altere o nome para `Gold_CDC_Geografia_Agg`

![Untitled](/Imagens/Untitled%2060.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2061.png)

<a name = "GoldSemanal"></a>
**Semanal**

Clone o `Silver_CDC_Semanal`

![Untitled](/Imagens/Untitled%2062.png)

Altere o nome para `Gold_CDC_Semanal_Estado`

![Untitled](/Imagens/Untitled%2063.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2064.png)

Clone o `Gold_CDC_Semanal_Estado`

![Untitled](/Imagens/Untitled%2065.png)

Altere o nome para `Gold_CDC_Semanal_Agg`

![Untitled](/Imagens/Untitled%2066.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2067.png)

Clone o `Silver_CDC_Semanal`

![Untitled](/Imagens/Untitled%2068.png)

Altere o nome para `Gold_CDC_Semanal_normalizado`

![Untitled](/Imagens/Untitled%2069.png)

No campo do meio do caminho do arquivo, escreva `Gold`

No último campo, escreva o nome do arquivo com a terminação `.parquet`

![Untitled](/Imagens/Untitled%2070.png)

Agora publique tudo

![Untitled](/Imagens/Untitled%2071.png)

Clique em `Publicar`