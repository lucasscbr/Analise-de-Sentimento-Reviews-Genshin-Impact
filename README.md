# Análise de Sentimentos de Reviews do Genshin Impact

## Descrição

Este projeto utiliza técnicas de aprendizado de máquina e processamento de linguagem natural (NLP) para realizar uma análise de sentimentos em avaliações do jogo **Genshin Impact** coletadas da Google Play Store.
O objetivo do projeto é classificar os sentimentos das avaliações em três categorias: **positivo**, **negativo** e **neutro**. Para isso, são utilizadas diversas etapas, desde a coleta e pré-processamento dos dados até o treinamento e avaliação de modelos de classificação.

## Tecnologias e Bibliotecas Utilizadas
- **Python**
- **Google Play Scraper**: Coleta de avaliações da loja Google Play.
- **NLTK e SpaCy**: Tokenização, lematização e remoção de palavras irrelevantes.
- **Scikit-learn**: Modelos de aprendizado de máquina, vetorização de textos e avaliação de métricas.
- **Transformers (Hugging Face)**: Fine-tuning de modelos BERT para classificação de sentimentos.
- **SMOTE (imbalanced-learn)**: Balanceamento de classes para reduzir o impacto do desbalanceamento nos dados.
- **Matplotlib e Seaborn**: Visualização de dados.

## Estrutura do Projeto
1. **Coleta de Dados**:
   - As avaliações são coletadas usando `google_play_scraper`.
   - Os dados incluem texto das reviews e notas (1 a 5 estrelas).

2. **Pré-processamento**:
   - Remoção de acentos, pontuações e palavras irrelevantes (*stopwords*).
   - Tokenização e lematização dos textos.
   - Mapeamento das notas para sentimentos:
     - 1 e 2 estrelas: **Negativo**.
     - 3 estrelas: **Neutro**.
     - 4 e 5 estrelas: **Positivo**.
    
3. **Análise Exploratória de Dados (EDA)**:
   - Análise de desbalanceamento de classes.
   - Distribuição do tamanho das avaliações.
   - Palavras mais frequentes.
  
4. **Modelagem**:
   - **Modelo SVM**:
     - Utilização de `CountVectorizer` para vetorização de texto.
     - Aplicação de SMOTE para balanceamento das classes.
   - **Modelo BERT**:
     - Fine-tuning com `Hugging Face Transformers`.
     - Utilização de pesos balanceados para lidar com o desbalanceamento.

5. **Avaliação de Modelos**:
   - Métricas utilizadas:
     - **F1-score** (principal métrica).
     - **Precisão**.
     - **Acurácia**.
   - Comparação de desempenho entre os modelos SVM e BERT.
