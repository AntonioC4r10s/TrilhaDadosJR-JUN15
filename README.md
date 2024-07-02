![Código Certo Coders](https://utfs.io/f/3b2340e8-5523-4aca-a549-0688fd07450e-j4edu.jfif)

# 📚 Trilha Inicial Ciência de Dados Jr
Este projeto tem como objetivo realizar uma análise básica de dados utilizando Python, explorando um conjunto de dados pré-definido para extrair insights simples através de estatísticas descritivas e visualizações gráficas.

# Análise de Vendas de Cursos Online

Este projeto de ciência de dados analisa as vendas de cursos online usando um conjunto de dados CSV. As análises incluem o cálculo da receita total gerada, a identificação do curso com o maior número de vendas e a visualização da distribuição das vendas ao longo do tempo.

## Sumário

- [Introdução](#introdução)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Análises](#tecnologias-utilizadas)
- [Conclusões](#conclusões) 
- [Contato](#contato)

## Introdução

Este projeto foi desenvolvido no Google Colab e foca em três principais abordagens:
1. Calcular a receita total gerada pela venda dos cursos.
2. Identificar o curso com o maior número de vendas.
3. Visualizar a distribuição das vendas ao longo do tempo através de gráficos.

## Tecnologias Utilizadas

- Python 3.10.12
- Pandas
- Matplotlib
- Seaborn
- Google Colab

## Instalação
Basta abrir o arquivo .ipynb e escolher a opção 'Open in Colab', onde será possível modificar, copiar e trabalhar no projeto.

## Análises

- Calcular a receita total gerada pela venda dos cursos.

```python
vendas = df_dados['Quantidade de Vendas']
print(f'Receita total: R$ {sum(df_dados["Preço Unitário"] * df_dados["Quantidade de Vendas"]):.2f}')
# saída: Receita total: R$ 32735.10
```
- Identificar o curso com o maior número de vendas.

```python
df_cursos = df_cursos.sort_values(by='Quantidade de Vendas', ascending=False)
print(f'Curso com maior número de vendas: {df_cursos.iloc[0]["Nome do Curso"]} - {df_cursos.iloc[0]["Quantidade de Vendas"]} vendas')
# saída: Curso com maior número de vendas: Introdução à Programação em Python - 95 vendas
```

- Visualizar a distribuição das vendas ao longo do tempo através de gráficos.
```python
df_tempo = df_dados.groupby('Data')['Quantidade de Vendas'].sum().reset_index()
df_tempo.head()
plt.figure(figsize=(10, 6))
sns.lineplot(x='Data', y='Quantidade de Vendas', data=df_tempo, marker='o', palette='Blues')

plt.xlabel('Data')
plt.ylabel('Quantidade de Vendas')
plt.title('Quantidade de Vendas ao longo do tempo')
plt.xticks(rotation=90)
plt.show()
# saída:
```
<img src="Quantidade de Vendas ao longo do tempo.png" width="700">

- Visualizar a quantidade de Vendas por Curso
```python
plt.figure(figsize=(10, 6))
sns.barplot(x='Nome do Curso', y='Quantidade de Vendas', data=df_cursos, palette='Set1')

for index, value in enumerate(df_cursos['Quantidade de Vendas']):
    plt.text(index, value, str(value), ha='center', va='bottom')

plt.xticks(rotation=90)
plt.xlabel('Curso')
plt.ylabel('Quantidade de Vendas')
plt.title('Quantidade de Vendas por Curso')
plt.show()  
# saída:
```
<img src="Quantidade de Vendas por Curso.png" width="700">

- Gráfico de dispersão para relação entre variáveis Vendas e Preço.

```python
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Preço Unitário', y='Quantidade de Vendas', 
                hue='Nome do Curso', data=df_dados, palette='Set2', s=70) 
plt.xlabel('Preço')
plt.ylabel('Quantidade de Vendas')
plt.title('Quantidade de Vendas x Preço')
plt.show()
# saída:
```
<img src="Quantidade de Vendas x Preço.png" width="700">

## Conclusões

Temos a conclusão a partir do case analisado que o curso com o maior número de vendas é o 'Introdução à Programação em Python'. Além disso, é possível observar picos de vendas em dois períodos distintos: um no início do mês e outro por volta do dia 20. Esses períodos sugerem que há uma demanda sazonal por cursos específicos nessas datas.

Analisando o gráfico de dispersão, observamos que cursos mais baratos tendem a ter vendas mais elevadas, refletindo uma sensibilidade dos consumidores ao preço. Por outro lado, cursos mais caros apresentam um volume de vendas menor, indicando uma preferência por preços mais acessíveis entre os consumidores.

Esta análise permite inferir estratégias de marketing e precificação que podem ser exploradas para otimizar as vendas de cursos online, ajustando os preços e lançamentos de novos cursos de acordo com os padrões observados.

## Contato

- [Linkedin](https://www.linkedin.com/in/antoniojuniortec/)
- [Github](https://github.com/AntonioC4r10s)

