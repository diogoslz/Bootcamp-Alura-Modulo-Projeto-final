# Projeto Previsão de UTI para Pacientes com Covid-19
 <img src="https://img.olhardigital.com.br/wp-content/uploads/2019/12/20191219064913-1207x450.jpg">

## Visão geral do projeto:

- 1. Introdução
- 2. Descrição dos Dados
- 3. Analise Exploratória
   - 3.1 Importação de Bibliotecas
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

Este projeto de ciência de dados tem como objetivo desenvolver um modelo preditivo para detectar<b> quais pacientes precisarão ser admitidos na UTI</b>, a partir dos dados clínicos individuais do histórico de pacientes atendidos com <b>COVID-19</b>. O dados que serão utilizados neste projeto foram disponilizados pelo <b>Hospital Sírio Libanês - São Paulo e Brasília</b> no Kaggle (plataforma de competição de ciência de dados muito conhecida). Este modelo apoiará o hospital na organização e otimização quanto à disponibilidade de leitos para pacientes com COVID-19. Desta forma, a remoção e transferência deste(a) paciente pode ser organizada antecipadamente, evitando a ruptura, e assim, ajudando a <b>salvar vidas</b>.

## 2. Descrição dos Dados

Conforme falado anteriormente, o dataset que utilizaremos para desenvolvimento do modelo são dados clinícos individualizados de pacientes atendidos com COVID-19, disponbilizado pelo <b>Hospital Sírio Libanês</b>. E podemos baixar no portal do Kaggle neste [link](https://www.kaggle.com/S%C3%ADrio-Libanes/covid19).

#### <b>Características dos Dados:</b>

- Informações demográficas do paciente (03 colunas)
- Doenças anteriores agrupadas de pacientes (09 colunas)
- Resultados de sangue (36 colunas)
- Sinais vitais (06 colunas)

## 3. Analise Exploratória


<b>Informações demográficas do paciente (03 colunas):</b>
- <b>Idade Acima de 65 Anos (AGE_ABOVE65)</b>
- <b>Faixa Etária (AGE_PERCENTIL)</b>
- <b>[Genêro](https://www.kaggle.com/S%C3%ADrio-Libanes/covid19/discussion/164019) (GENDER)</b>
    0: Masculino
    1: Feminina

<b>Doenças anteriores agrupadas de pacientes (09 colunas):</b>
- <b>Grupo de Doenças 1 (DISEASE GROUPING 1)</b>
- <b>Grupo de Doenças 2 (DISEASE GROUPING 2)</b>
- <b>Grupo de Doenças 3 (DISEASE GROUPING 3)</b>
- <b>Grupo de Doenças 4 (DISEASE GROUPING 4)</b>
- <b>Grupo de Doenças 5 (DISEASE GROUPING 5)</b>
- <b>Grupo de Doenças 6 (DISEASE GROUPING 6)</b>
- <b>Hipertensão (HTN)</b>
- <b>Imunocomprometido (IMMUNOCOMPROMISED)</b>
- <b>Outros (OTHER)</b>

<b>Sinais vitais (6 colunas):</b> 
- <b>Saturação do Oxigênio (OXYGEN_SATURATION)</b>; 
- <b>Frequência Respiratória (RESPIRATORY_RATE)</b>;
- <b>Temperatura (TEMPERATURE)</b>;
- <b>Pressão Sistólica (BLOODPRESSURE_SISTOLIC);</b>
- <b>Pressão Diatolica (BLOODPRESSURE_DIASTOLIC);</b>.
- <b>Frequência Cardíaca (HEART_RATE);</b> 

<b>Exames laboratoriais (36 colunas):</b>

- <b>Glicose (GLUCOSE)</b>
- <b>Linfócitos (LINFOCITOS)</b>
- <b>PCR</b>
- <b>Creatinina (CREATININ)</b>
- ETC...
