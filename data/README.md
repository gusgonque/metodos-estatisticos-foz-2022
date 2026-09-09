# Dados

Os arquivos de dados brutos **não são armazenados neste repositório**. Eles são disponibilizados publicamente pelo Instituto Brasileiro de Geografia e Estatística (IBGE) no contexto do Censo Demográfico 2022.

## Arquivos utilizados

### 1. Atributos dos setores censitários do Brasil

Arquivo esperado pelo notebook:

```text
BR_setores_CD2022.csv
```

Fonte oficial do IBGE:

https://ftp.ibge.gov.br/Censos/Censo_Demografico_2022/Agregados_por_Setores_Censitarios/malha_com_atributos/setores/csv/BR_setores_CD2022.csv

O arquivo contém os atributos dos setores censitários. No notebook, os registros são filtrados para Foz do Iguaçu pelo código municipal `4108304`.

### 2. Malha dos setores censitários do Paraná

Arquivo esperado pelo notebook:

```text
PR_setores_CD2022.gpkg
```

Fonte oficial do IBGE:

https://ftp.ibge.gov.br/Censos/Censo_Demografico_2022/Agregados_por_Setores_Censitarios/malha_com_atributos/setores/gpkg/UF/PR/PR_setores_CD2022.gpkg

A geometria é associada aos atributos pelo campo `CD_SETOR`.

## Organização sugerida

Após o download, você pode organizar os arquivos localmente assim:

```text
data/
├── BR_setores_CD2022.csv
└── PR_setores_CD2022.gpkg
```

O notebook original foi desenvolvido no Google Colab com os arquivos armazenados no Google Drive. Para reproduzir a análise em outro ambiente, ajuste os caminhos das células de importação.

## Observação sobre licenciamento

A licença MIT deste repositório se aplica ao código e ao material autoral do projeto. Ela **não altera a titularidade ou as condições de uso dos dados do IBGE**.
