
# Análise Temporal da Violência Sexual contra Meninas no Brasil (2011-2025)

## 📌 Sobre o Projeto
Este projeto analisa a série temporal da violência sexual contra meninas e adolescentes (0 a 17 anos) no Brasil, buscando identificar padrões, tendências e disparidades regionais. A violência contra a mulher é reconhecida como um problema de saúde pública e uma violação aos direitos humanos, exigindo análises que subsidiem políticas eficazes de prevenção e enfrentamento.

O estudo foca no período de **2011 a 2025**, utilizando modelos estatísticos avançados para compreender a escalada dos casos e o impacto de eventos externos, como a pandemia de COVID-19 e mudanças nos sistemas de registro.

## 🛠️ Tecnologias e Metodologia
O projeto foi desenvolvido em **R**, utilizando o ecossistema `fpp3` e o conceito de *tidy forecasting*.
*   **Manipulação de Dados:** `tidyverse`, `tsibble` e `janitor`.
*   **Análise Exploratória (EDA):** Decomposição STL, médias móveis e funções de autocorrelação (ACF).
*   **Modelagem Preditiva:** Modelos ARIMA (especificamente priorizando a diferenciação $d=1$ para capturar tendências de alta) e modelos ETS.
*   **Métricas de Acurácia:** Avaliação via MAE e MAPE para validar a eficácia das previsões em conjuntos de treino e teste.

## 📊 Principais Achados
*   **Perfil de Vulnerabilidade:** Mais de **60% dos casos** de violência sexual ocorrem contra meninas de **00 a 17 anos**. Meninas **pardas (42,3%)** e **brancas (33,3%)** são as vítimas mais frequentes.
*   **Disparidades Regionais:** Embora o Sudeste concentre o maior volume de casos (33,5%), a **região Norte** apresenta as maiores taxas de incidência específica para violência sexual, atingindo **35,4 casos por 100 mil habitantes** em 2022.
*   **Tendência de Alta:** Os dados revelam um crime em constante crescimento estrutural, com um pico significativo em 2019 e uma aceleração agressiva na região Sul entre 2017 e 2019.
*   **Impacto Pandêmico:** Houve uma queda visível nos registros em 2020, interpretada como **subnotificação** decorrente do isolamento social, e não como uma redução real na criminalidade.

## 📈 Desafios da Modelagem
Um dos destaques técnicos deste repositório é a decisão metodológica de ignorar testes de estacionariedade automáticos (que sugeriam $d=0$) em favor da **evidência visual de tendência de alta** ($d=1$) observada nas séries regionais.
*   **Instabilidade no Sul:** O modelo ARIMA automático apresentou um erro elevado (MAPE de 42%) na região Sul devido à mudança brusca na inclinação da série no final do período de treino, demonstrando a complexidade de prever fenômenos sociais em rápida escalada.

## 📂 Estrutura do Repositório
*   `data/`: Bases consolidadas unindo dados do SINAN, SINESP e projeções do IBGE/PNAD.
*   `scripts/`: Fluxo completo desde a limpeza (`clean_names`, `str_trim`) até a modelagem e diagnóstico de resíduos.
*   `plots/`: Visualizações de tendências suavizadas, decomposições e projeções futuras.

## 📖 Referências
*   Hyndman, R.J., & Athanasopoulos, G. (2021) *Forecasting: principles and practice*.
*   Mapa da Violência contra a Mulher (Senado Federal).
*   Estatuto da Criança e do Adolescente (ECA) e Lei Maria da Penha.

--- 

Este projeto contribui para os **Objetivos de Desenvolvimento Sustentável (ODS) 3 e 5** da ONU, promovendo saúde, bem-estar e igualdade de gênero através da ciência de dados.
