# Análise de Popularidade de Nomes de Bebês nos EUA (1880-2010)

Análise de dados exploratória sobre o dataset de nomes de bebês dos Estados Unidos, focada em identificar tendências históricas e picos de popularidade causados por eventos externos.


## 🎯 Objetivo do Projeto

Este projeto busca responder às seguintes perguntas:
- Como a popularidade dos nomes evolui ao longo do tempo?
- É possível identificar "modas" de nomes que surgem e desaparecem rapidamente?
- Eventos externos, como o surgimento de celebridades ou o lançamento de filmes, podem ser correlacionados com um aumento súbito na popularidade de um nome?

---

## 🛠️ Metodologia

A análise foi conduzida seguindo os seguintes passos:

1.  **Consolidação de Dados:** Os dados, originalmente separados em arquivos anuais (de `yob1880.txt` a `yob2010.txt`), foram lidos e consolidados em um único DataFrame do Pandas para facilitar a manipulação.

2.  **Normalização dos Dados:** Para comparar a popularidade dos nomes entre anos com diferentes totais de nascimentos, foi criada uma coluna de proporção (`prop`). Esta coluna foi calculada da seguinte forma para cada nome em um determinado ano:
    $$ \text{proporção} = \frac{\text{nascimentos}_{\text{nome}}}{\text{total de nascimentos}_{\text{ano}}} $$

3.  **Detecção de Picos de Popularidade:** Foi desenvolvida uma função em Python (`maior_aumento`) que, para um determinado nome, encontra o ano em que houve o maior aumento **proporcional** de popularidade em relação ao ano anterior. Isso permite identificar "explosões" de nomes de forma mais precisa do que apenas olhando o número bruto de nascimentos.

4.  **Análise de Causa e Efeito:** Com a capacidade de identificar os picos, a análise buscou conectar esses aumentos a eventos externos documentados. Um caso de estudo principal foi o nome **"Maddox"**, cujo aumento meteórico no início dos anos 2000 foi diretamente ligado à adoção do filho da atriz Angelina Jolie.

5.  **Visualização de Dados:** Para cada nome analisado, foi gerado um gráfico de linha do tempo, plotando o número de nascimentos ao longo dos anos. Esta visualização serve para confirmar as tendências e o impacto dos eventos externos.


## 🚀 Resultados e Insights

A análise confirmou que eventos externos têm um impacto massivo e mensurável na escolha de nomes.

**Exemplo: O Caso "Maddox"**

O gráfico abaixo ilustra a popularidade do nome "Maddox". Antes de 2003, o nome era praticamente inexistente. Após a adoção de Maddox Jolie-Pitt, o nome explodiu em popularidade, provando a forte correlação entre a cultura de celebridades e as tendências de nomes.

<img width="841" height="547" alt="image" src="https://github.com/user-attachments/assets/d3604ae2-319d-4e05-9b67-dda074a5d7d1" />

---

## 💻 Como Executar o Projeto

1.  Clone este repositório: `git clone https://github.com/seu-usuario/analise-nomes-bebes-eua.git`
2.  O código está no notebook `analise-nomes-bebes-eua.ipynb` e pode ser executado em ambientes como Google Colab ou Jupyter Notebook.
3.  Os dados originais não estão incluídos neste repositório, mas podem ser encontrados no [repositório de Wes McKinney](https://github.com/wesm/pydata-book/tree/3rd-edition/datasets/babynames), autor de "Python for Data Analysis". O notebook carrega os dados diretamente a partir do GitHub.

---

**Ferramentas Utilizadas:** Python, Pandas, Matplotlib.
