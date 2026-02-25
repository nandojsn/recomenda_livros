

# 📚 Sistema de Recomendação de Livros: Filtros de Alta Relevância![recording-ezgif com-optimize](https://github.com/user-attachments/assets/0d84baff-1616-4233-95ec-e846fd84f38a)


Este projeto foi desenvolvido como parte da minha migração de carreira da área educacional para a **Ciência de Dados**. O objetivo foi construir um motor de recomendação que une Processamento de Linguagem Natural (NLP) e rigor estatístico para sugerir leituras de alta qualidade.

<p align="center">
  <img src="https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen" alt="Status Concluído">
  <img src="https://img.shields.io/badge/Python-3.13-blue" alt="Python Version">
  <img src="https://img.shields.io/badge/Interface-Gradio-orange" alt="Interface Gradio">
</p>

## 🎯 O Problema
Sistemas de recomendação baseados apenas em similaridade textual podem sugerir itens com baixa aceitação do público ou poucos dados históricos. Como professor de Física, busquei aplicar filtros de relevância para garantir que as recomendações sejam não apenas parecidas com o livro base, mas também bem avaliadas pela comunidade.

## 🛠️ Tecnologias e Ferramentas
- **Ambiente:** Linux Mint
- **Linguagem:** Python 3.13
- **Bibliotecas:** - `Pandas`: Limpeza e manipulação de dados.
  - `Scikit-learn`: TF-IDF Vectorizer e Similaridade de Cosseno.
  - `Gradio`: Criação da interface web interativa.
- **Dataset:** [Goodreads Books](https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks) (via Kaggle).

## 🧠 Lógica do Projeto

### 1. Engenharia de Dados e Limpeza
O dataset original apresentava problemas de "parsing" em algumas linhas e espaços extras nos nomes das colunas.
- Implementei o tratamento de erros na leitura do CSV utilizando `on_bad_lines='skip'`.
- Realizei o *stripping* de espaços em branco nos nomes das colunas para garantir a integridade das consultas.
- Verifiquei a integridade dos dados, confirmando que as 11.123 linhas estavam devidamente preenchidas.

### 2. Processamento de Linguagem Natural (NLP)
Para calcular a semelhança entre os livros, utilizei a técnica **TF-IDF** para transformar metadados (Título, Autor e Editora) numa matriz numérica, ignorando *stopwords* do inglês.

### 3. Similaridade de Cosseno
A recomendação é baseada no cálculo matemático do cosseno do ângulo entre os vetores de cada livro:

$$\text{similarity} = \cos(\theta) = \frac{\mathbf{A} \cdot \mathbf{B}}{\|\mathbf{A}\| \|\mathbf{B}\|}$$

### 4. Filtros de Qualidade (Business Logic)
O diferencial deste motor é a camada de filtragem pós-processamento:
- **Nota Mínima:** Apenas livros com `average_rating` >= 4.0.
- **Volume de Dados:** Apenas livros com mais de 500 avaliações (`ratings_count`).


Desenvolvido por um entusiasta de Física e Ciência de Dados. [Meu LinkedIn](https://www.linkedin.com/in/fernando-nunes-b65945b1/)
