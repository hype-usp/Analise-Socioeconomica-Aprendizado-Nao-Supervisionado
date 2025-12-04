# Análise Socioeconômica: Aprendizado Não Supervisionado 🌍📊

> **Projeto desenvolvido pelo grupo de estudos Hype Data & AI - EACH USP**

Este repositório contém o desenvolvimento, na figura do notebook Jupyter, e os resultados do projeto "Análise Socioeconômica: Aprendizado Não Supervisionado". O objetivo principal foi investigar padrões globais de desenvolvimento humano utilizando técnicas de Machine Learning para segmentar países em perfis socioeconômicos distintos. Além disso, para além do notebook com os códigos trabalhados, neste respositório se encontram um Relatório Final com os trabalhos organizados e uma Apresentação com os principais insights. 

## 👥 Integrantes do Grupo
**Membros:**
* [Beatriz dos Santos Bento](https://github.com/beatriz7227)
* [Giovanna Antunes](https://github.com/gigi-antunes)
* [Gabriela Alcaide](https://github.com/Gabriela-Alcaide)
* [Jean Lucas Santanna de Almeida]()
* [Rafael Chagas Araujo](https://github.com/RafaelCA-USP)
---

## Objetivo

O objetivo central deste estudo é realizar uma análise socioeconômica global mediante a aplicação de técnicas de agrupamento de dados (clustering). O projeto visa categorizar as nações em perfis distintos de desenvolvimento humano e examinar as inter-relações entre saúde, educação, renda e demografia.

## 🗂️ Sobre os Dados

O estudo utiliza a base de dados do **Subnational Human Development Index (SHDI)**, fornecida pelo **Global Data Lab** (versão 2022).

* **Cobertura:** 187 países, período de 1990 a 2022.
* **Variáveis Principais:**
    * **Saúde:** Expectativa de vida ao nascer.
    * **Educação:** Anos médios de escolaridade e anos esperados de escolaridade.
    * **Renda:** Renda Nacional Bruta per capita.
    * **Gênero:** Dados desagregados para análise de disparidades.

---

## 🛠️ Metodologia

O projeto foi estruturado em etapas sequenciais para garantir a consistência das análises:

### 1. Tratamento e Pré-processamento
* **Limpeza:** Remoção de duplicatas e colunas irrelevantes.
* Tratamento de valores nulos.
* **Normalização:** Aplicação do `MinMaxScaler` (biblioteca `sklearn`) para ajustar todas as variáveis numéricas ao intervalo [0, 1].

### 2. Análise Exploratória
* **Matriz de Correlação:** Identificação de alta colinearidade entre os pilares do IDH (Saúde, Educação, Renda).
* **Visualização:** Uso de histogramas, box plots e outros tipos de plotagens para identificar padrões geográficos.
* **Análise das Medidas Descritivas:** Cálculo das principais medidas estatísticas para as variáveis numéricas do dataset.

### 3. Modelagem (Clustering)
Utilização do algoritmo **K-Means** para segmentação dos países.
* **Definição de K:** O Método do Cotovelo (*Elbow Method*) indicou $K=3$ como o número ideal de clusters.
* **Modelos Criados:**
    1.  **Modelo Base:** Pilares centrais (saúde, educação, renda, expectativa de vida).
    2.  **Modelo de Desigualdade:** Adição de IDH subnacional e média de escolaridade.
    3.  **Modelo de Gênero:** Inclusão de variáveis desagregadas por sexo.

### 4. Visualização e Redução de Dimensionalidade
Aplicação de **PCA (Principal Component Analysis)** para projetar os clusters em um gráfico de dispersão 2D, facilitando a interpretação visual da separação dos grupos.

---

## Principais Resultados

A segmentação resultou na identificação de perfis claros de desenvolvimento:

* **Cluster de Baixo Desenvolvimento:** Países com menores índices em saúde, educação e renda, associados a maiores médias de desigualdade interna.
* **Cluster de Alto Desenvolvimento:** Países com elevados padrões de vida e alta equidade de gênero.
* **Cluster de Médio Desenvolvimento:** Países em transição com índices intermediários.

**Conclusões Chave:**
1.  **Visão Sistêmica:** Saúde, educação e renda são interdependentes; dificilmente um país avança em apenas um pilar.
2.  **População:** O tamanho da população não atua como determinante linear do IDH.
3.  **Desigualdade:** O alto desenvolvimento está fortemente correlacionado com baixa desigualdade interna e maior equidade de gênero.

---

## 💻 Tecnologias Utilizadas

* **Linguagem:** Python
* **Ambiente:** Google Colab
* **Bibliotecas:**
    * `Pandas` e `NumPy` para manipulação de dados.
    * `Seaborn` e `Matplotlib` para visualização.
    * `Scikit-learn` para K-Means, PCA e pré-processamento.
