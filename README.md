
# Trabalhando com Machine Learning

Vou explicar nesse documento como criei um modelo de Machine Learning no Azure Machine Learning. O modelo deve prever o número esperado de aluguéis de bicicletas levando em consideração dia, mês, ano, estação e outras características meteorológicas.

### Primeiro passo: criar uma conta no portal Azure
Para utilizar o portal é necessário criar uma conta no site Azure:

[Azure](https://azure.microsoft.com/pt-br/)

### Segundo passo: configurando modelos e conjunto de dados
Segui o modelo disponibilizado em [Microsoft Learn](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html). 

Dentro do portal Azure, cliquei em "Criar Recurso" e procurei por "Azure Machine Learning".

![image](https://github.com/fustianly/LabIA-900/assets/160360567/226b19ad-633e-4f77-b249-4a749fb33309)

Os campos foram preenchidos de acordo com o modelo citado anteriormente. Após a criação do recurso, temos o link que nos direciona ao [Estúdio do Azure Machine Learning](https://ml.azure.com/). 

Criei um Novo Trabalho de ML Automatizado com as seguintes características:

**Nome do trabalho**: mslearn-bike-automl

**Novo nome do experimento**: mslearn-bike-rental

**Descrição**: Aprendizado de máquina automatizado para previsão de aluguel de bicicletas

**Tipo de tarefa**: Regressão

As outras configurações de tarefas e modelo de computação foram configuradas de acordo com [Microsoft Learn](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html). 

Após enviado o trabalho de treinamento, segui para o terceiro passo.

### Terceiro passo: análise e teste de modelo

Depois do trabalho de treinamento ter sido processado, o melhor modelo treinado foi avaliado. Segui as indicações do documento para implantar e testar o modelo.

![image](https://github.com/fustianly/LabIA-900/assets/160360567/b3eedac1-d1bb-46f4-bd6e-7342f7668205)

Na aba **Pontos de Extremidade**, cliquei no modelo gerado anteriormente e acessei a aba **Testar**. Inseri os dados disponibilizados no documento:

```
 {
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }
 ```
Obtendo o seguinte resultado: 

```
{
  "Results": [
    512.6031940332446
  ]
}
```
