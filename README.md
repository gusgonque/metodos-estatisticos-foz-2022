# Métodos Estatísticos aplicados aos setores censitários de Foz do Iguaçu

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gusgonque/metodos-estatisticos-foz-2022/blob/main/notebooks/Mestrado_Estatistica.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Projeto desenvolvido para a disciplina **Métodos Estatísticos Avançados**, utilizando dados do **Censo Demográfico 2022 do IBGE** para analisar a distribuição da população e da densidade populacional entre os setores censitários de **Foz do Iguaçu (PR)**.

## Pergunta de pesquisa

> Como se distribuem a população e a densidade populacional entre os setores censitários de Foz do Iguaçu?

O trabalho também usa a base completa como referência para avaliar, de forma didática, procedimentos de **amostragem** e **estimação**.

## Base de dados

- **Fonte:** Instituto Brasileiro de Geografia e Estatística (IBGE), Censo Demográfico 2022.
- **Unidade de análise:** setor censitário.
- **Recorte:** município de Foz do Iguaçu (código IBGE `4108304`).
- **Número de setores analisados:** `522`.
- **População total no recorte:** `285.415` habitantes.
- **Variáveis principais:** população residente e densidade populacional (`POPULACAO / AREA_KM2`).

Os arquivos brutos não são versionados neste repositório por causa do tamanho e por serem distribuídos oficialmente pelo IBGE. As instruções e os links de obtenção estão em [`data/README.md`](data/README.md).

## Etapas da análise

1. Preparação, recorte municipal e junção da geometria.
2. Verificação da qualidade e coerência dos dados.
3. Estatística descritiva: frequências, posição, dispersão, assimetria, curtose, histogramas, boxplots e mapas coropléticos.
4. Dimensionamento amostral para população finita.
5. Comparação entre Amostragem Aleatória Simples (AAS) e Amostragem Aleatória Estratificada proporcional (AAE).
6. Simulação de 1.000 amostras para comparar o comportamento dos métodos.
7. Estimação pontual e intervalar, incluindo correção para população finita.
8. Avaliação didática de intervalos para variância e desvio padrão sob as condições discutidas no trabalho.

## Principais resultados

| Indicador | População por setor | Densidade populacional |
|---|---:|---:|
| Média | 546,77 hab. | 4.870,73 hab./km² |
| Mediana | 558 hab. | 4.179,99 hab./km² |
| Coeficiente de variação | 57,87% | 86,71% |
| Assimetria de Pearson | ≈ -0,01 | ≈ 0,68 |
| Outliers superiores (boxplot) | 6 | 8 |

A população por setor apresentou distribuição aproximadamente simétrica, porém com elevada dispersão. A densidade populacional foi ainda mais heterogênea, com assimetria positiva moderada e poucos setores com valores muito elevados.

### Amostragem

Foi adotada uma amostra de **187 setores**. Em uma realização específica, a AAE apresentou menor erro para a população, enquanto a AAS apresentou menor erro para a densidade. Entretanto, nas **1.000 repetições**, a AAE apresentou erros médios ligeiramente menores nas duas variáveis:

| Variável | Erro médio AAS | Erro médio AAE |
|---|---:|---:|
| População | 2,75% | 2,60% |
| Densidade | 4,07% | 3,93% |

A diferença foi pequena, mostrando que a estratificação por situação territorial melhora modestamente a precisão, mas não elimina a elevada variabilidade existente dentro do estrato urbano.

### Estimação

Os intervalos de confiança de 95% para as médias foram avaliados usando a população completa como referência. A correção para população finita foi relevante porque a amostra representa aproximadamente **35,8%** dos 522 setores. Nas simulações, os intervalos corrigidos apresentaram cobertura próxima do nível nominal de 95%.

## Estrutura do repositório

```text
metodos-estatisticos-foz-2022/
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── .gitignore
├── data/
│   └── README.md
└── notebooks/
    └── Mestrado_Estatistica.ipynb
```

## Como reproduzir

1. Clone o repositório.
2. Instale as dependências com `pip install -r requirements.txt`.
3. Baixe os arquivos do IBGE indicados em [`data/README.md`](data/README.md).
4. Ajuste, no notebook, os caminhos das células de carregamento do CSV e do GeoPackage para o local em que os arquivos foram salvos.
5. Execute o notebook a partir do início.

> A versão publicada do notebook é uma versão leve voltada à reprodução: preserva a estrutura da análise e as células de código, mas remove as saídas de execução e os textos interpretativos extensos. Os resultados e interpretações principais estão resumidos neste README; tabelas, gráficos e mapas são regenerados ao executar o notebook.

## Tecnologias

Python, pandas, NumPy, GeoPandas, Matplotlib, SciPy, Folium, Mapclassify e Google Colab.

## Licença e dados

O **código e o material autoral deste repositório** são disponibilizados sob a licença [MIT](LICENSE).

Os **dados do Censo Demográfico 2022** pertencem ao IBGE e devem ser utilizados e citados conforme as condições e a documentação da fonte oficial. Os arquivos brutos não são redistribuídos neste repositório.

## Autor

**Gustavo Gonçalves Queiroz**  
GitHub: [@gusgonque](https://github.com/gusgonque)
