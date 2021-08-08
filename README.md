# Predição do valor de aluguel de imóveis

##  🚀 Sobre
___

<br> Implementação dos modelos de Random Forest, XGBoost e Catboost para predizer o valor de aluguel de imóveis em cinco cidades brasileiras. </br>

## 💻 Instruções de Instalação
___

<br>Recomendo  bifurcar o repositório e cloná-lo localmente usando a função **git clone** no terminal. Instruções sobre como fazer isso podem ser acessadas [aqui](
https://docs.github.com/pt/github/getting-started-with-github/fork-a-repo).
</br>

``` bash
# Clonar repositório
git clone https://github.com/jluss0ll1/predicao-alugueis
```
Outra alternativa é clicar no botão verde "clone or download" neste repositório e então clicar em "Download ZIP". Em seguida, extrair o arquivo ZIP no local que você desejar editar ou executar o código.

## 💾 Ferramentas utilizadas

* Python
* Jupyter Notebook
* Pandas
* scikit-learn
* Random Forest
* XGBoost
* Catboost

## 🎫 Visão Geral do Projeto

<br> Os dados, após serem tratados no MySQL Workbench, são carregados utilizando a biblioteca Pandas como um dataframe com 13 colunas e 10691 linhas. A coluna com o estado é deletada pois já há informação sobre a cidade que o imóvel está localizada e o valor do seguro incêndio e do IPTU também são deletados por serem extremamente tendenciosos (correlação próxima à 1 com o valor do aluguel). A localização (cidade) é convertida em variáveis dummies para serem incluidos na regressão como valores discretos. A distribuição dos valores de aluguel não era normal, com uma longa cauda à direita, então apliquei transformação logaritmica para melhor distribuir os dados e evitar possíveis problemas de convergência. Para evitar multicolinariedade, foram criadas novas colunas para a razão entre o número de banheiros e o número de quartos no imóvel e a razão do número de garagens com o número de quartos, e as colunas antigas de número de andares e quantidade de vagas de garagem foram deletadas. </br>

<br> Os dados foram dividods em treino (75%) e teste (25%). As métricas de avaliação utilizadas foram Mean Absolute Error, Mean Squared Error, R² e Mean Absolute Scaled Error. Os métodos de regressão utilizados foram Random Forest, XGBoost e Catboost, sendo que Early Stopping foi aplicado nos dois últimos para evitar overfitting. Catbbost obteve o melhor desempenho, apesar de não ter sido significativamente maior que os outros dois modelos. O erro médio absoluto entre os valores reais e os valores previstos é BRL 1200. O tamanho da base de dados foi um limitador para a performance do modelo preditivo, pretendo analisar maiores posteriormente.</br> 

![image](https://user-images.githubusercontent.com/65292945/128636420-2860b115-bcfa-46d8-bb4f-210896e4933a.png)
