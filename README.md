# SysPredict - Previsão de Falhas na Indústria 4.0

## Qual o problema que este software resolve?
Num parque fabril monitorizado por sensores, a quebra inesperada de equipamentos causa paragens drásticas na linha de produção, gerando enormes prejuízos. O **SysPredict** é um Pipeline Preditivo de Ciência de Dados construído para analisar a telemetria das máquinas (temperatura, rotação, torque e desgaste) e prever antecipadamente se uma avaria vai ocorrer (Falha = 1) ou se o funcionamento está normal (Falha = 0), permitindo que a manutenção aja antes da quebra.

## Técnicas e Tecnologias Utilizadas
* **Linguagem:** Python
* **Ambiente:** Google Colab / Jupyter Notebook
* **Análise e Limpeza de Dados:** `pandas`, `matplotlib`, `seaborn` (EDA, Imputação pela Mediana, Boxplots)
* **Engenharia de Recursos (Feature Engineering):** Criação da variável matemática `potencia` (Rotação RPM * Torque Nm).
* **Machine Learning:** `scikit-learn`
  * Prevenção de Data Leakage e divisão Treino/Teste (80/20).
  * Balanceamento de dados sintéticos com técnica **SMOTE** (`imbalanced-learn`).
  * Padronização de escala com **StandardScaler**.
  * Modelos classificadores avaliados: **K-Nearest Neighbors (KNN)** e **Árvore de Decisão (Decision Tree)**.

##Como executar o sistema
1. Clone este repositório para a sua máquina local.
2. Certifique-se de ter o Python instalado.
3. Instale as dependências listadas executando o comando no terminal: `pip install -r requirements.txt`
4. Abra o ficheiro Notebook (`.ipynb`) no Jupyter Notebook, VS Code ou Google Colab.
5. Execute as células sequencialmente. *(Nota: certifique-se de que o ficheiro `manutencao_preditiva.csv` está acessível no caminho relativo `/data/`).*

## Melhorias Futuras
* Testar algoritmos de *Ensemble* (como Random Forest ou XGBoost) para tentar aumentar ainda mais a precisão.
* Implementar um modelo de *Regressão* para tentar prever *quantas horas* faltam para a falha (RUL - Remaining Useful Life).
* Empacotar o modelo final numa API (usando FastAPI ou Flask) para que os sensores da fábrica possam consultar a Inteligência Artificial em tempo real.
