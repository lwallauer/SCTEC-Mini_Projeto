# 📊 Projeto DataView — Pipeline de Engenharia e Análise de Dados
> **Status do Projeto:** `CONCLUÍDO 🚀`

[![Python Version](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-orange.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/Library-NumPy-darkblue.svg)](https://numpy.org/)
[![PEP8](https://img.shields.io/badge/Style_Guide-PEP_8-green.svg)](https://peps.python.org/pep-0008/)

Este repositório contém o desenvolvimento completo do **DataView**, um pipeline automatizado de ponta a ponta focado no ecossistema de e-commerce brasileiro (inspirado nos padrões de dados da *Olist*). O objetivo principal do sistema foi simular uma base bruta com falhas sistêmicas estruturais, aplicar um processo defensivo de higienização de dados, extrair inteligência estatística e consolidar relatórios analíticos prontos para a tomada de decisão.

---

## 🏗️ Estrutura Organizacional do Repositório

O projeto segue estritamente a arquitetura de diretórios recomendada pelas boas práticas de mercado para projetos de dados, garantindo o desacoplamento entre dados brutos, processados e outputs analíticos:

```text
Projeto/
├── data/                       # Governança de dados e ciclo de vida
│   ├── raw/                    # Massa de dados bruta e original (com inconsistências)
│   ├── processed/
│   │   ├── v1_com_outliers/    # Base higienizada preservando a dispersão original
│   │   └── v2_outliers_tratado/# Base com ruídos e outliers estatísticos isolados
│   └── final/                  # Dataset consolidado e enriquecido (Base de Produção)
├── notebooks/                  # Jupyter Notebooks ou scripts principais do pipeline (.py/.ipynb)
├── outputs/                    # Relatórios estruturados (CSVs e JSON)
│   └── graficos/               # Visualizações geradas automaticamente (PNGs)
└── README.md                   # Documentação do projeto (este arquivo)
