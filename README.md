# Risco Default

A partir de uma base de dados dos clientes, queremos identificar quem são os bons e maus pagadores.

O trabalho está dividido em duas partes: análise descritiva e modelagem.

<p align='justify'>O primeiro ponto foi fazer uma análise detalhada e profunda da base de dados, de maneira a identificar alguns problemas e como tratá-los. Como problemas, há outliers, algumas variáveis possuem observações não muito condizentes com o que deveriam possuir, alguns valores como Nan's foram tratados, fiz o log de algumas variáveis, outras foram transformadas em dummies etc. Busquei também identificar a relação entre as variáveis com a variável-alvo, se o cliente pagou ou não o empréstimo, de forma a fazer alguns insights e ter ideia de quais variáveis podem ser relevantes. Tudo isso está mais detalhado no notebook.

<p align='justify'>Para a modelagem, como o dataset é desbalanceado, fiz três abordagens: sem balancear o dataset, multiplicando (smote) as linhas da variável-alvo que possuem menor ocorrência - nesse caso, o cliente que dá o default - de forma a balancear o dataset e, por fim, balanceando o dataset exluindo linhas (near miss) em que a variável-alvo teve maior ocorrência - clientes que pagaram o empréstimo. Em todos esses casos, rodei os seguintes modelos:

- Logistic Regression
- SVC
- K Neighbors Classifier
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier

<p align='justify'>Nesses primeiro modelos, não utilizei parâmetros. A partir das métrica Recall, selecionei os dois melhores, e em seguida fiz um GridSearchCV desses dois melhores com alguns parâmetros. Por fim, avaliei os resultados e escolhi o melhor em cada caso. Fiz isso com as três abordagem e por fim um comparativo entre elas. O método escolhido é o smote, uma vez que apresentou as métricas mais interessante. No notebook há mais detalhes, junto do meu raciocínio em cada caso.
