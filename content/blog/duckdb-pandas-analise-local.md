+++
title = "DuckDB + pandas: analyze local sem servidor"
date = 2026-06-24
draft = false
tags = ["dados", "duckdb", "pandas", "python"]
weight = 3
+++

Quando o CSV tem 2GB e o `pd.read_csv` começa a soffrer, é hora de conhecer o **DuckDB**. Nesse post mostro o fluxo que uso pra análise local sem montar servidor nenhum.

## O problema

Você tem um arquivo grande. Carregar tudo no pandas derruba a RAM. Subir um Postgres só pra isso é overkill. A resposta do meio é o DuckDB: um banco analítico **embarcado**, que roda dentro do seu processo Python.

## O básico

```python
import duckdb
import pandas as pd

# Roda SQL direto em cima do CSV, sem carregar tudo na memória
df = duckdb.sql("""
    SELECT cliente, SUM(valor) AS total
    FROM 'vendas.csv'
    WHERE status = 'pago'
    GROUP BY cliente
    ORDER BY total DESC
    LIMIT 20
""").df()

print(df)
```

O DuckDB lê o CSV por trás, faz o GROUP BY em streaming, e te devolve só o resultado como DataFrame. RAM feliz.

## Por que tem funcionado pra mim

- **Sem servidor** — `pip install duckdb` e pronto
- **SQL padrão** — reaproveita o que você já sabe
- **Integra com pandas/Arrow/Parquet** — sem atrito
- **Rápido** — colunar, vetorizado, pensado pra analytics

## Quando ainda prefiro pandas

- Dados pequenos (megabytes) onde a verbosidade do SQL não se paga
- Operações muito específicas de índice/multindex
- Notebooks de exploração curta e interativa

## Resumo

DuckDB virou peça fixa do meu toolkit de dados. Não substitui pandas — **complementa**. CSV grande? DuckDB. Transformação relacional? DuckDB. Manipulação livre e exploratória? pandas.

Nos próximos posts entro em ETL, visualização e pegadinhas de modelagem que aparecem no caminho.
