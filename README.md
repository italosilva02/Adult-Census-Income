# 📊 Adult Census Income | Análise Demográfica e Previsão de Renda

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C4C4C?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-success?style=for-the-badge)

> Análise de dados desenvolvida no Power BI com integração em Python (Matplotlib e Seaborn) para identificar padrões demográficos associados a rendas superiores a $50K anuais. O projeto transforma o dataset clássico do Census Bureau em inteligência de negócios, analisando o peso estatístico de fatores como escolaridade, idade, carga horária semanal, estado civil e ocupação na probabilidade de alta renda.

---

## 📊 Acesse o Dashboard Interativo

Para navegar pelas páginas, interagir com os filtros e explorar os gráficos gerados via script Python dinamicamente, acesse a versão publicada no Power BI Web:

[![Acessar Relatório Power BI](https://img.shields.io/badge/Visualizar_Dashboard_Interativo-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiYWE5NzFiYzgtYTNhMy00NWNiLTllOWYtOGM3MjNlYmU2ZjI1IiwidCI6IjkwN2IxZDhiLTE2ZTEtNDZiZi05ODczLTI3MjNmNTlmODcwYSJ9)

---

## 💡 Principais Insights Analíticos

A exploração da base de dados e a integração com scripts estatísticos revelaram padrões estruturais determinantes para a classificação de renda:

* 🎓 **Educação é o principal impulsionador de renda:** Profissionais com titulação de Doutorado (`Doctorate`) e formação técnica (`Prof-school`) lideram as estatísticas absolutas, com **75%** de probabilidade de superar os $50K anuais.

* 💼 **Nível hierárquico define o teto de ganhos:** Cargos de nível executivo e gerencial (`Exec-managerial`) concentram a maior proporção de alta renda. No extremo oposto, serviços domésticos (`Priv-house-serv`) registram apenas **1,4%** de retenção na faixa de alta renda.

* 📈 **Pico de rentabilidade na maturidade:** A análise de agrupamento (qcut) em eixo duplo demonstrou que a probabilidade de alta renda cresce de forma acentuada a partir dos 25 anos, atingindo seu **ápice estatístico próximo aos 50 anos**, iniciando um declínio natural nas faixas etárias subsequentes.

* ⏱️ **Jornada de trabalho tem limite de impacto:** O aumento das horas trabalhadas por semana (`horas_por_semana`) eleva a probabilidade de ganhos superiores a $50K, mas a matriz de correlação mostra que esse impacto se estabiliza e apresenta retornos marginais decrescentes em jornadas extremas (acima de 60 horas).

* 👨‍👩‍👧 **Estrutura familiar forte correlaciona-se com estabilidade financeira:** Grupos categorizados como esposas (`Wife`, 49%) e maridos (`Husband`, 46%) apresentam taxas de alta renda substancialmente maiores do que indivíduos fora de núcleos familiares (`Not-in-family`, 11%) ou solteiros (`Unmarried`, 7%).

---

## 📈 Resumo de KPIs

| Métrica | Valor | Métrica | Valor |
|---|---:|---|---:|
| 🎯 **Média de Alta Renda (>50K)** | 25,0% | 🎂 **Idade Média da População** | 38,44 anos |
| 🎓 **Maior Retorno (Escolaridade)** | Doctorate (75%) | 💼 **Maior Retorno (Ocupação)** | Exec-managerial |
| 📉 **Menor Retorno (Ocupação)** | Priv-house-serv (1,4%) | 🤝 **Base Familiar (Wife/Husband)** | ~47,5% |

---

## ⚙️ Arquitetura do Modelo Semântico

O projeto foi estruturado em um modelo híbrido, combinando transformações nativas (Power Query / DAX) com um motor de visualização em Python injetado diretamente nos visuais do Power BI.

Essa arquitetura foi escolhida para contornar as limitações visuais nativas, permitindo a renderização de mapas de calor analíticos e gráficos de eixo duplo complexos diretamente sobre o contexto filtrado pelo usuário.

```mermaid
graph TD

    A[Adult Census Income Dataset] --> B[Power Query ETL]
    
    B --> C[Tratamento de Nulos e Duplicatas]
    B --> D[Transformação Target: Renda Binária]
    
    D --> E[Modelo de Dados Power BI]
    D --> F[Motor de Visualização Python]
    
    E --> G[Medidas DAX: Médias e Contagens]
    
    F --> H[Heatmap: Matriz de Correlação]
    F --> I[Heatmap: Médias Numéricas por Renda]
    F --> J[Dual-Axis: Prop. e Frequência por Idade]
    F --> K[Dual-Axis: Prop. e Frequência por Horas]
