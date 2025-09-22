# Hackathon Forecast Big Data 2025

## Objetivo
Prever a demanda semanal de cada PDV × Produto (SKU) para as 5 semanas de janeiro/2023, utilizando os dados de 2022 como histórico.

---

## Estrutura do Repositório
hackathon-forecast-2025/
├─ src/ # scripts principais da solução
│ └─ desafio_bigdata.py
├─ submissions/
│ └─ submissao_jan2023.csv
├─ README.md # este documento
└─ requirements.txt # dependências do projeto

yaml
Copiar código

- `src/` → código-fonte da pipeline (leitura, features, treino e previsão).  
- `submissions/` → arquivo final enviado à plataforma (`submissao_jan2023.csv`).  
- `requirements.txt` → bibliotecas necessárias para rodar o projeto.  

---

## Tecnologias Utilizadas
- Python 3.10+
- Polars
- LightGBM
- Optuna
- scikit-learn
- Outras dependências listadas em `requirements.txt`

---

## Como Reproduzir
1. Clone o repositório:
   ```bash
   git clone https://github.com/<seu-usuario>/hackathon-forecast-2025.git
   cd hackathon-forecast-2025
Crie um ambiente virtual e instale as dependências:

bash
Copiar código
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

pip install -r requirements.txt
Execute o script principal:

bash
Copiar código
python src/desafio_bigdata.py
O arquivo de submissão será gerado em:

bash
Copiar código
submissions/submissao_jan2023.csv
Formato da Submissão
O arquivo submissao_jan2023.csv segue o formato exigido pela competição:

Separador: ;

Encoding: UTF-8

Colunas:

semana (1 a 5)

pdv (inteiro)

produto (inteiro)

quantidade (inteiro, arredondado e ≥0)

Exemplo:

Copiar código
semana;pdv;produto;quantidade
1;1023;123;120
2;1045;234;85
3;1023;456;110
Equipe
Luis Fernando Denardi Lorenzetti

Observações
O repositório inclui tanto o código quanto a submissão final.

A pipeline segue a abordagem Hurdle Model (classificação + regressão), com calibração isotônica, cutoff τ* e priors hierárquicos.

javascript
Copiar código
