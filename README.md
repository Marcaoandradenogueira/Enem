# Cloud Data Warehouse Enem

### Introdução

Esse é um projeto para criar uma Data Warehouse na nuvem utilizando o Redshift e realizar analises sobre os dados do Enem 2017.

## Como começar

Para executar esse projeto, será necessário:

Python 3
configparser
pandas
boto3
json
pandas_redshift
seaborn

## Desenvolvedor

Para desenvolver esse projeto é necessário uma CHAVE e um SEGREDO da AWS e configurar esses valores dentro do arquivo dwh.cf

### Construção

1. Executar IaC.ipynb para criar a regra IAM e o cluster Redshift
2. Rodar ETL.ipynb para fazer o processo de extração, tansformação e carregamento dos dados
2.1 Caso seja necessário execute a última célula para limpar os dados das cidades
3. Execute Correlação Nota,IDH, população.ipynb para extrair dados referente a correlação entre nota, idh e população.

### Nesse projeto analistas de dados e cientistas de dados poderão realizar consultas no DataWarehouse para conseguir ideias e entendimento sobre os daddos do Enem 2017

### Descrição das tabelas

#### Staging Area

##### Staging_enem

Dados retirados do arquivo MICRODADOS_ENEM_2017.csv.gz com informações sobre as notas dos incritos no Enem 2017.

##### Staging_cidade

Dados retirados do arquivo cidades.csv com informações gerais sobre a cidade.

#### Data Warehouse

##### dim_inscrito

Tabela de dimensão com dados dos inscritos como cidade em que nasceu e dados referentes a qualidade sócio-economica do inscrito.


##### dim_escola

Tabela de dimensão com dados da escola.

##### fat_enem

Tabela de fato com informações sobre as notas dos inscritos.

#### Data bus

##### view_unpivot_fat_enem

View com dados da fat_enem unpivotados para facilitar o drill-down sobre disciplina.

##### view_agg_fat_enem

View com dados agregados da view_unpivot_fat_enem para facilitar a consulta.


