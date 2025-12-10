Resumo do Projeto: Imputação Inteligente de Séries Temporais Meteorológicas
Este repositório contém o código-fonte e o pipeline de análise para o trabalho de conclusão sobre a Imputação de Dados Faltantes em Séries Temporais Meteorológicas Horárias.

🌟 Objetivo Principal
Avaliar e comparar a eficácia de diferentes metodologias de Machine Learning (ML), Deep Learning (DL) e modelos estatísticos para preencher lacunas sequenciais curtas (3 horas) em dados climáticos. O objetivo é desenvolver uma estratégia de imputação adaptativa e otimizada baseada na natureza das variáveis meteorológicas (contínuas vs. esparsas).

🛠️ Componentes do Código
O pipeline é estruturado em células modulares, cobrindo todo o fluxo de trabalho de ponta a ponta:

Setup e Imports (CÉLULA 1): Configuração do ambiente, instalação de bibliotecas essenciais (Pandas, NumPy, Scikit-learn, TensorFlow/Keras) e definição de funções utilitárias.

Preparação de Dados:

Carregamento: Funções para carregar e pré-processar dados horários da estação EMA A632 (INMET).

Engenharia de Features: Criação de features de lags (cria_dataset_lags) para fornecer ao modelo o contexto temporal necessário.

Simulação de Lacunas: Implementação da função simula_lacunas_seq_3 para criar e isolar lacunas sequenciais de teste.

Modelagem e Treinamento (TODOS_METODOS):

Contém as funções de imputação para cada metodologia (Random Forest, KNN, GBR, LSTM, e benchmarks).

O treinamento é encapsulado em funções que aceitam o período de treino e devolvem a imputação para o período de teste.

Validação Rigorosa (Rolling Origin): Implementação da estratégia de validação Rolling Origin, que simula um avanço no tempo usando múltiplas janelas de treino/teste para evitar data leakage e garantir a robustez das métricas.

Visualização e Análise (CÉLULA FINAL 4.0):

Geração de gráficos de zoom comparativos para as variáveis com melhor desempenho.

Otimização do gráfico para focar apenas no período da lacuna e sombreá-lo corretamente (lógica Lag-Aware), facilitando a comparação visual entre o valor real e as previsões de diferentes modelos.
