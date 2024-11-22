# Análise Estatística e Preditiva da Expectativa de Vida  

Este projeto utiliza modelagem estatística e preditiva para identificar as principais variáveis associadas a uma melhor expectativa de vida. Por meio deste estudo, foram obtidos insights relevantes para promover melhorias na saúde pública e orientar políticas que previnam a redução da expectativa de vida.  

**Fonte dos dados:**  
Os dados foram extraídos do [site da Organização Mundial da Saúde (OMS)](https://www.who.int/data/gho/data/themes/mortality-and-global-health-estimates/ghe-life-expectancy-and-healthy-life-expectancy).  

## Estrutura do Projeto  
O estudo foi segmentado em **7 etapas principais**:  

### 1. Ajustes Iniciais  
Nesta etapa, foram realizadas as importações necessárias e verificou-se que o *dataframe* apresentava espaçamentos nos nomes das colunas, o que poderia causar problemas futuros. Este problema foi resolvido para garantir consistência no processamento dos dados.  

---

### 2. Análise Exploratória  
Foram analisadas as distribuições das variáveis e criados gráficos para entender melhor o comportamento dos dados. Durante essa análise, foi identificado que diversas variáveis apresentavam distribuições assimétricas, indicando possíveis **outliers**.  
![Exemplo de gráfico exploratório](https://github.com/user-attachments/assets/8584169a-3b13-4fdc-b85a-21b24ac87257)  

---

### 3. Tratamento de Outliers e Valores Ausentes  
Uma grande dificuldade foi lidar com a ausência de dados em algumas colunas, como a variável de população, que apresentava 22% de valores faltantes.  

**Estratégias utilizadas:**  
- Valores ausentes acima de 3% foram preenchidos com a mediana, para evitar distorções causadas por valores extremos.  
- Valores ausentes abaixo de 3% foram removidos do conjunto de dados.  
- Outliers foram tratados utilizando a métrica de **quantis**: valores fora do intervalo `[Q1 - 1.5 * IQR, Q3 + 1.5 * IQR]` foram excluídos.  

Após esses ajustes, observou-se uma melhoria significativa na dispersão dos dados.  
![Ajuste dos dados após tratamento](https://github.com/user-attachments/assets/241c5b67-79be-49d9-a9e4-973f3a4f116a)  

---

### 4. Engenharia de Atributos (*Feature Engineering*)  
Novas variáveis foram criadas para enriquecer a análise, incluindo:  
- **pop_size**: classificação da população em 3 categorias com base nos quartis.  
- **lifestyle**: índice calculado a partir do consumo médio de álcool e índice de massa corporal.  

---

### 5. Análise de Correlação  
Nesta etapa, foi realizada uma análise de correlação para evitar multicolinearidade entre as variáveis (importante para métodos de regressão). Somente as variáveis altamente correlacionadas com o alvo e sem alta correlação entre si foram mantidas.  
![Mapa de correlação](https://github.com/user-attachments/assets/972c6cb2-5b2a-4535-95d7-5fc6747a2eab)  

---

### 6. Modelagem Estatística  
Foram elaborados três modelos estatísticos diferentes, avaliando:  
- O valor-p das variáveis em relação ao alvo.  
- A existência de multicolinearidade residual.  

O modelo final explicou aproximadamente **77% da variação na expectativa de vida**, indicando uma alta precisão na previsão.  

---

### 7. Conclusões  
**Fatores positivos que aumentam a expectativa de vida:**  
- Alta cobertura vacinal contra DTP3 (difteria, tétano e coqueluche) em crianças de 1 ano.  
- Maior nível de escolaridade.  
- Estilo de vida saudável (baixo consumo de álcool e bom índice de massa corporal).  

**Fatores negativos que reduzem a expectativa de vida:**  
- Altos índices de HIV.  
- Baixo peso aos 19 anos.  
- Alta taxa de mortalidade adulta.  

---

## Recomendações  
Com base nos resultados, foram propostas as seguintes recomendações para melhorar a saúde pública:  
1. Ampliar projetos sociais de conscientização sobre métodos preventivos para reduzir o HIV.  
2. Intensificar campanhas de vacinação.  
3. Incentivar a prática de esportes como parte de um estilo de vida saudável.  

---  

Este projeto demonstra como a análise de dados pode ser uma ferramenta poderosa para informar políticas públicas e melhorar a qualidade de vida da população.  
