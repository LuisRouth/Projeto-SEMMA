# 🔄 Previsão de Churn - Framework SEMMA

Este repositório contém a aplicação prática do framework analítico **SEMMA** (Sample, Explore, Modify, Model, Assess) para o desenvolvimento de um motor de Machine Learning focado na previsão de Churn (evasão de usuários).

## 🎯 Objetivo
Desenvolver um modelo preditivo capaz de identificar usuários com alta probabilidade de cancelamento, isolando o ambiente de testes contra *data leakage* e validando o Retorno sobre o Investimento (ROI) matemático.

## 🛠️ Estrutura do Framework Aplicado

- **[S] Sample**: Divisão estratificada (80/20) garantindo a volumetria exata do evento de interesse. Isolamento temporal (*Out-of-Time*) da última safra para simulação de deploy.
- **[E] Explore**: Diagnóstico da saúde da base, auditoria de dados corrompidos e análise bivariada no isolamento da base de Treino.
- **[M] Modify**: Higienização e padronização matemática através de `Pipeline` e `ColumnTransformer` (Scikit-Learn).
- **[M] Model**: Treinamento de uma Random Forest otimizada via `GridSearchCV` com validação cruzada (`CV=3`).
- **[A] Assess**: Auditoria de estabilidade via Acurácia e Curva ROC AUC (Treino vs Teste vs OOT) e elaboração de relatórios de *Lift/Gains* de negócios.

## 🚀 Tecnologias e Bibliotecas
- Python 3
- Pandas & NumPy
- Matplotlib
- Scikit-Learn
- Jupyter Notebook

## 📁 Estrutura de Arquivos
- `semma_pipeline.ipynb`: Notebook com o racional analítico e engenharia do código.
- `data/`: Diretório contendo a Analytical Base Table (ABT). *(Omitido via .gitignore)*
- `models/`: Diretório de saída do artefato final em formato `.pkl`. *(Omitido via .gitignore)*
- `simulador_producao.ipynb`: Notebook auxiliar para carregar o modelo treinado (.pkl) e visualizar a simulação dos resultados gerados pelo framework.