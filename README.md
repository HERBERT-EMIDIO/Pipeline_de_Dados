 
# Pipeline de Dados: Fusão de Empresas

Este projeto é uma implementação de um pipeline de dados desenvolvido durante o curso de Pipeline de Dados da Alura. O objetivo do projeto é processar e integrar dados de duas empresas que passaram por um processo de fusão.

## Tabela de Conteúdos

- [Introdução](#introdução)
- [Objetivos](#objetivos)
- [Arquitetura do Pipeline](#arquitetura-do-pipeline)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar](#como-executar)
- [Estrutura de Diretórios](#estrutura-de-diretórios)
- [Contribuições](#contribuições)
- [Licença](#licença)

## Introdução

A fusão de empresas é um processo complexo que envolve a integração de diversos sistemas e dados. Este projeto visa criar um pipeline de dados automatizado para integrar e processar os dados das duas empresas, garantindo a consistência e a qualidade dos dados.

## Objetivos

- Extrair dados de diferentes fontes (bancos de dados, arquivos CSV, APIs).
- Transformar os dados para unificação e limpeza.
- Carregar os dados transformados em um banco de dados centralizado.
- Garantir a integridade e a qualidade dos dados ao longo do processo.

## Arquitetura do Pipeline

![Arquitetura do Pipeline](docs/arquitetura_pipeline.png)

O pipeline de dados é composto pelas seguintes etapas:

1. **Extração**: Coleta de dados de múltiplas fontes.
2. **Transformação**: Limpeza, normalização e unificação dos dados.
3. **Carregamento**: Armazenamento dos dados transformados em um data warehouse.

## Tecnologias Utilizadas

- **Python**: Linguagem principal para a construção do pipeline.
- **Pandas**: Biblioteca para manipulação e análise de dados.
- **SQLAlchemy**: Biblioteca para integração com bancos de dados SQL.
- **Airflow**: Orquestração e automação do pipeline de dados.
- **PostgreSQL**: Banco de dados utilizado como data warehouse.

## Como Executar

### Pré-requisitos

- [Python 3.8+](https://www.python.org/downloads/)
- [PostgreSQL](https://www.postgresql.org/download/)
- [Airflow](https://airflow.apache.org/docs/apache-airflow/stable/installation/index.html)

### Instalação

1. Clone o repositório:

    ```sh
    git clone https://github.com/HERBERT-EMIDIO/Pipeline_de_Dados-.git
    cd Pipeline_de_Dados-
    ```

2. Crie e ative um ambiente virtual:

    ```sh
    python -m venv venv
    source venv/bin/activate  # No Windows use `venv\Scripts\activate`
    ```

3. Instale as dependências:

    ```sh
    pip install -r requirements.txt
    ```

4. Configure o Airflow:

    ```sh
    airflow db init
    airflow users create -u admin -p admin -r Admin -e admin@example.com -f Admin -l User
    ```

5. Inicie o servidor do Airflow:

    ```sh
    airflow webserver --port 8080
    airflow scheduler
    ```

6. Acesse o Airflow pelo navegador em `http://localhost:8080` e inicie o DAG do pipeline.

## Estrutura de Diretórios

```plaintext
.
├── dags
│   └── pipeline_dados.py
├── data
│   ├── empresa_a.csv
│   ├── empresa_b.csv
├── docs
│   └── arquitetura_pipeline.png
├── scripts
│   ├── extract.py
│   ├── transform.py
│   └── load.py
├── tests
│   ├── test_extract.py
│   ├── test_transform.py
│   └── test_load.py
├── .gitignore
├── README.md
└── requirements.txt
