# STEP BY STEP FOR A MACHINE LEARNING PROJECT

### **1. Definição do problema de negócio**
* Entender a natureza do problema: **[Regressão]**, **[Classificação]**, **[Clusterização]**, **[IA]**, **[Estatística básica]**
* Coleta dos dados.
* Importação dos pacotes e bibliotecas

### **2. Análise exploratória dos dados**
* Estimativas de Localização/Posição **[Média, mediana e estimativas robustas]**
* Estimativas de variabilidade **[Desvio padrão e estimativas relacionadas]**
* Explorar distribuição dos dados **[Histogramas e percentis]**
* Verificar correlação dos dados
	
### **3. Dividir os dados em Treino e Testes**
* A técnica mais comum é a divisão 70/30
* Caso o conjunto seja grande, utilizar alguma técnica de amostragem
* Caso o conjunto seja pequeno, utilizar bootstrap
> **NOTA**: Qualquer transformação a seguir, aplicar no conjunto de testes seguindo as regras do conjunto de treino, a fim de evitar vazão de informação.

### **4. Lidar com Outliers**
* Remover dados ausentes **[Z Score, IQR, Boxplot, ABOD, CBLOF, Isolation Forest, LoOP]**

### **5. Tratar dados ausentes**
* Imputar dados com **[média, mediana, moda, clusterização para obter características]**
* Aplicar visualização de dados para verificar o motivo e se há padrão
* Remover a linha ou a coluna com dados ausentes **[utilizar como último recursos]**

### **6. Transformação dos dados**
* **[CATEGORIA]** Aplicar label encoding se houver hierárquia nos dados categóricos.
* **[CATEGORIA]** Aplicar o one hot encoding quando não há hierárquia.
* **{CATEGORIA}** Aplicar o **[category_encoders.TargetEncoder]** para converter categorias em probabilidades.
* **[CATEGORIA]** Criar grupos quando há muitas categorias.
* **[CONTÍNUOS]** Aplicar técnicas de padronização **[Standard, Robust, Quantile, Normalization]**

### **7. Seleção de atributos**
* Lidar com atributos multicolineares **[remover 1 coluna no one hot encoding e colunas de correlação perfeita derivadas de outros métodos]**
* Verificar os atributos mais relevantes para o modelo **[Matriz de correlação, Árvore de decisão]**
* Utilizar o pacote **[rfpimp]** para obter a matriz de atributos. Quanto mais próximo de 1, mais um atributo pode ser previsto a partir de outro.
* Utilizar a eliminação recursiva de atributos. Pg:93.

### **8. Criar atributos**
* Pode ser interessante criar atributos combinando um ou mais atributos
* Aplicar clusterização para encontrar relacionamentos
	
### **9. Validação das transformação em Treino e Testes**
* Certificar que as transformações foram aplicadas nos dados de testes sem vazamento de informação.
	
### **10. Balanceamento de classes**
* Certificar de que a proporção entre as classes estejam balanceadas **[Remover registros, criar novos registros fake]**
	
### **11. Primeira modelagem**
* Criar um modelo completamente aleatório pra ter como base **[Random ou selecionar um algoritmo qualquer]**
	
### **12. Testar os dados com diferentes modelos**
* Listar diferentes algoritmos e testá-los
* Aplicar validação cruzada **[K-Fold]**
	
### **13. Ajuste de Hiperparâmetros**
* Aplicar técnicas para testar diferentes parâmetros **[GridSearch, RandomSearch]**
	
### **14. Testar e Avaliar o modelo**
* Aplicar o modelo ao conjunto de testes
* Utilizar métricas de avaliação para verificar o desempenho do modelo
* Voltar ao passo **[6]**, se necessário
	
### **15. Questão de negócio**
* Medir os ganhos da empresa com a implementação do modelo
	
### **16. Deploy do modelo**
* Gerar o arquivo do modelo
* Escolher onde será feito o deploy **[GCP, AWS, Azure]**
* Dentro do ambiente, escolher como será feito o deploy **[EC2, Lambda, WebApp, API]**

---

## References:
* **[1]**: *Practical Statistics for Data Scientists*: 50+ Essential Concepts Using R and Python 2nd Edition. [Link](https://www.amazon.com/Practical-Statistics-Data-Scientists-Essential/dp/149207294X)
* **[2]**: *Machine Learning Pocket Reference*: Working with Structured Data in Python 1st Edition. [Link](https://www.amazon.com/Machine-Learning-Pocket-Reference-Structured/dp/1492047546)
* **[3]**: *Hands-on Machine Learning with Scikit-Learn, Keras, and TensorFlow*: Concepts, Tools, and Techniques to Build Intelligent Systems. [Link](https://www.amazon.com.br/Hands-Machine-Learning-Scikit-Learn-TensorFlow/dp/1492032646/ref=asc_df_1492032646/?tag=googleshopp00-20&linkCode=df0&hvadid=379733272930&hvpos=&hvnetw=g&hvrand=16572882679886660793&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1001760&hvtargid=pla-523968811896&psc=1)
