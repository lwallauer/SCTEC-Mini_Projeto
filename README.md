# 📊 Projeto DataView — Pipeline de Engenharia e Análise de Dados

> ![Status](https://img.shields.io/badge/Status-Concluído-success)🚀`

[![Python Version](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-orange.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/Library-NumPy-darkblue.svg)](https://numpy.org/)
[![PEP8](https://img.shields.io/badge/Style_Guide-PEP_8-green.svg)](https://peps.python.org/pep-0008/)

Este repositório contém o desenvolvimento completo do **DataView**, um pipeline automatizado de ponta a ponta focado no ecossistema de e-commerce brasileiro (inspirado nos padrões de dados da *Olist*).

O objetivo principal do sistema foi simular uma base bruta com falhas sistêmicas estruturais, aplicar um processo defensivo de higienização de dados, extrair inteligência estatística e consolidar relatórios analíticos prontos para a tomada de decisão.

---

# 📚 Sumário

- [🏗️ Estrutura do Projeto](#️-estrutura-organizacional-do-repositório)
- [⚙️ Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [🚀 Como Executar](#-como-executar)
- [🔄 Arquitetura do Pipeline](#-arquitetura-do-pipeline)
- [📈 Etapas do Pipeline](#-etapas-do-pipeline)
- [📊 Visualizações](#-visualizações)
- [🌟 Boas Práticas](#-boas-práticas-e-qualidade-de-software)
- [🔮 Próximos Passos](#-próximos-passos)
- [👨‍💻 Autor](#-autor)

---

# 🏗️ Estrutura Organizacional do Repositório

O projeto segue estritamente a arquitetura de diretórios recomendada pelas boas práticas de mercado para projetos de dados, garantindo o desacoplamento entre dados brutos, processados e outputs analíticos:

```text
Projeto/
├── data/
│   ├── raw/
│   ├── processed/
│   │   ├── v1_com_outliers/
│   │   └── v2_outliers_tratado/
│   └── final/
├── notebooks/
├── outputs/
│   ├── graficos/
│   ├── metricas_por_mes.csv
│   ├── segmentacao_clientes.csv
│   └── estatisticas_gerais.json
├── dataview.py
└── README.md
```

---

# ⚙️ Tecnologias Utilizadas

| Tecnologia | Finalidade |
|-------------|------------|
| Python 3.9+ | Linguagem principal |
| Pandas | Manipulação e análise de dados |
| NumPy | Computação científica e vetorização |
| Matplotlib | Visualizações |
| Seaborn | Visualizações estatísticas |
| Regex (re) | Limpeza e padronização de textos |
| JSON | Persistência de dados |
| CSV | Armazenamento tabular |

---

# 🚀 Como Executar

Clone o repositório:

```bash
git clone https://github.com/seu_usuario/dataview.git
```

Entre na pasta:

```bash
cd dataview
```

Instale as dependências:

```bash
pip install pandas numpy matplotlib seaborn
```

Execute o pipeline:

```bash
python dataview.py
```

---

# 🔄 Arquitetura do Pipeline

```text
Dados Brutos
      ↓
RF01 - Geração do Dataset
      ↓
RF02 - Auditoria Estrutural
      ↓
RF03 - Limpeza e Higienização
      ↓
RF04 - Tratamento de Outliers
      ↓
RF05 - Feature Engineering
      ↓
RF06 - Métricas Agregadas
      ↓
RF07 - Segmentação de Clientes
      ↓
RF08 - Estatísticas com NumPy
      ↓
RF09 - Visualizações
      ↓
RF10 - Funções Reutilizáveis
      ↓
RF11 - Exportação e Auditoria
      ↓
RF12 - Dataset Final
```

---

# 📈 Etapas do Pipeline

## RF01 — Geração de Dados Sintéticos

- Simulação do cenário de e-commerce;
- Injeção controlada de inconsistências;
- Dados inspirados no ecossistema Olist.

## RF02 — Auditoria Estrutural

- Tipos de dados;
- Valores ausentes;
- Estatísticas descritivas iniciais.

## RF03 — Limpeza e Higienização

- Tratamento de valores nulos;
- Regex para padronização de textos;
- Conversão de datas;
- Aplicação de regras de negócio.

## RF04 — Tratamento de Outliers

Aplicação do método estatístico IQR para obtenção de duas versões:

- V1 — Com Outliers;
- V2 — Sem Outliers.

## RF05 — Feature Engineering

Criação de:

- Receita total;
- Ano;
- Mês;
- Trimestre;
- Ano-Mês;
- Faixas de receita.

## RF06 — Métricas Agregadas

Agrupamentos por:

- Mês;
- Categoria;
- Região;
- Faixa de valor.

## RF07 — Segmentação de Clientes

Classificação em:

🥇 Ouro

🥈 Prata

🥉 Bronze

## RF08 — Estatísticas com NumPy

Cálculo de:

- Média;
- Mediana;
- Desvio padrão;
- Percentis;
- Participação percentual;
- Broadcasting.

## RF09 — Visualizações

Geração automática de:

- Gráfico de linha;
- Gráfico de barras;
- Boxplot.

## RF10 — Funções Reutilizáveis

Aplicação de:

- Higher-Order Functions;
- Callbacks;
- Expressões Lambda.

## RF11 — Exportação e Auditoria

Persistência em:

- CSV;
- JSON;

Validação automática da integridade dos arquivos.

## RF12 — Dataset Final

Consolidação da base de produção:

```text
data/final/vendas_final.csv
```

---

# 📊 Visualizações

## 📈 Receita Total por Mês

![Receita por Mês](outputs/graficos/receita_por_mes.png)

---

## 📊 Top Categorias por Receita

![Top Categorias](outputs/graficos/top_produtos.png)

---

## 📦 Distribuição de Receita por Região

![Distribuição por Região](outputs/graficos/dist_regiao.png)

# 🌟 Boas Práticas e Qualidade de Software

### ✔ Conformidade PEP 8

- Importações centralizadas;
- Nomenclaturas padronizadas;
- Código modular;
- Docstrings em todas as funções.

### ✔ Programação Defensiva

- Uso de `.copy()`;
- Tratamento de exceções;
- Auditoria dos dados.

### ✔ Clean Code

- Funções reutilizáveis;
- Separação por responsabilidade;
- Código legível.

### ✔ Vetorização

- Pandas;
- NumPy;
- Broadcasting.

---

# 🔮 Próximos Passos

## 🗄️ Modelagem Relacional SQL

Separação em dimensões:

- dim_produtos
- dim_categorias

Relacionadas por chaves estrangeiras.

---

## ⚙️ Orquestração

Integração com:

- Apache Airflow

Para:

- DAGs;
- Retentativas automáticas;
- Monitoramento do pipeline.

---

## ☁️ Data Lake

Persistência em:

- Amazon S3;
- Google Cloud Storage.

Com particionamento:

```text
ano/
└── mes/
    └── dia/
```

---

# 👨‍💻 Autor

Projeto desenvolvido como exercício de Engenharia e Análise de Dados, contemplando conceitos de:

- Engenharia de Dados;
- Data Cleaning;
- Feature Engineering;
- Estatística Aplicada;
- NumPy;
- Pandas;
- Visualização de Dados;
- Programação Defensiva;
- PEP 8;
- Clean Code.

---

## ⭐ Se este projeto foi útil, considere deixar uma estrela no repositório.
