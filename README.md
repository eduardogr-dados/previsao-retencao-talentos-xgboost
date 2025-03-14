# Previsão de Rotatividade de Funcionários usando XGBoost na Salifort Motors

## Visão Geral do Projeto
Este projeto aborda a alta rotatividade de funcionários na Salifort Motors, uma fabricante fictícia de veículos de energia alternativa. Utilizando o conjunto de dados "HR_comma_sep.csv" do Kaggle, que contém informações como nível de satisfação, número de projetos e horas trabalhadas, foi desenvolvido um modelo preditivo para identificar colaboradores em risco de deixar a empresa. O modelo XGBoost alcançou um recall de 93,72% e uma precisão de 90,31%, oferecendo insights acionáveis para reduzir custos e melhorar a retenção de talentos.

## Entendimento do Negócio
A equipe de liderança sênior e o departamento de Recursos Humanos (RH) da Salifort Motors são as principais partes interessadas neste projeto. Eles enfrentam o desafio de uma alta taxa de rotatividade, que gera custos significativos em recrutamento, treinamento e perda de expertise. O objetivo foi criar um modelo que previsse quais funcionários poderiam sair e identificar os fatores que impulsionam essa decisão, permitindo estratégias proativas de retenção e fortalecimento da cultura organizacional.

## Compreensão dos Dados
Os dados foram extraídos do conjunto "HR_comma_sep.csv" ([Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction)), contendo 11.991 registros únicos de funcionários após remoção de duplicatas. As variáveis incluem:

- `satisfaction_level`: Nível de satisfação autorreferido [0-1].
- `number_of_projects`: Quantidade de projetos atribuídos.
- `average_monthly_hours`: Média de horas mensais trabalhadas.
- `tenure`: Tempo de empresa em anos.
- `employee_left`: Indicador de saída (variável-alvo).

Limitações incluem a ausência de informações sobre feedback de liderança ou clima organizacional e possíveis vieses em dados autorreferidos.

## Modelagem e Avaliação
Dois modelos de aprendizado de máquina foram testados: Random Forest e XGBoost, ambos otimizados via GridSearchCV com foco no recall, devido ao alto custo de falsos negativos. Os resultados no conjunto de teste foram:

- **Random Forest**:
  - Recall: ~90%
  - Accuracy: >98%
- **XGBoost** (modelo selecionado):
  - Recall: 93,72%
  - Precision: 90,31%
  - F1-Score: 91,98%
  - Accuracy: 97,29%

O XGBoost destacou-se pelo desempenho superior. Features como `workload_risk` (risco de sobrecarga/subutilização), `satisfaction_level` e `tenure` foram os principais preditores, confirmando insights da análise exploratória.

## Conclusão
### Recomendações
- **Gerenciar a alocação de projetos**: Evitar extremos (≤2 ou ≥6 projetos) para reduzir riscos de saída de funcionários.
- **Focar em engajamento**: Implementar planos de carreira e feedback contínuo, especialmente para funcionários com mais de 3 anos sem promoção.
- **Implementar o modelo**: Integrar o XGBoost em sistemas de RH para monitoramento em tempo real.
- **Melhorar dados**: Coletar variáveis adicionais (ex.: clima organizacional) para análises futuras.
- **Monitorar ética**: Auditar o modelo para evitar vieses e garantir privacidade.

### Próximas Etapas
- Validar o modelo em produção com dados em tempo real.
- Desenvolver um dashboard interativo para o RH.
- Refinar hiperparâmetros com técnicas como Randomized Search e explorar interpretabilidade com SHAP values.

Este projeto oferece uma solução para a Salifort Motors, combinando análise preditiva e recomendações estratégicas para aumentar a retenção e otimizar recursos.


