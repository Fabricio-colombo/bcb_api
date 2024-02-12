# Brazilian Central Bank API

This repository contains Python scripts to interact with the Brazilian Central Bank API.

## Overview

The provided scripts demonstrate how to retrieve data from the Brazilian Central Bank API using Python's `requests` library and process it using `pandas`.

## Script 1: Single Request

```python
import requests
import pandas as pd

# Endpoint URL for the API
link = "https://olinda.bcb.gov.br/olinda/servico/mecir_dinheiro_em_circulacao/versao/v1/odata/informacoes_diarias?$top=10000&$orderby=Data%20desc&$format=json"

# Make a request to the API
requisicao = requests.get(link)
informacoes = requisicao.json()

# Convert the response to a DataFrame
tabela = pd.DataFrame(informacoes["value"])

# Display the DataFrame
display(tabela)
