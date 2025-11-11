# Análise de Risco Bancário - Relatório Completo

## 📊 Resumo Executivo

Este documento apresenta uma análise exploratória completa do dataset de marketing bancário, focando na identificação de padrões comportamentais e características que influenciam a conversão de clientes em produtos bancários (termo de depósito).

**Dataset:** Bank Marketing Dataset  
**Período:** Maio de 2008 a Novembro de 2010  
**Total de Registros:** 45.211 clientes  
**Variáveis:** 17 (7 numéricas, 10 categóricas)

---

## 1. Análise Exploratória Inicial

### 1.1 Estrutura dos Dados

O dataset possui **45.211 registros** sem valores faltantes, contendo:
- **7 variáveis numéricas:** age, balance, day, duration, campaign, pdays, previous
- **10 variáveis categóricas:** job, marital, education, default, housing, loan, contact, month, poutcome, y

**Variável Target:** `y` (sim/não - se o cliente assinou o termo de depósito)

---

## 2. Análise Demográfica

### 2.1 Distribuição de Idade

**Principais Descobertas:**
- O público-alvo principal está concentrado na faixa de **30-40 anos**
- Idades de 30-32 anos apresentam o maior número de clientes
- A base de clientes se estende até idades bem avançadas (até 95 anos)
- A distribuição apresenta uma curva aproximadamente normal com leve assimetria positiva

**Análise de Outliers (Idade):**
- O boxplot revela a presença de alguns outliers na faixa etária mais alta
- A maioria dos clientes está concentrada entre os quartis Q1 e Q3

### 2.2 Distribuição de Profissões

**Top 5 Profissões:**
1. **Blue-collar** - 9.732 clientes (21.53%)
2. **Management** - 9.458 clientes (20.92%)
3. **Technician** - 7.597 clientes (16.80%)
4. **Admin.** - 5.171 clientes (11.44%)
5. **Services** - 4.154 clientes (9.19%)

**Conclusão:** A maioria dos clientes está concentrada em profissionais manuais/fábricas, gestão/administrativa e técnicos, representando juntos **59.25%** da base total.

**Outras Profissões:**
- Retired: 2.264 (5.01%)
- Self-employed: 1.579 (3.49%)
- Entrepreneur: 1.487 (3.29%)
- Unemployed: 1.303 (2.88%)
- Housemaid: 1.240 (2.74%)
- Student: 938 (2.07%)
- Unknown: 288 (0.64%)

---

## 3. Análise de Contato

### 3.1 Tipos de Contato

**Distribuição:**
- **Cellular (Celular):** 29.285 contatos (64.77%)
- **Unknown (Desconhecido):** 13.020 contatos (28.80%)
- **Telephone (Telefone Fixo):** 2.906 contatos (6.43%)

**Conclusão:** A grande maioria dos contatos é realizada via celular, indicando uma preferência por este canal de comunicação.

---

## 4. Análise Financeira

### 4.1 Relação Idade vs. Saldo

**Observações:**
- O gráfico de dispersão mostra uma relação fraca positiva entre idade e saldo
- Há presença de **overplotting** (sobreposição de pontos), indicando concentração em determinadas faixas
- O histograma 2D de densidade revela maior concentração de saldos entre -5.000 e 20.000 euros
- Clientes mais velhos tendem a ter saldos ligeiramente maiores, mas a correlação é baixa

### 4.2 Distribuição de Saldo por Variáveis de Risco

**Análise de Saldo vs. Inadimplência (Default):**
- Clientes sem inadimplência apresentam distribuição de saldo similar àqueles com inadimplência
- Não há diferença significativa na mediana de saldo entre os grupos

**Análise de Saldo vs. Financiamento Imobiliário (Housing):**
- Clientes com financiamento imobiliário tendem a ter saldos ligeiramente menores
- Isso pode indicar que parte da renda está comprometida com o financiamento

**Análise de Saldo vs. Empréstimo Pessoal (Loan):**
- Clientes com empréstimo pessoal também apresentam saldos menores
- Similar ao padrão observado com financiamento imobiliário

---

## 5. Identificação de Outliers

### 5.1 Método IQR (Intervalo Interquartil)

**Cálculos:**
- **Quartil 1 (Q1):** 72 euros
- **Quartil 3 (Q3):** 1.428 euros
- **IQR:** 1.356 euros
- **Limite Superior:** 3.462 euros

**Resultados:**
- **Clientes Outliers:** 4.712 (10.42%)
- **Clientes Não-Outliers:** 40.499 (89.58%)

**Definição:** Clientes com saldo acima de **3.462 euros** foram classificados como outliers.

### 5.2 Análise Comparativa: Outliers vs. Não-Outliers

#### Taxa de Conversão

**Grupo NÃO-OUTLIERS (Saldo ≤ 3.462 euros):**
- Não converteu: 88.83%
- Converteu: 11.17%

**Grupo OUTLIERS (Saldo > 3.462 euros):**
- Não converteu: 83.74%
- Converteu: **16.26%**

**🎯 Descoberta Importante:** Clientes com saldo alto (outliers) apresentam uma **taxa de conversão 45% maior** que clientes com saldo baixo/médio (16.26% vs 11.17%).

#### Distribuição de Idade

**Grupo NÃO-OUTLIERS:**
- Média: 40.63 anos
- Mediana: 39 anos
- Desvio Padrão: 10.47 anos
- Faixa: 18-95 anos

**Grupo OUTLIERS:**
- Média: 43.57 anos
- Mediana: 42 anos
- Desvio Padrão: 11.52 anos
- Faixa: 19-87 anos

