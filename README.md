# Wine Quality-Python
**a.** Como foi a definição da sua estratégia de modelagem? <br>

*Esse problema será tratado com um algoritmo supervisionado, pois conhecemos a variável resposta. A variável resposta é categórica e não apresenta um preenchimento "robusto" em todas suas categorias, ou seja, são desbalanceados. Uma alternativa seria agrupar os score em classes menores (ex: bons e ruins; ruins, bons e médios,...) ou usufluir de alguma técnica de agrupamento para tratar problemas multi-classes com desbalanceamento. Uma maneira que poderia ser abordarda é testar diferentes formas de usar a variável resposta e assim escolher aquela que trará os melhores resultados. Dito isso, a estratégia usada para prever a qualidade do vinho foi considerar duas classes (como um problema de classificação binário) para prever a qualidade do vinho. Além disso, a ideia são testar diferentes algoritimos para tentar encontrar aquele que melhor se adeque ao problema referido.* <br>

**b.** Como foi definida a função de custo utilizada? <br>

*A função custo irá depender do algoritmo selecionado, por exemplo: no caso de árvores de decisão podemos escolher o critério de entropia como função custo; ou no SVM a função custo é dada como maximização da margem (que irá separar as duas classes, no caso de um problema binário); já para uma regressão logística a função custo é dada para miminizar a entropia cruzada (otimizada iterativamente pelo gradiente descendente).* <br>

**c.** Qual foi o critério utilizado na seleção do modelo final?

*Como critério para escolha do modelo final utilizaremos métricas que visam avaliar o quão bom os modelos se comportaram nesse problema. Existe uma gama de critérios para avaliação de modelos, cada um como pontos fortes e fracos. Por isso, vamos tentar escolher o algoritmo que possa maximizar duas métricas, que são: Acurácia e F1-Score. Um pouco sobre cada uma das métricas: Acurácia: irá medir o quão bem são classificados corretamente tanto a classe positiva quanto negativa, perante todas as classificações realizadas, quanto maior seu valor melhor (entre 0 e 1); F1-Score é uma medida com peso ponderado das métricas de precisão e recall, novamente aqui quanto maior seu valor melhor (entre 0 a 1) * <br>

**d.** Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método? <br>

*Como critério utilizado para validação de modelos vamos utilizar o método k-fold (com k=10 folds). Ele consiste em dividir a amostra original em k (k<n) partes, treinar com k-1 partes, testar com a que sobrou. Esse processo é repetivo k vezes, cada vez deixando uma parte diferente de fora do treinamento (para teste). A escolha é que esse método apresenta algumas vantagens perante a outros métodos: i) Menos enviesada que o holdout; ii) menos custoso que o leave-one-out; iii) menor variância que a do leave-one-out.* <br>

**e.** Quais evidências você possui de que seu modelo é suficientemente bom?

*Devido ao teste de validação cruzada e mais de um algoritmo testado é possível avaliar o desempenho do modelo. Nessas análises, as métricas no período de teste foram importantes para vermos como o modelo consegiu realizar predições em amostras que não foram usadas no treinamento. Enfim, como resultado tivemos a Random Forest como modelo que obteve melhor desempenho tanto em acurácio quanto f1-score, no período de teste quanto na validação cruzada. Além disso, para obter melhores resultados é necessário um tratamento das variáveis explicativas com feature engineering, testar outros modelos e seleção/filtros/criação de novas variáveis, ajudaria em obter um desempenho melhor.* <br>

**Podemos melhorar ainda mais os modelos realizando o tunning de parâmetros, por meio do grid search. A ideia é otimizar os parâmetros para uma métrica para obter os melhores parâmetros de cada algoritmo.**

### Modelos Propostos

*Testaremos modelos dos mais clássicos até o mais complexo:* <br>

1.Regressão Logística <br>
2.SVM RFB Kernel <br>
3.Árvore de Decisão <br>
4.KNN <br>
5.Random Forest <br>
