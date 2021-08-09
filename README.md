# Projeto Previsão de UTI para Pacientes com Covid-19
 <img src="https://img.olhardigital.com.br/wp-content/uploads/2019/12/20191219064913-1207x450.jpg">

## Visão geral do projeto:

- 1. Introdução
- 2. Descrição dos Dados
- 3. Analise Exploratória
   - 3.1  Importação de Bibliotecas
   - 3.2. Carregamento dos Dados
   - 3.3. Preenchendo Dados Faltantes
   - 3.4. Levantamento de Hipóteses
   - 3.5. Análise
   - 3.6. Seleção de Dados para Previsão
   - 3.7. Análise (Parte 2)
   - 3.8. Conclusões
- 4. Desenvolvimento de Modelo Preditivo
   - 4.1. Importando bibliotecas
   - 4.2. Engenharia de recursos
   - 4.3. Separação dos dados
   - 4.4. Treinamento do Modelo
- 5. Conclusões
- 6. Referências

## 1. Introdução

Este projeto de ciência de dados tem como objetivo desenvolver um modelo preditivo para detectar<b> quais pacientes precisarão ser admitidos na UTI</b>, a partir dos dados clínicos individuais do histórico de pacientes atendidos com <b>COVID-19</b>. O dados que foram utilizados neste projeto estão disponilizados pelo <b>Hospital Sírio Libanês - São Paulo e Brasília</b> no Kaggle (plataforma de competição de ciência de dados muito conhecida). Este modelo apoiará o hospital na organização e otimização quanto à disponibilidade de leitos para pacientes com COVID-19. Desta forma, a remoção e transferência deste(a) paciente pode ser organizada antecipadamente, evitando a ruptura, e assim, ajudando a <b>salvar vidas</b>.

## 2. Descrição dos Dados

Conforme falado anteriormente, o dataset que utilizamos para desenvolvimento do modelo foram dados clinícos individualizados de pacientes atendidos com COVID-19, disponbilizado pelo <b>Hospital Sírio Libanês</b>. E podemos baixar no portal do Kaggle neste [link](https://www.kaggle.com/S%C3%ADrio-Libanes/covid19).

#### <b>Características dos Dados:</b>

- Informações demográficas do paciente (03 colunas)
- Doenças anteriores agrupadas de pacientes (09 colunas)
- Resultados de sangue (36 colunas)
- Sinais vitais (06 colunas)

## 3. Analise Exploratória
### Carregamento dos Dados
Analisamos  algumas informações estatísticas dos nossos dados, como <b> frequência (count), média (mean), desvio padrão (std), max, min e quartis</b>.

   #### - 3.3. Preenchendo Dados Faltantes
   
Utilizamos   ```heatmap``` do <b>Seaborn</b> e visualizamos os dados faltantes. Para resolver esse problema,  tratamos os dados contínuos já separados com `fillna` com   parâmetro method `bfill`, onde ele preenche a medida vazia anterior repetindo a medida posterior, e `ffill`, onde ele peenche a medida vazia posterior repetindo a medida anterior.
   
   #### - 3.4. Levantamento de Hipóteses
   
   <img src="https://media1.tenor.com/images/4c6187594727c6937f0ed9c4cbaf7249/tenor.gif?itemid=8949118">
   
Levantamos  algumas hipóteses de como a evolução do quadro clínico de pacientes – registrado nos exames laboratoriais e sinais vitais, coletados durante o período de    internação – influenciou na internação em UTI (ICU).

   - <b>Pessoas com mais idade tem mais tendência a ir para a UTI?</b>
   - <b>Qual grupo de risco é mais propenso?</b>
   - <b>Existe um genêro predominante de pacientes indo para a UTI?</b>
   - <b>Os resultados dos exames laboratoriais tem correlação com ida da pessoas para a UTI?</b
 
   #### - 3.5. Análise
 
 Analisamos as chances por: **Faixa Etária, Genêro e Grupos de Doenças de serem internadas na UTI no período das janelas.
 Também analisamos as correlações entre as variáveis, utilizando o médodo `corr` em nosso dataframe e plotando com `heatmap` e percebemos fortes correlações entre os variáveis expandidas.
 
   #### - 3.6. Seleção de Dados para Previsão

Nesta etapa, removemos todos os pacientes que foram **direto para a UTI na primeira janela**. Em seguida, criamos um método para buscar em **todas as janelas de que o paciente foi para a UTI e preenchemos com esta informação a linha da primeira **janela**. Como isso, selecionamos somente os IDs dos pacientes na **janela 0-2** e **ICU igual a 1**.
 
   #### - 3.7. Análise (Parte 2)
 
 Analisamos as chances por: Faixa Etária, Gênero e Grupos de Doenças de serem internadas na UTI por pacientes para repondermos as hipoteses levantadas.
 
   #### - 3.8. Conclusões
 
 Na conclusão, respondemos as hipóteses levantadas, através da análise exploratória.
 
### - 4. Desenvolvimento de Modelo Preditivo
   #### - 4.1. Importando bibliotecas
 
 Importamos as bibliotecas necessárias para desenvolvido do modelo preditivo.
 
   #### - 4.2. Engenharia de recursos
 
 utilizamos o LabelEncoder do sklearn, para transformar a variável categóriga AGE_PERCENTIL do tipo texto para o tipo numérico .
 
   #### - 4.3. Separação dos dados
 
 Separamos os dados em treino e teste com o médoto `train_test_split` do sklearn para o desenvolvimento do modelo preditivo.
 
   #### - 4.4. Treinamento do Modelo

Treinamos e testamos com 5 algoritmos de classificação: Regressão Logística (LogisticRegression), KNN (KNeighborsClassifier), Foresta Aleatória (RandomForestClassifier), Árvore de Decisão (DecisionTreeClassifier) e o Gradient Boosting (XGBClassifier). e analisamos as métricas, comparamos e analisamos qual o modelo trouxe melhores resultados para resolver o nosso problema. 
 
### - 5. Conclusões
 
 
