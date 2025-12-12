#1. Introdução
Este projeto consiste no desenvolvimento de um Modelo Preditivo de Risco Cardíaco baseado em aprendizado supervisionado de Classificação Binária. O objetivo é fornecer uma Ferramenta de Apoio à Decisão Clínica (CDSS) capaz de identificar pacientes de alto risco a partir de dados clínicos e demográficos não invasivos.


2. Metodologia e Pipeline
O trabalho seguiu um pipeline rigoroso, destacando-se pela abordagem clinicamente fundamentada ao tratamento dos dados.

<img width="649" height="490" alt="image" src="https://github.com/user-attachments/assets/b16dc295-047d-4ebc-8846-fe712ffecaf9" />


3. Modelagem e ResultadosForam comparados cinco algoritmos de classificação: Regressão Logística, Random Forest, SVM, KNN e Gradient Boosting. A otimização foi feita via Grid Search com k=5 Stratified K-Fold.
  3.1.Métricas de Avaliação 
  A métrica mais crítica (Recall) foi priorizada para minimizar Falsos Negativos (FN), que representam o maior risco clínico (doente classificado como saudável).

  3.2.Comparação de Desempenho no Teste
  <img width="625" height="324" alt="image" src="https://github.com/user-attachments/assets/3fe85266-1587-483a-98c5-92db48556df5" />

O Gradient Boosting foi o modelo selecionado, pois apresentou o melhor equilíbrio (F1-Score) e o Recall máximo, sendo o mais consistente globalmente.

3.3. Interpretabilidade (Importância das Features)
O modelo Gradient Boosting validou os achados clínicos, confirmando que as variáveis de maior peso no risco são:

cp_asymptomatic: Dor torácica assintomática (0.2821)
chol: Colesterol sérico (0.1172)
age: Idade (0.1139)
oldpeak: Depressão do segmento ST induzida por exercício (0.1013)
thalch: Frequência cardíaca máxima atingida (0.0841)

4. Instruções de Uso
Para replicar os experimentos e rodar o modelo:

4.1. Dependências
Instale as bibliotecas necessárias usando o requirements.txt:
pip install -r requirements.txt

4.2. Aquisição de Dados
O dataset original deve ser obtido via Kaggle. Você precisará de uma chave (kaggle.json). O notebook heart_disease_uci.ipynb executa o download e o pré-processamento, gerando o arquivo final: data/heart_disease_model_ready.csv.


4.3. Execução dos Experimentos
Execute os notebooks na ordem abaixo:

notebooks/heart_disease_uci.ipynb: Para confirmar a limpeza e o pré-processamento.

notebooks/etapa_2_ML.ipynb: Para treinar, otimizar e avaliar os modelos, e reproduzir a tabela de resultados e o gráfico de importância.
