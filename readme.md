# **Machine Learning na Prática no Azure ML**

## Criando o modelo de previsão:
#### 📌 Antes de tudo [clique aqui](https://azure.microsoft.com/pt-br/free/search/?ef_id=_k_CjwKCAjw_e2wBhAEEiwAyFFFo3RE7HE2-y1etoQbR5ZCAMuisChiKRd4zrBUFLYWzX6sBgB0OCxusRoChoMQAvD_BwE_k_&OCID=AIDcmmzmnb0182_SEM__k_CjwKCAjw_e2wBhAEEiwAyFFFo3RE7HE2-y1etoQbR5ZCAMuisChiKRd4zrBUFLYWzX6sBgB0OCxusRoChoMQAvD_BwE_k_&gad_source=1&gclid=CjwKCAjw_e2wBhAEEiwAyFFFo3RE7HE2-y1etoQbR5ZCAMuisChiKRd4zrBUFLYWzX6sBgB0OCxusRoChoMQAvD_BwE) para criar a sua conta na Microsoft Azure. 


#

**1 -**  Primeiro procuramos o Azure Machine Learning na biblioteca de serviços da "Azure".

![alt text](Capturar001.PNG)
#
**2 -** Criamos um novo modelo.

![
](Capturar002.PNG)
#
**3 -** Inserção do nome do projeto, seleção da região e criação/escolha do resource group para manter o modelo.

![alt text](Capturar003.PNG)
#
**4 -** Após concluída a primeira estapa clicamos em "Go to resource"

![alt text](Capturar004.PNG)
#
**5 -** Clicamos em "Launch studio" 

![alt text](Capturar005.PNG)
#
**6 -**  Em seguida aparece a página de serviços da azure, porém precisamos finalizar as configurações do nosso modelo, logo clicamos em "all workspaces" e selecionamos o que foi criado.

![alt text](Capturar006.PNG)
![alt text](Capturar007.PNG)
#
**7 -** Entramos na aba de automatização e criamos uma nova, inserindo o "Job name" e o "New experiment name". Mais adiante foi selecionada a tarefa do tipo "regressão" e tipo "tabular".

![alt text](Capturar008.PNG)
![alt text](Capturar009.PNG)
![alt text](Capturar0010.PNG) 
![alt text](Capturar0011.PNG)
#
**8 -** Agora selecionamos o recurso de dados da web para inserir o link externo e definir a primeira linha como cabeçalho:

    https://aka.ms/bike-rentals

 
![alt text](Capturar0012.PNG) 
![alt text](Capturar0013.PNG) 
![alt text](Capturar0014.PNG) 
![alt text](Capturar0015.PNG)
![alt text](Capturar0016.PNG)
#

**9 -** Nesta etapa selecionamos o job criado selecionando o valor "rentals" como coluna alvo, adicionamos os modelos "RandomForest" e "LightGBM". Por fim as demais informações para finalizar:

    Max trials: 3
    Max concurrent trials: 3
    Max nodes: 3
    Metric score threshold: 0.085 (de modo que, se um modelo atingir uma pontuação métrica de erro quadrático médio normalizado de 0,085 ou menos o trabalho será encerrado)
    Timeout: 15
    Iteration timeout: 15
    Enable early termination: Selected  

![alt text](Capturar0017.PNG)
![alt text](Capturar0018.PNG) 
![alt text](Capturar0019.PNG) 
![alt text](Capturar0020.PNG) 
![alt text](Capturar0021.PNG)
![alt text](Capturar0022.PNG) 
#

**10 -** Após criado, clicando "Algorithm name" em "Best model summary" obtemos os detalhes e métricas de previsão.

![alt text](Capturar0023.PNG) 
![alt text](Capturar0024.PNG)
![alt text](Capturar0025.PNG)
#

**11 -** Para testar apenas acessar a aba "endpoint", colar o script .json e clicar em "test".
![alt text](Capturar0031-2.PNG)
Script .json utilizado:

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



#

![Microsoft Azure](https://img.shields.io/badge/MicrosoftAzure-000?style=for-the-badge&logo=MicrosoftAzure&logoColor=30A3DC)

![JSON](https://img.shields.io/badge/JSON-000?style=for-the-badge&logo=JSON&logoColor=30A3DC)
## 🔎 Links de apoio:
- [Serviços Azure](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html) 
- [ML Workspace](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)







