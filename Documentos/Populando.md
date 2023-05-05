+ [Populando camada (Bronze)](#Bronze)
    + [Data](#BronzeData)
    + [CDC NNDSS](#CDCNNDSS)
+ [Populando camada (Silver)](#Silver)
    + [Data](#SilverData)
    + [Semanal](#SilverSemanal)
    + [Geografia](#SilverGeografia)
+ [Populando camada (Gold)](#Gold)
    + [Data](#GoldData)
    + [Semanal](#GoldSemanal)
    + [Geografia](#GoldGeografia)

## Populando as camadas

<br/>

<a name = "Bronze"></a>
**Populando camada (Bronze)**
>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

Antes de prosseguir verifique se foram criados todos os Datasets a seguir:

![Untitled](/Imagens/Untitled%2072.png)

<br/>

<a name = "BronzeData"></a>
**Data**

Crie um novo pipeline

![Untitled](/Imagens/Untitled%2073.png)

Dê um nome para o pipeline

![Untitled](/Imagens/Untitled%2074.png)

Dentro do pipeline, crie um `Copiar dados`

![Untitled](/Imagens/Untitled%2075.png)

Dê um nome para a atividade `Copiar dados`

![Untitled](/Imagens/Untitled%2076.png)

Na aba `Origem`, em `Conjunto de dados de origem`, selecione o `Source_Data`

![Untitled](/Imagens/Untitled%2077.png)

Na aba `Coletor`, em `Conjunto de dados do coletor`, selecione `Bronze_Data`

![Untitled](/Imagens/Untitled%2078.png)

Para salvar, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%2079.png)

Clique em `Publicar`

Para rodar a atividade criada, clique em `Adicionar gatilho` e em seguida, `disparar agora`

![Untitled](/Imagens/Untitled%2080.png)

Clique em `OK`

![Untitled](/Imagens/Untitled%2081.png)

Aguarde a execução do Pipeline

![Untitled](/Imagens/Untitled%2082.png)

Após o aviso `Bem-sucedido`, verifique o contêiner criado no recurso `Conta de armazenamento`

![Untitled](/Imagens/Untitled%2083.png)

Dentro do contêiner, na pasta `Bronze`, verifique se foi criado o arquivo `data.csv`

![Untitled](/Imagens/Untitled%2084.png)

<br/>

<a name = "CDCNNDSS"></a>
**CDC NNDSS**

Crie um novo pipeline

![Untitled](/Imagens/Untitled%2085.png)

Dê um nome para o pipeline

![Untitled](/Imagens/Untitled%2086.png)

Dentro do pipeline, crie um `Copiar dados`

![Untitled](/Imagens/Untitled%2075.png)

Dê um nome para a atividade `Copiar dados`

![Untitled](/Imagens/Untitled%2087.png)

Na aba `Origem`, em `Conjunto de dados de origem`, selecione o `Source_CDC_NNDSS_Dados`

![Untitled](/Imagens/Untitled%2088.png)

Na aba `Coletor`, em `Conjunto de dados do coletor`, selecione `Bronze_CDC_Semanal`

![Untitled](/Imagens/Untitled%2089.png)

Para salvar, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%2090.png)

Clique em `Publicar`

Para rodar a atividade criada, clique em `Adicionar gatilho` e em seguida, `disparar agora`

![Untitled](/Imagens/Untitled%2091.png)

Clique em `OK`

![Untitled](/Imagens/Untitled%2092.png)

Aguarde a execução do Pipeline

![Untitled](/Imagens/Untitled%2093.png)

Após o aviso `Bem-sucedido`, verifique o contêiner criado no recurso `Conta de armazenamento`

![Untitled](/Imagens/Untitled%2094.png)

Dentro do contêiner, na pasta `Bronze`, verifique se foi criado o arquivo `CDC_Semanal.csv`

![Untitled](/Imagens/Untitled%2095.png)


<br/>

<a name = "Silver"></a>
**Populando camada (Silver)**

>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

<br/>

<a name = "SilverData"></a>
**Data**

Crie um novo fluxo de dados para receber os dados da camada Bronze

![Untitled](/Imagens/Untitled%2096.png)

Nomeie o Data flow

![Untitled](/Imagens/Untitled%2097.png)

Para adicionar o Dataset, clique em `Adicionar Origem`

![Untitled](/Imagens/Untitled%2098.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Bronze_Data`

![Untitled](/Imagens/Untitled%2099.png)

Clique na aba Inspecionar e verifique se os campos estão corretamente preenchidos

![Untitled](/Imagens/Untitled%20100.png)

Insira a próxima etapa do Data flow, que será o `Selecionar`

![Untitled](/Imagens/Untitled%20101.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20102.png)

Remova os espaços em vazios dos campos

![Untitled](/Imagens/Untitled%20103.png)

Insira a próxima etapa do Data flow, que será o `Coluna Derivada`

![Untitled](/Imagens/Untitled%20104.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20105.png)

Em `Colunas`, adicione as seguintes colunas e suas respectivas expressões:

![Untitled](/Imagens/Untitled%20106.png)

Clique em `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20107.png)

Mantenha a opção padrão

![Untitled](/Imagens/Untitled%20108.png)

Clique em `OK`

Aguarde até que se inicie a sessão de depuração

![Untitled](/Imagens/Untitled%20109.png)

Na aba `Visualização de dados`, verifique se os campos foram modificados corretamente

![Untitled](/Imagens/Untitled%20110.png)

Desabilite a `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20111.png)

Confirme a desativação da `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20112.png)

Clique em `OK`

Insira a próxima etapa do Data flow, que será o `Coletor`

![Untitled](/Imagens/Untitled%20113.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_Data`

![Untitled](/Imagens/Untitled%20114.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20115.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20116.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20117.png)

Clique em `Publicar`

Populando o arquivo `Silver_Data`

Crie um novo pipeline

![Untitled](/Imagens/Untitled%20118.png)

Dê um nome para o pipeline

![Untitled](/Imagens/Untitled%20119.png)

Dentro do pipeline, crie um fluxo de dados

![Untitled](/Imagens/Untitled%20120.png)

Dê um nome para o fluxo de dados

![Untitled](/Imagens/Untitled%20121.png)

Na aba configurações, selecione o fluxo de dados `BronzeDataToSilver`, criado anteriormente

![Untitled](/Imagens/Untitled%20122.png)

Para salvar o Pipeline criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20123.png)

Clique em `Publicar`

Para rodar o Pipeline, clique em `Adicionar gatilho` e em seguida, `disparar agora`

![Untitled](/Imagens/Untitled%20124.png)

Clique em `OK`

![Untitled](/Imagens/Untitled%20125.png)

Aguarde a execução do Pipeline

![Untitled](/Imagens/Untitled%20126.png)

Após o aviso `Bem-sucedido`, verifique o contêiner criado no recurso `Conta de armazenamento`

![Untitled](/Imagens/Untitled%20127.png)

Dentro do contêiner, na pasta `Silver`, verifique se foi criado o arquivo `Data.parquet`

![Untitled](/Imagens/Untitled%20128.png)
<br/>

<a name = "SilverSemanal"></a>
**Semanal**

Para começar a receber os dados da camada Bronze, importe os arquivos do CDC_Semanal

Em Datasets, acesse o `Bronze_CDC_Semanal`

![Untitled](/Imagens/Untitled%20129.png)

Para salvar a importação, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20130.png)

Clique em `Publicar`

Crie um novo fluxo de dados para receber os dados da camada Bronze

![Untitled](/Imagens/Untitled%20131.png)

Nomeie o Data flow

![Untitled](/Imagens/Untitled%20132.png)

Para adicionar o Dataset, clique em `Adicionar Origem`

![Untitled](/Imagens/Untitled%2098.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Bronze_CDC_Semanal`

![Untitled](/Imagens/Untitled%20133.png)

Clique na aba Inspecionar e verifique se os campos estão corretamente preenchidos

![Untitled](/Imagens/Untitled%20134.png)

Insira a próxima etapa do Data flow, que será o `Selecionar`

![Untitled](/Imagens/Untitled%20135.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20136.png)

Remova os espaços em vazios dos campos

![Untitled](/Imagens/Untitled%20137.png)

Clique em `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20138.png)

Mantenha a opção padrão

![Untitled](/Imagens/Untitled%20139.png)

Clique em `OK`

Aguarde até que se inicie a sessão de depuração

![Untitled](/Imagens/Untitled%20140.png)

![Untitled](/Imagens/Untitled%20141.png)

Na aba `Visualização de dados`, verifique se os campos foram modificados corretamente

![Untitled](/Imagens/Untitled%20142.png)

Insira a próxima etapa do Data flow, que será o `Coluna Derivada`

![Untitled](/Imagens/Untitled%20143.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20144.png)

Em `Colunas`, adicione as seguintes colunas e suas respectivas expressões:

| Latitude | replace(split(geocode,' ')[2],"(","") |
|  |  |
| Longitude | replace(split(geocode,' ')[3],")","") |
| CreatedDate | currentDate() |
| YearWeekKey | concat(CurrentMMWRYear, case(toInteger(MMWRWEEK) >= 10,MMWRWEEK,                                  concat(toString(0),MMWRWEEK))) |

![Untitled](/Imagens/Untitled%20145.png)

Na aba `Visualização de dados`, verifique se os campos foram modificados corretamente

![Untitled](/Imagens/Untitled%20146.png)

Insira a próxima etapa do Data flow, que será o `Coluna Derivada`

![Untitled](/Imagens/Untitled%20147.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20148.png)

Em `Colunas`, adicione as seguintes colunas e suas respectivas expressões:

| CurrentMMWRYear | toInteger(CurrentMMWRYear) |
|  |  |
| MMWRWEEK | toInteger(MMWRWEEK) |
| Currentweek | toInteger(Currentweek) |
| CumulativeYTDCurrentMMWRYear | toInteger(CumulativeYTDCurrentMMWRYear) |
| CumulativeYTDPreviousMMWRYear | toInteger(CumulativeYTDPreviousMMWRYear) |
| sort_order | toInteger(sort_order) |
| YearWeekKey | toInteger(YearWeekKey) |

![Untitled](/Imagens/Untitled%20149.png)

Verifique se o tipo dos dados foram alterados corretamente

![Untitled](/Imagens/Untitled%20150.png)

Desabilite a `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20151.png)

Confirme a desativação da `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20152.png)

Clique em `OK`

Insira a próxima etapa do Data flow, que será o `Coletor`

![Untitled](/Imagens/Untitled%20153.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_CDC_Semanal`

![Untitled](/Imagens/Untitled%20154.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20155.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20156.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20157.png)

Clique em `Publicar`

Populando o arquivo `Silver_CDC_Semanal`

Crie um novo pipeline

![Untitled](/Imagens/Untitled%20158.png)

Dê um nome para o pipeline

![Untitled](/Imagens/Untitled%20159.png)

Dentro do pipeline, crie um fluxo de dados

![Untitled](/Imagens/Untitled%20160.png)

Dê um nome para o `fluxo de dados`

![Untitled](/Imagens/Untitled%20161.png)

Na aba configurações, selecione o fluxo de dados `BronzeCDCToSilver`, criado anteriormente

![Untitled](/Imagens/Untitled%20162.png)

Para salvar o Pipeline criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20163.png)

Clique em `Publicar`

Para rodar o Pipeline, clique em `Adicionar gatilho` e em seguida, `disparar agora`

![Untitled](/Imagens/Untitled%20164.png)

Clique em `OK`

![Untitled](/Imagens/Untitled%20165.png)

Aguarde a execução do Pipeline

![Untitled](/Imagens/Untitled%20166.png)

Após o aviso `Bem-sucedido`, verifique o contêiner criado no recurso `Conta de armazenamento`

![Untitled](/Imagens/Untitled%20167.png)

Dentro do contêiner, na pasta `Silver`, verifique se foi criado o arquivo `CDC_Semanal.parquet`

![Untitled](/Imagens/Untitled%20168.png)
<br/>

<a name = "SilverGeografia"></a>
**Geografia**

Como os dados já foram carregados na etapa anterior, clone o `BronzeCDCToSilver`

![Untitled](/Imagens/Untitled%20169.png)

Renomeie o Data flow

![Untitled](/Imagens/Untitled%20170.png)

Apague as colunas mantendo apenas as colunas a seguir:

![Untitled](/Imagens/Untitled%20171.png)

Em `ColunaNova`, remova o `YearWeekKey`

![Untitled](/Imagens/Untitled%20172.png)

Exclua a etapa `AlterarTipoDado`

![Untitled](/Imagens/Untitled%20173.png)

No lugar do `AlterarTipoDado`, inclua o `Agregação`

![Untitled](/Imagens/Untitled%20174.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20175.png)

Em `Fluxo de entrada`, insira as seguintes colunas:

![Untitled](/Imagens/Untitled%20176.png)

Em `Agregações`, insira a coluna Agg e em expressão `count()`

![Untitled](/Imagens/Untitled%20177.png)

Clique em `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20178.png)

Mantenha a opção padrão

![Untitled](/Imagens/Untitled%20179.png)

Clique em `OK`

Aguarde até que se inicie a sessão de depuração

![Untitled](/Imagens/Untitled%20140.png)

![Untitled](/Imagens/Untitled%20141.png)

Na aba `Visualização de dados`, verifique se os campos foram modificados corretamente

![Untitled](/Imagens/Untitled%20180.png)

Desabilite a `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20181.png)

Confirme a desativação da `Depuração de fluxo de dados`

![Untitled](/Imagens/Untitled%20182.png)

Clique em `OK`

Insira a próxima etapa do Data flow, que será a `Chave Alternativa`

![Untitled](/Imagens/Untitled%20183.png)

Nomeie o fluxo de saída e insira um nome para a `Coluna da chave`

![Untitled](/Imagens/Untitled%20184.png)

Clique na aba `Inspecionar` e verifique se os campos estão corretamente preenchidos

![Untitled](/Imagens/Untitled%20185.png)

Insira a próxima etapa do Data flow, que será o `Selecionar`

![Untitled](/Imagens/Untitled%20186.png)

Nomeie o fluxo de saída e remova a coluna `Agg`

![Untitled](/Imagens/Untitled%20187.png)

Selecione o conjunto de dados `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%20188.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20189.png)

Na aba otimizar, verifique se a opção de partição esta em `Partição Única`

![Untitled](/Imagens/Untitled%20156.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20190.png)

Clique em `Publicar`

Populando o arquivo `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%20191.png)

Dê um nome para o pipeline

![Untitled](/Imagens/Untitled%20192.png)

Dentro do pipeline, crie um fluxo de dados

![Untitled](/Imagens/Untitled%20193.png)

Dê um nome para o fluxo de dados

![Untitled](/Imagens/Untitled%20194.png)

Na aba configurações, selecione o fluxo de dados `BronzeToSilverGeo`, criado anteriormente

![Untitled](/Imagens/Untitled%20195.png)

Para salvar o Pipeline criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20196.png)

Clique em `Publicar`

Para rodar o Pipeline, clique em `Adicionar gatilho` e em seguida, `disparar agora`

![Untitled](/Imagens/Untitled%20197.png)

Clique em `OK`

![Untitled](/Imagens/Untitled%20198.png)

Clique em `OK`

Aguarde a execução do Pipeline

![Untitled](/Imagens/Untitled%20199.png)

Após o aviso `Bem-sucedido`, verifique o contêiner criado no recurso `Conta de armazenamento`

![Untitled](/Imagens/Untitled%20200.png)

Dentro do contêiner, na pasta `Silver`, verifique se foi criado o arquivo `CDC_Geografia.parquet`

![Untitled](/Imagens/Untitled%20201.png)
<br/>

<a name = "Gold"></a>
Populando camada (Gold)

>💡 Para realizar esta etapa, é necessário ter concluído a etapa anterior.

<br/>

<a name = "GoldData"></a>
**Data**

Para começar a popular o arquivo de Data da camada Gold é necessário importar os dados da camada Bronze para a Silver

Acesse o Dataset `Silver_Data` e importe o esquema do arquivo.

![Untitled](/Imagens/Untitled%20202.png)

Verifique se os dados importados estão corretos

![Untitled](/Imagens/Untitled%20203.png)

Para gravar as alterações feitas, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20204.png)

Clique em `Publicar`

Para começar a utilizar o Dataset `Silver_Data`, crie um `Novo fluxo de dados`

![Untitled](/Imagens/Untitled%20205.png)

Dê um nome para o fluxo de dados

![Untitled](/Imagens/Untitled%20206.png)

Para adicionar o Dataset, clique em `Adicionar Origem`

![Untitled](/Imagens/Untitled%20207.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_Data`

![Untitled](/Imagens/Untitled%20208.png)

Adicione a próxima etapa do Dataflow, que será o `Coletor`

![Untitled](/Imagens/Untitled%20209.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_Data`

![Untitled](/Imagens/Untitled%20210.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20211.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20212.png)

Verifique se o Data flow ficou assim: 

![Untitled](/Imagens/Untitled%20213.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20214.png)

Clique em `Publicar`

<br/>

<a name = "GoldSemanal"></a>
**Semanal**

Para começar a popular o arquivo de CDC_Semanal da camada Gold é necessário importar os dados da camada Bronze para a Silver

Acesse o Dataset `Silver_CDC_Semanal` e importe o esquema do arquivo.

![Untitled](/Imagens/Untitled%20215.png)

Verifique se os dados importados estão corretos

![Untitled](/Imagens/Untitled%20216.png)

Para gravar as alterações feitas, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20217.png)

Clique em `Publicar`

Para começar a utilizar o Dataset `Silver_CDC_Semanal`, crie um `Novo fluxo de dados`

![Untitled](/Imagens/Untitled%20205.png)

Dê um nome para o fluxo de dados

![Untitled](/Imagens/Untitled%20218.png)

Para adicionar o Dataset no fluxo, clique em `Adicionar Origem`

![Untitled](/Imagens/Untitled%20219.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_CDC_Semanal`

![Untitled](/Imagens/Untitled%20220.png)

Adicione mais uma origem

![Untitled](/Imagens/Untitled%20221.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%20222.png)

Adicione ao `CopiaCDCSilver` a próxima etapa do Dataflow, que será a `Junção`

![Untitled](/Imagens/Untitled%20223.png)

Nomeie o fluxo de saída

No Fluxo esquerdo, selecione a `CopiaCDCSilver`

No Fluxo direito, selecione a `CopiaGeoSilver`

Em tipo de junção, selecione e `Externa esquerda`

Em condições de junção, selecione a `ReportingArea` de cada Dataset

![Untitled](/Imagens/Untitled%20224.png)

Insira a próxima etapa do Dataflow, que será o `Selecionar`

![Untitled](/Imagens/Untitled%20225.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20226.png)

Mantenha apenas as colunas a seguir:

![Untitled](/Imagens/Untitled%20227.png)

Insira a próxima etapa do Dataflow, que será o `Divisão Condicional`

![Untitled](/Imagens/Untitled%20228.png)

Em Nomes de fluxo, coloque os campos `States` e `GeoAggs`, na condição de `States` insira:

```bash
isNull(LOCATION2)
```

![Untitled](/Imagens/Untitled%20229.png)

Insira a próxima etapa do Dataflow, que será novamente o `Selecionar`

![Untitled](/Imagens/Untitled%20230.png)

Nomeie o fluxo de saída

![Untitled](/Imagens/Untitled%20231.png)

Remova a coluna `LOCATION2`

![Untitled](/Imagens/Untitled%20232.png)

Repita o mesmo processo para a continuação do `GeoAggs`

![Untitled](/Imagens/Untitled%20233.png)

![Untitled](/Imagens/Untitled%20234.png)

![Untitled](/Imagens/Untitled%20235.png)

Insira a próxima etapa do Data flow, que será o `Coletor`

![Untitled](/Imagens/Untitled%20236.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_CDC_Semanal_Estado`

![Untitled](/Imagens/Untitled%20237.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20238.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20239.png)

Repita o mesmo processo para a continuação do `GeoAggs`

![Untitled](/Imagens/Untitled%20240.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_CDC_Geografia_Agg`

![Untitled](/Imagens/Untitled%20241.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20242.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20243.png)

Adicione um Coletor para o `CopiaSilverCDC`

![Untitled](/Imagens/Untitled%20244.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_CDC_Semanal_normalizado`

![Untitled](/Imagens/Untitled%20245.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20246.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20243.png)

Verifique se o Data flow ficou assim: 

![Untitled](/Imagens/Untitled%20247.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20248.png)

Clique em `Publicar`
<br/>

<a name = "GoldGeografia"></a>
**Geografia**

Para começar a popular o arquivo de CDC_Geografia da camada Gold é necessário importar os dados da camada Bronze para a Silver

Acesse o Dataset `Silver_CDC_Geografia` e importe o esquema do arquivo.

![Untitled](/Imagens/Untitled%20249.png)

Verifique se os dados importados estão corretos

![Untitled](/Imagens/Untitled%20250.png)

Para gravar as alterações feitas, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20251.png)

Clique em `Publicar`

Para começar a utilizar o Dataset `Silver_CDC_Geografia`, crie um `Novo fluxo de dados`

![Untitled](/Imagens/Untitled%20205.png)

Dê um nome para o fluxo de dados

![Untitled](/Imagens/Untitled%20252.png)

Para adicionar o Dataset, clique em `Adicionar Origem`

![Untitled](/Imagens/Untitled%20253.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Silver_CDC_Geografia`

![Untitled](/Imagens/Untitled%20254.png)

Adicione a próxima etapa do Dataflow, que será a `Divisão Condicional`

![Untitled](/Imagens/Untitled%20255.png)

Em Nomes de fluxo, coloque os campos `States` e `GeoAggs`, na condição de `States` insira:

```bash
isNull(LOCATION2)
```

![Untitled](/Imagens/Untitled%20256.png)

Insira a próxima etapa do Dataflow, que será o `Coletor`

![Untitled](/Imagens/Untitled%20257.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_CDC_Geografia_Estado`

![Untitled](/Imagens/Untitled%20258.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20259.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20260.png)

Também gere um Coletor de saída de fluxo para o `GeoAggs`

![Untitled](/Imagens/Untitled%20261.png)

Nomeie o fluxo de saída e selecione o conjunto de dados `Gold_CDC_Geografia_Agg`

![Untitled](/Imagens/Untitled%20262.png)

Na aba configurações, selecione a opção de nome de arquivo como `Saída para arquivo único`

Na saída para arquivo único, nomeie o arquivo com a extensão `.parquet`

![Untitled](/Imagens/Untitled%20263.png)

Na aba otimizar, em opção de partição, selecione `Partição Única`

![Untitled](/Imagens/Untitled%20264.png)

Verifique se o Data flow ficou assim: 

![Untitled](/Imagens/Untitled%20265.png)

Para salvar o Data flow criado, clique em `Publicar tudo`

![Untitled](/Imagens/Untitled%20266.png)

Clique em `Publicar`