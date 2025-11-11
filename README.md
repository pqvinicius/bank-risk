# Análise de Risco Bancário

## 📋 Sobre o Projeto

Este é um projeto de análise de dados sobre risco bancário, desenvolvido como parte dos meus estudos em análise de dados. O objetivo é explorar e entender padrões relacionados ao comportamento de clientes bancários, identificando características que podem estar associadas a diferentes perfis de risco.

**Status do Projeto:** 🚧 Em desenvolvimento

## 🎯 Objetivos

- Explorar e entender a base de dados de clientes bancários
- Realizar análises descritivas sobre o perfil dos clientes
- Identificar padrões e características relevantes
- Visualizar dados de forma clara e informativa

## 📊 Sobre os Dados

O dataset utilizado é o **Bank Marketing Dataset**, que contém informações sobre campanhas de marketing direto de uma instituição bancária portuguesa. Os dados incluem:

- **45.211 registros** de clientes
- **17 variáveis** incluindo características demográficas, financeiras e comportamentais
- Período dos dados: Maio de 2008 a Novembro de 2010

### Principais Variáveis
- Dados demográficos: idade, profissão, estado civil, educação
- Dados financeiros: saldo, empréstimos, crédito em default
- Dados de campanha: duração do contato, número de tentativas, resultado anterior

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Pandas** - Manipulação e análise de dados
- **NumPy** - Operações numéricas
- **Matplotlib** - Visualização de dados
- **Seaborn** - Visualizações estatísticas avançadas
- **Jupyter Notebook** - Ambiente de desenvolvimento

## 📈 Análises Realizadas

### Análise Exploratória
- Estatísticas descritivas da base de dados
- Distribuição de idade dos clientes
- Análise de profissões dos clientes
- Análise de tipos de contato
- Identificação de outliers (método IQR)
- Análise de correlação entre variáveis numéricas

### Análises de Relacionamento
- Relação entre idade e saldo bancário
- Distribuição de saldo vs. inadimplência, empréstimos e financiamento imobiliário
- Taxa de conversão por grupos (outliers vs. não-outliers)
- Comparação entre clientes novos e antigos

### Visualizações
- Histogramas de distribuição
- Boxplots para análise de outliers
- Gráficos de barras para variáveis categóricas
- Gráficos de dispersão e densidade
- Mapas de calor de correlação
- Gráficos comparativos de taxa de conversão

## 📝 Principais Descobertas

Através das análises realizadas, foi possível identificar que:

- O público-alvo principal está concentrado na faixa de **30-40 anos**
- As profissões mais representadas são: blue-collar (21.53%), gestão (20.92%) e técnicos (16.80%)
- O dataset não possui valores faltantes
- **10.42%** dos clientes são considerados outliers em relação ao saldo (acima de 3.462 euros)
- Clientes com saldo alto (outliers) têm **taxa de conversão maior** (16.26% vs 11.17%)
- Clientes antigos têm **taxa de conversão significativamente maior** (23.07% vs 9.16%) que clientes novos
- A maioria dos contatos é feita por **celular (64.77%)**

## 📄 Documentação

Para uma análise detalhada e completa dos resultados, consulte o arquivo **[ANALISE.md](ANALISE.md)** que contém todas as descobertas, metodologias e conclusões do projeto.

---

**Nota:** Este é um projeto é parte do meu aprendizado em análise de dados. Feedback e sugestões são sempre bem-vindos! 😊

OBS: Todos os markdowns foram feitos com AI.
