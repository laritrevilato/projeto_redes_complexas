# projeto_redes_complexas
Projeto final da disciplina de Redes Complexas do PPGCO UFU - Larissa Alves Trevilato

# Análise de Estruturas Proteicas por meio de Redes Complexas

## Descrição

Este projeto apresenta uma metodologia para modelagem de proteínas como **redes complexas**, permitindo a aplicação de técnicas clássicas da Teoria dos Grafos para análise de sua organização estrutural.

A metodologia foi validada inicialmente utilizando a proteína **1UBQ (Ubiquitina)** e posteriormente aplicada à proteína **6B1T**, correspondente ao capsídeo do **Adenovírus Humano Tipo 5**, obtida no **Protein Data Bank (PDB)**.

O projeto foi desenvolvido como trabalho final da disciplina **Redes Complexas**, do Programa de Pós-Graduação em Ciência da Computação da Universidade Federal de Uberlândia (UFU).

---

# Objetivos

O projeto possui os seguintes objetivos:

- Ler estruturas proteicas no formato PDB;
- Representar proteínas como redes de contatos entre resíduos;
- Construir grafos não direcionados e não ponderados;
- Avaliar diferentes valores de cutoff para construção da rede;
- Calcular métricas topológicas clássicas;
- Detectar comunidades utilizando o algoritmo Louvain;
- Visualizar os resultados obtidos em duas e três dimensões.

---

# Metodologia

O pipeline desenvolvido é composto pelas seguintes etapas:

1. Leitura do arquivo PDB;
2. Extração dos resíduos contendo átomo Cα;
3. Construção de uma KD-Tree para busca eficiente de vizinhos;
4. Construção da rede de contatos;
5. Cálculo das estatísticas da rede;
6. Avaliação de diferentes valores de cutoff;
7. Cálculo das medidas de centralidade;
8. Detecção de comunidades utilizando Louvain;
9. Visualização da estrutura tridimensional.

---

# Estrutura do Projeto

```text
.
├── data/
│   ├── 1UBQ.pdb
│   ├── 6b1t-pdb-bundle.tar
│
├── notebook/
│   └── Protein_Contact_Network.ipynb
│
├── results/
│   ├── figures/
│   └── tables/
│
├── report/
│   └── Relatorio.pdf
│
└── README.md
```

---

# Bibliotecas utilizadas

O projeto foi desenvolvido em **Python** utilizando:

- Biopython
- NetworkX
- SciPy
- NumPy
- Pandas
- Matplotlib
- py3Dmol

---

# Proteínas utilizadas

## Proteína de validação

**PDB:** 1UBQ

Função:

Validação do pipeline computacional antes da aplicação à proteína principal.

---

## Proteína analisada

**PDB:** 6B1T

Descrição:

Capsídeo do Adenovírus Humano Tipo 5.

---

# Modelo de Rede

Cada resíduo contendo átomo **Cα** é representado por um vértice da rede.

Uma aresta é criada entre dois resíduos quando a distância euclidiana entre seus átomos Cα é menor ou igual a **8 Å**.

A rede construída possui as seguintes características:

- Não direcionada;
- Não ponderada;
- Baseada em contatos espaciais entre resíduos.

---

# Métricas calculadas

Foram calculadas as seguintes métricas:

- Número de vértices;
- Número de arestas;
- Grau médio;
- Componentes conectados;
- Distribuição de graus;
- Degree Centrality;
- Eigenvector Centrality;
- Closeness Centrality;
- Betweenness Centrality (aproximada).

Também foi aplicada a detecção de comunidades utilizando o algoritmo **Louvain**.

---

# Principais resultados

Para a proteína **6B1T**, foi obtida uma rede com:

| Métrica | Valor |
|----------|------:|
| Número de vértices | 12.544 |
| Número de arestas | 66.809 |
| Grau médio | 10,65 |
| Componentes conectados | 1 |
| Comunidades | 33 |

O estudo comparativo entre diferentes valores de cutoff indicou que **8 Å** apresentou o melhor equilíbrio entre conectividade, modularidade e custo computacional.

---

# Arquivos gerados

Durante a execução do notebook são produzidos automaticamente:

## Tabelas

- Estatísticas da rede;
- Comparação entre valores de cutoff;
- Distribuição de graus;
- Comunidades detectadas;
- Medidas de centralidade.

## Figuras

- Distribuição de graus;
- Distribuição em escala log-log;
- Visualização das comunidades;
- Visualização tridimensional da proteína.

---

# Como executar

## Instalar as dependências

```bash
pip install biopython networkx scipy pandas matplotlib py3Dmol
```

## Executar o notebook

Executar todas as células do notebook na ordem em que foram organizadas.

Os resultados serão armazenados automaticamente na pasta:

```text
results/
```

---

# Referências

- Protein Data Bank (PDB)
- Biopython Documentation
- NetworkX Documentation
- Barabási, A.-L. *Network Science*
- Newman, M. E. J. *Networks: An Introduction*

---

# Autor

**Larissa Trevilato**

Programa de Pós-Graduação em Ciência da Computação

Universidade Federal de Uberlândia (UFU)

Disciplina: Redes Complexas
