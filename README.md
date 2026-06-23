# 📊 Projeto DataView — Pipeline de Engenharia e Análise de Dados

> **Status do Projeto:** `CONCLUÍDO 🚀`

[![Python Version](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-orange.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/Library-NumPy-darkblue.svg)](https://numpy.org/)
[![PEP8](https://img.shields.io/badge/Style_Guide-PEP_8-green.svg)](https://peps.python.org/pep-0008/)

Este repositório contém o desenvolvimento completo do **DataView**, um pipeline automatizado de ponta a ponta focado no ecossistema de e-commerce brasileiro (inspirado nos padrões de dados da *Olist*).

O objetivo principal do sistema foi simular uma base bruta com falhas sistêmicas estruturais, aplicar um processo defensivo de higienização de dados, extrair inteligência estatística e consolidar relatórios analíticos prontos para a tomada de decisão.

---

# 🏗️ Estrutura Organizacional do Repositório

O projeto segue estritamente a arquitetura de diretórios recomendada pelas boas práticas de mercado para projetos de dados, garantindo o desacoplamento entre dados brutos, processados e outputs analíticos:

```text
Projeto/
├── data/                       # Governança de dados e ciclo de vida
│   ├── raw/                    # Massa de dados bruta e original (com inconsistências)
│   ├── processed/
│   │   ├── v1_com_outliers/    # Base higienizada preservando a dispersão original
│   │   └── v2_outliers_tratado/# Base com ruídos e outliers estatísticos isolados
│   └── final/                  # Dataset consolidado e enriquecido (Base de Produção)
├── notebooks/                  # Scripts principais do pipeline (.py/.ipynb)
├── outputs/                    # Relatórios estruturados (CSV e JSON)
│   └── graficos/               # Visualizações geradas automaticamente (PNG)
└── README.md                   # Documentação do projeto
```

---

# 🛠️ Tecnologias e Configurações Requeridas

O ambiente de desenvolvimento foi projetado para rodar de forma nativa e sem configurações adicionais em ecossistemas como o Google Colab, ou localmente em qualquer máquina com Python 3 instalado.

## Bibliotecas Utilizadas

- **Pandas**
  - Ingestão, manipulação matricial, engenharia de atributos e agregações estruturadas.

- **NumPy**
  - Computação matemática vetorizada de alta performance e broadcasting estatístico.

- **Matplotlib & Seaborn**
  - Geração de gráficos, mapas de distribuição e análise visual descritiva.

- **Regex (re)**
  - Expressões regulares aplicadas na limpeza fina e padronização de strings.

---

## Configuração de Execução Local

Caso queira reproduzir o pipeline em sua máquina, instale as dependências executando:

```bash
pip install pandas numpy matplotlib seaborn
```

---

# 📈 Detalhamento Técnico do Pipeline

O script principal executa, de forma linear e defensiva, os 12 Requisitos Funcionais (RFs), divididos em quatro grandes fases.

---

## 1️⃣ Ingestão e Engenharia Defensiva (RF01 ao RF04)

### Simulação de Inconsistências

- Strings com espaços duplicados;
- Registros nulos em chaves primárias;
- Datas corrompidas;
- Preços zerados.

### Higienização Avançada

- Limpeza via Expressões Regulares (Regex);
- Tratamento de dados faltantes;
- Conversão de tipos (`float`, `int`, `datetime`).

### Isolamento de Versões (IQR)

Aplicação da metodologia do Intervalo Interquartil (IQR) para identificar dispersões severas de quantidade e receita.

Criação das versões:

- **V1:** Base com outliers.
- **V2:** Base com outliers tratados.

---

## 2️⃣ Feature Engineering e Agregações (RF05 ao RF07)

### Vetorização Financeira

Criação de métricas utilizando o método `np.select()` para classificação por faixas de valor.

### Agregações Nomeadas

Uso intensivo de:

- `groupby()`
- Agregações nomeadas
- Ordenações lógicas

### Segmentação Estratégica

Classificação dos clientes em:

- 🥇 Ouro
- 🥈 Prata
- 🥉 Bronze

Utilizando funções de ordem superior e callbacks com `lambda`.

---

## 3️⃣ Computação Científica e Visualização (RF08 e RF09)

### Broadcasting NumPy

Conversão de DataFrames para arrays puros do NumPy para cálculo otimizado de:

- Média
- Mediana
- Desvio padrão
- Percentil 25 (P25)
- Percentil 75 (P75)

### Relatórios Visuais

Exportação automática de três gráficos:

#### 📈 Evolução Temporal

Linha de tendência da receita mensal.

#### 📊 Market Share

Ranking das categorias mais relevantes do e-commerce.

#### 📦 Análise de Dispersão

Boxplot mostrando o comportamento de compras por região brasileira.

---

## 4️⃣ Persistência e Auditoria (RF10 ao RF12)

### Exportação Multiformato

Geração automática de:

- `.csv`
- `.json`

Com codificação:

```text
utf-8-sig
```

Garantindo compatibilidade com Excel e sistemas externos.

### Auditoria Cruzada

Rotina de validação que:

- Lê os arquivos exportados;
- Compara métricas persistidas;
- Garante integridade matemática dos resultados.

---

# 🌟 Boas Práticas e Qualidade de Software

## Conformidade PEP 8

Todo o código foi desenvolvido seguindo:

- Importações centralizadas;
- Comentários por blocos;
- Padrões de nomenclatura limpos;
- Princípios de Clean Code.

---

## Tratamento de Exibição

Configuração global:

```python
pd.options.display.float_format
```

Permitindo:

- Exibição com duas casas decimais;
- Padrão brasileiro de formatação;
- Preservação do tipo numérico `float`.

---

## Régua de Caracteres (Ruler)

Desenvolvimento orientado ao limite de:

```text
79–80 caracteres por linha
```

Com objetivo de:

- Facilitar revisões de código;
- Melhorar leitura em Split Screen;
- Evitar rolagem horizontal.

---

# 🔮 Próximos Passos (Plano de Escalabilidade)

## 🗄️ Modelagem Relacional SQL

Migrar a coluna consolidada `produto_categoria` para uma modelagem dimensional composta por:

- `dim_produtos`
- `dim_categorias`

Relacionadas através de chaves estrangeiras (FK).

---

## ⚙️ Orquestração de Fluxo (DAGs)

Desacoplar funções lineares e utilizar ferramentas como:

- Apache Airflow

Permitindo:

- Controle de falhas;
- Retentativas automáticas;
- Paralelismo.

---

## ☁️ Persistência em Nuvem (Data Lake)

Substituir o armazenamento local por soluções em nuvem como:

- Amazon S3
- Google Cloud Storage

Com particionamento físico:

```text
ano/
└── mes/
    └── dia/
```

---

# 🚀 Autor

Projeto desenvolvido como exercício de Engenharia e Análise de Dados, contemplando conceitos de:

- Engenharia de Dados
- Data Cleaning
- Feature Engineering
- Estatística Aplicada
- NumPy
- Pandas
- Visualização de Dados
- Boas Práticas de Software
- PEP 8
- Clean Code