**Conclusão:** Clientes com saldo alto são, em média, **3 anos mais velhos** que o grupo de não-outliers, sugerindo que clientes mais maduros tendem a acumular mais recursos financeiros.

---

## 6. Análise de Taxa de Conversão

### 6.1 Taxa de Conversão por Variáveis de Risco

#### Inadimplência (Default)
- Clientes sem inadimplência apresentam taxa de conversão maior
- Clientes com inadimplência têm menor propensão a assinar o termo de depósito

#### Financiamento Imobiliário (Housing)
- Clientes com financiamento imobiliário apresentam padrão de conversão diferente
- A presença de financiamento pode influenciar a decisão de investir em termo de depósito

#### Empréstimo Pessoal (Loan)
- Similar ao padrão de financiamento imobiliário
- Clientes com empréstimos podem ter menor capacidade de investimento

---

## 7. Análise de Correlação

### 7.1 Matriz de Correlação (Pearson)

**Correlações Mais Fortes:**
- **pdays e previous:** 0.4548 (correlação moderada positiva)
  - Indica que clientes contatados anteriormente tendem a ter mais contatos prévios
  
**Correlações Fracas:**
- **age e balance:** 0.0978 (correlação fraca positiva)
- **balance e duration:** 0.0216 (correlação muito fraca)
- **day e campaign:** 0.1625 (correlação fraca positiva)

**Correlações Negativas:**
- **day e pdays:** -0.0930 (correlação fraca negativa)
- **duration e campaign:** -0.0846 (correlação fraca negativa)

**Conclusão:** As variáveis numéricas apresentam correlações geralmente fracas, indicando baixa multicolinearidade e sugerindo que cada variável traz informações únicas para o modelo.

---

## 8. Análise de Clientes Novos vs. Antigos

### 8.1 Definição dos Grupos

- **Clientes Novos:** `previous == 0` (nunca foram contatados antes)
- **Clientes Antigos:** `previous > 0` (já foram contatados em campanhas anteriores)

### 8.2 Taxa de Conversão Comparativa

**Clientes Novos:**
- Não converteu: **90.84%**
- Converteu: **9.16%**

**Clientes Antigos:**
- Não converteu: **76.93%**
- Converteu: **23.07%**

**🎯 Descoberta Crítica:** Clientes antigos (já contatados anteriormente) apresentam uma **taxa de conversão 2,5 vezes maior** que clientes novos (23.07% vs 9.16%). Isso sugere que:

1. Clientes que já foram contatados têm maior interesse ou familiaridade com o produto
2. A persistência em campanhas de marketing pode ser eficaz
3. Clientes antigos podem estar mais propensos a investir após múltiplos contatos

---

## 9. Conclusões Principais

### 9.1 Perfil do Cliente com Maior Taxa de Conversão

Com base nas análises realizadas, o perfil ideal de cliente com maior probabilidade de conversão seria:

✅ **Saldo alto** (acima de 3.462 euros)  
✅ **Cliente antigo** (já contatado em campanhas anteriores)  
✅ **Sem inadimplência**  
✅ **Idade média de 43-44 anos**  
✅ **Profissão:** Management, Technician ou Admin.

### 9.2 Insights para Estratégia de Marketing

1. **Foco em Clientes Antigos:** Priorizar clientes que já foram contatados anteriormente, pois apresentam taxa de conversão significativamente maior.

2. **Segmentação por Saldo:** Clientes com saldo alto devem receber atenção especial, pois têm maior propensão a investir.

3. **Canal Preferencial:** Celular é o canal dominante (64.77% dos contatos), indicando que este deve ser o foco principal das campanhas.

4. **Profissões Alvo:** Profissionais de gestão, técnicos e administrativos representam quase 50% da base e devem ser segmentos prioritários.

5. **Idade Ideal:** Focar em clientes entre 30-50 anos, com atenção especial para aqueles na faixa de 40-45 anos que tendem a ter maior saldo.

### 9.3 Limitações e Próximos Passos

**Limitações:**
- Análise exploratória descritiva, sem modelagem preditiva ainda
- Não foram testadas hipóteses estatísticas formais
- Análise temporal (por mês/ano) não foi explorada em detalhes

**Próximos Passos Sugeridos:**
- [ ] Análise temporal (sazonalidade, tendências ao longo do tempo)
- [ ] Modelagem preditiva (Regressão Logística, Random Forest, etc.)
- [ ] Análise de importância de variáveis
- [ ] Segmentação de clientes (clustering)
- [ ] Análise de custo-benefício das campanhas
- [ ] Criação de score de propensão à conversão

---

## 10. Metodologia

### 10.1 Ferramentas Utilizadas

- **Python 3** - Linguagem de programação
- **Pandas** - Manipulação e análise de dados
- **NumPy** - Operações numéricas
- **Matplotlib** - Visualização de dados
- **Seaborn** - Visualizações estatísticas avançadas
- **Jupyter Notebook** - Ambiente de desenvolvimento

### 10.2 Métodos Estatísticos

- **Estatísticas Descritivas:** Média, mediana, desvio padrão, quartis
- **Método IQR:** Identificação de outliers
- **Correlação de Pearson:** Análise de relacionamento entre variáveis numéricas
- **Análise de Proporções:** Comparação de taxas de conversão entre grupos

---

## 📚 Referências

- Dataset: [Bank Marketing Dataset](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing)
- Artigo original: Moro et al., 2011 - "Using Data Mining for Bank Direct Marketing: An Application of the CRISP-DM Methodology"

---

**Autor:** Estudante e Aspirante a Analista de Dados  
**Data:** 2025
**Status:** Projeto Concluid


OBS: Todos os markdowns foram feitos com AI.

