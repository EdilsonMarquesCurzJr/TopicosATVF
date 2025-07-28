# Instituto Federal do Maranhão (IFMA)  
**Curso:** Bacharelado em Sistemas de Informação  
**Disciplina:** Tópicos Avançados em Visualização de Dados  
**Professor:** Josenildo Costa Da Silva 
**Equipe:**  
- Edilson Marques  
- Gabriel Vinícius  
- Reinaldo Dias  
- Jorge Lucas  

---

# Relatório de Análise Exploratória de Dados (EDA)  
**Dataset utilizado:** [State of Data Brazil 2024/2025 – Data Hackers](https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-20242025/data)

---

## 1. Preparação dos Dados

O dataset original possuía centenas de colunas, sendo muitas derivadas de perguntas de múltipla escolha convertidas por one-hot encoding. A equipe fez uma **partição temática dos dados** em grupos funcionais, facilitando a visualização e manipulação.

- Utilizou-se o método `info()` para entender o tipo de dados e a existência de valores nulos.  
- Colunas irrelevantes, duplicadas ou com baixa variabilidade foram descartadas.  
- Criaram-se cópias dos subconjuntos com `df.copy()` para preservar o dataset original.

---

## 2. Tratamento de Valores Nulos

- Foi aplicada a verificação de nulos com `isna().sum()`.  
- As colunas com grande proporção de nulos foram eliminadas.  
- Em outras, os valores faltantes foram tratados com imputação por valores padrão ou mais frequentes.

---

## 3. Tratamento de Anomalias

- A distribuição de atributos numéricos como **idade** foi verificada por meio de boxplots e histogramas.  
- Utilizou-se `skew()` e `kurtosis()` para verificar assimetria e curtose.  
- Detectaram-se valores extremos (e.g., idades implausíveis) que foram filtrados ou ajustados.

---

## 4. Transformações e Codificações

- Variáveis qualitativas (ex: modelo de trabalho ideal) foram transformadas com codificação numérica para análises de correlação.  
- Foram criadas tabelas cruzadas com `pd.crosstab` e aplicadas transformações com `melt` ou `pivot`.  
- Garantiu-se que colunas numéricas representassem grandezas reais e não códigos.

---

## 5. Análise Exploratória de Dados

### Análise Univariada

- A maioria dos respondentes está entre 20 e 35 anos.  
- Há predominância de pessoas com pós-graduação.  
- A faixa salarial mais comum está entre R$ 4.000 e R$ 8.000 mensais.  
- São Paulo se destaca como a UF com maior número de respondentes.

### Análise Bivariada

- **Heatmap 1:** Correlação positiva (ainda que fraca) entre idade e preferência por modelo remoto de trabalho.  
- **Heatmap 2:** Concentração de profissionais com pós-graduação nas faixas salariais mais altas.  
- **Outros cruzamentos** mostraram como variáveis como nível profissional, escolaridade e localização afetam a remuneração e preferências de trabalho.

---

## 6. Principais Achados e Recomendações

- O mercado de dados mostra-se **inclusivo** em relação à formação, mas ainda privilegia quem possui **pós-graduação**.  
- **São Paulo** concentra as melhores oportunidades em termos de salário e vagas.  
- A valorização do **modelo remoto** é sutilmente maior entre os profissionais mais velhos.  
- Oportunidades de qualificação técnica podem elevar o perfil de entrada de profissionais iniciantes.

---
