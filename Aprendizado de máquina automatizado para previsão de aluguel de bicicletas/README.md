# Aprendizado de máquina automatizado para previsão de aluguel de bicicletas

Para trabalhar no machine learn é essencial que você possua um workspace e esta é a tarefa inicial, criar o seu workspace para assim poder criar o seu trabalho automatizado.
Seguindo o roteiro que está no caminho https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html


__*Configurando um recurso Azure Machine Learning*__
---

<p align="center"><img src="./DIO.png" width="500"></p>
 

 

 

__*Depois que nosso workspace estiver pronto temos que entrar no ML studio para criar um "novo treinamento de ML automatizado".*__


 


 
Carregando a base  informada para  para ser a base do do ativo para o treinamento
Link da base:  https://aka.ms/bike-rentals  
	
 
__*Configure os parâmetros do JOB de treinamento: *__
Tipo de tarefa; Regressão
Métrica primária: Erro de quadrado de média de raiz normalizado
Explicar o melhor modeloDesabilitado
Modelos permitidos: LightGBM,RandomForest
Modelos bloqueados:TensorFlowDNN,TensorFlowLinearRegressor
Número de validações cruzadas: --
Aprendizado profundo: Desabilitado
Critério de saída: Tempo de treinamento (horas)0.25
Tipo de validação: Divisão de validação de treinamento
Iteração simultânea máxima:3

 

 
 
__*Após enviar seu trabalho, em cerca de 15 minutos, estará pronto para execução.*__
 
 

 
__*Treinamento Concluido*__
 

__*Histórico de execução*__
---


 __*Testando o modelo*__
Na página do modelo, clique na aba "Pontos de extremidade". Em seguida, acessei a aba "Testar".
Para o teste, foi o json abaixo confor mês no exemplo do site da microsoft:
<p align="center">
{
	
  "input_data": {
  
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
  }
}

</p>
A previsão gerada foi: 361.95

---

__*Validando a integridade do treinamento do melhor teste que foi neste caso o wheat_caryon*__
__*Analisando algumas  Metricas *__
 

__*Previsto vs Realizado*__

Este gráfico avalia a precisão e a confiabilidade de um modelo de aprendizado de máquina. Ele ajuda os usuários a identificar discrepâncias entre as previsões do modelo e os valores reais, permitindo ajustes e melhorias no modelo, se necessário.
 
__*Residuals Histogram*__

Esse gráfico faz análise de um modelo de aprendizado de máquina para avaliar a qualidade do ajuste do modelo aos dados de treinamento. Ele fornece insights sobre como os erros do modelo estão distribuídos e se o modelo está capturando adequadamente a variabilidade nos dados.



