# Projeto Integrador — Análise de Sentimentos
### Grupo: Isabelli, Larissa, Samantha, Samuel Nunes

## 📂 Estrutura do Repositório

O repositório está organizado da seguinte forma:

### 📒 Notebook Principal

* **Arquivo `.ipynb`** contendo todo o código do projeto, análises, tratamento dos dados e geração de visualizações.

### 📊 Gráficos

* Pasta contendo os **arquivos `.png` dos gráficos gerados**, utilizados para visualização dos resultados obtidos ao longo da análise.

### 🗂️ Arquivos de Dados

O projeto disponibiliza os dados em dois formatos:

#### Pasta `parquet/`

Contém os arquivos no formato **Parquet**, utilizados para otimizar armazenamento e performance na leitura dos dados.

#### Pasta `csv/`

Contém os arquivos no formato **CSV**, utilizados para leitura tradicional dos datasets.

---

## ⚠️ Importante sobre a execução do código

O código atual do notebook está configurado para ler os arquivos diretamente do **Google Drive**, utilizando o Google Colab.

Exemplo da configuração atual:

```python
from google.colab import drive
drive.mount('/content/drive')

import pandas as pd

# pasta onde estão os arquivos CSV
pasta_csv = "/content/drive/MyDrive/Colab Notebooks/projeto integrador /"

# lista com os nomes dos arquivos
arquivos = [
    "pedidos",
    "produtos",
    "tabela_auxiliar",
    "vendedores",
    "geolocalizacao",
    "itens_pedidos",
    "pagamentos",
    "avaliacoes",
    "clientes"
]

# dicionário para armazenar os DataFrames
df = {}

# loop para ler os arquivos
for nome in arquivos:
    caminho = f"{pasta_csv}{nome}.csv"
    df[nome] = pd.read_csv(caminho, encoding="utf-8")
    print(f"{nome} carregado com sucesso!")

display(df["clientes"].head())
```

---

## ✅ Como rodar o projeto localmente

Para executar o notebook diretamente a partir dos arquivos presentes neste repositório, é necessário alterar o caminho de leitura dos dados para utilizar a pasta local `csv/`.

Utilize o código abaixo:

```python
import pandas as pd
import os

# pasta local dos arquivos CSV
pasta_csv = "./csv/"

# lista com os nomes dos arquivos
arquivos = [
    "pedidos",
    "produtos",
    "tabela_auxiliar",
    "vendedores",
    "geolocalizacao",
    "itens_pedidos",
    "pagamentos",
    "avaliacoes",
    "clientes"
]

# dicionário para armazenar os DataFrames
df = {}

# loop para ler os arquivos
for nome in arquivos:
    caminho = os.path.join(pasta_csv, f"{nome}.csv")
    df[nome] = pd.read_csv(caminho, encoding="utf-8")
    print(f"{nome} carregado com sucesso!")

# exemplo
display(df["clientes"].head())
```

> **Observação:** Para esse código funcionar corretamente, mantenha a pasta `csv/` no mesmo diretório do notebook (`.ipynb`).
