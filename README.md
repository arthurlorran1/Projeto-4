![bannergithub](https://github.com/CassioRibeiro/ProjetoFinal/assets/120439075/89aadd85-e874-4288-8009-5d2099cce9d9)

# Projeto 4 - Dados para Abastecer o Carro

## Conteúdo do Projeto
- [Contexto](#contexto)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Status](#status)
- [Download](#download)

## Contexto

Este projeto visa realizar uma análise exploratória dos preços da gasolina e do etanol nos dois últimos meses do ano atual, utilizando dados disponíveis no portal gov.br. Serão exploradas diversas perguntas relacionadas ao comportamento dos preços, médias por estado, municípios com os menores e maiores preços, correlações entre preços e regiões, além de outras questões adicionais.

## Estrutura do Projeto

- `Data/`: Pasta contendo os arquivos de dados e daso para o funcionamento do      README.
- `Doc/`: Contem os PDFs do trabalho e arquivos de teste.
- `notebooks/`: Pasta contendo o Jupyter Notebook desenvolvido.
- `presentation/`: Pasta contendo slides de apoio para a apresentação.
- `README.md`: Documentação principal do projeto.

## PDF do Projeto
- [PDF com Instruções e Detalhes do Projeto](Doc/1694464991_SEDadosM4Projetoemgrupopdf.pdf)

## Requisitos

- **Python 3.x:** Download Python
- **Pandas:** Instale com !pip install pandas
- **NumPy:** Instale com !pip install numpy
- **Matplotlib:** Instale com !pip install matplotlib

## Download

[![Download ZIP](https://img.shields.io/badge/Download_-ZIP-green?style=for-the-badge&logo=github)](https://github.com/NewKanvas/Projeto-4/archive/main.zip)

---

## Principais códigos

1. **Importando Bibliotecas e Carregando os dados**:

```
import pandas as pd
import numpy as np

etanol11 = pd.read_csv('../Data/precos-gasolina-etanol-11.csv', sep=';')
etanol12 = pd.read_csv('../Data/precos-gasolina-etanol-12.csv', sep=';')

```
2. **Limpeza e Preparação de Dados**:

```
df = pd.concat([etanol11,etanol12], ignore_index=True) # Juntando as duas tabelas

df.drop(['Cep','CNPJ da Revenda','Valor de Compra','Unidade de Medida','Complemento','Numero Rua','Nome da Rua'], inplace=True, axis='columns') # Retirando

df = df.reindex(columns=['Regiao - Sigla','Estado - Sigla','Municipio','Bairro','Bandeira','Revenda','Valor de Venda','Produto','Data da Coleta']) # Reordenando rotulos

df['Data da Coleta'] = pd.to_datetime(df['Data da Coleta'], format='%d/%m/%Y') # Mudando o Formato de Data 

df['Valor de Venda'] = df['Valor de Venda'].str.replace(',', '.').astype(float) # Mudando o Formato do Preço
```

## Resultados e Insights

### Perguntas Adicionais

## Integrantes
- [Cássio Ramos](https://github.com/NewKanvas)
- [Hudson Cesar](https://github.com/Hudsoncesar)
- [Arthur Lorran](link)
- [Xavier Flor](link)
- [Drielli Almeida](link)

**Link do Trello:** [Projeto 4 no Trello](https://trello.com/b/BnXV99YU/projeto-4)

---

## Status
![GitHub Repo Size](https://img.shields.io/github/repo-size/NewKanvas/Projeto-4?style=for-the-badge&logo=github)
![GitHub last commit](https://img.shields.io/github/last-commit/NewKanvas/Projeto-4?style=for-the-badge&logo=git)
[![Licence](https://img.shields.io/github/license/NewKanvas/Projeto-4?style=for-the-badge)](./LICENSE)
![Downloads](https://img.shields.io/github/downloads/NewKanvas/Projeto-4/total?style=for-the-badge)
![Forks](https://img.shields.io/github/forks/NewKanvas/Projeto-4?style=for-the-badge)
![Watchers](https://img.shields.io/github/watchers/NewKanvas/Projeto-4?style=for-the-badge)
![Stars](https://img.shields.io/github/stars/NewKanvas/Projeto-4?style=for-the-badge)
![Issues](https://img.shields.io/github/issues/NewKanvas/Projeto-4?style=for-the-badge)

---
