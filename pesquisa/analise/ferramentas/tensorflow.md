# TensorFlow

## O que é?

- O TensorFlow é uma biblioteca de código aberto desenvolvida pelo Google Brain Team, projetada para facilitar o desenvolvimento e a execução de modelos de aprendizado de máquina e aprendizado profundo. Ele permite que os desenvolvedores criem e treinem redes neurais de forma eficiente, aproveitando o poder de processamento de CPUs e GPUs.

## Conceitos

**Tensores:**

- São estruturas de dados fundamentais no TensorFlow, representando arrays multidimensionais. Um número escalar é um tensor de dimensão zero, um vetor é um tensor unidimensional, e uma matriz é um tensor bidimensional. Tensores de ordem superior representam dados em mais dimensões

**Forma:**
- Refere-se às dimensões de um tensor. Por exemplo, um tensor com forma (3, 3) possui 3 linhas e 3 colunas.

**Classificação:**
- Indica o número de dimensões de um tensor. Um escalar tem rank 0, um vetor tem rank 1, uma matriz tem rank 2, e assim por diante.

## Arquitetura

**Pré-processamento dos Dados:**
- Preparação e limpeza dos dados para serem utilizados no modelo.

**Construção do Modelo:** 
- Definição da arquitetura da rede neural, incluindo camadas e funções de ativação.

**Treinamento e Estimativa:** 
- Ajuste dos pesos do modelo com base nos dados de treinamento e avaliação de seu desempenho.

## Execução e Portabilidade

**Desktops:** 
- Sistemas operacionais como Windows, macOS e Linux.

**Nuvem:** 
- Serviços de computação em nuvem para treinamento e implantação de modelos em larga escala.

**Dispositivos Móveis:** 
- Plataformas como iOS e Android, utilizando o TensorFlow Lite para inferência em dispositivos com recursos limitados.

Pode ser executado em CPUs e GPUs, aproveitando o paralelismo para acelerar os cálculos, especialmente em operações envolvendo grandes matrizes.​

## Ferramentas e Visualização

**TensorBoard:** 
- Uma ferramenta integrada ao TensorFlow que permite a visualização gráfica do grafo computacional, métricas de treinamento, histogramas e muito mais, facilitando a depuração e o entendimento do modelo.

## Algoritmos e APIs Suportados

**Regressão Linear:** 
- `tf.estimator.LinearRegressor`

**Classificação Linear:** 
- `tf.estimator.LinearClassifier`

**Classificação com Redes Neurais Profundas:** 
- `tf.estimator.DNNClassifier`

**Modelos Combinados (Wide & Deep):** 
- `tf.estimator.DNNLinearCombinedClassifier`

**Regressão com Árvores de Decisão:** 
- `tf.estimator.BoostedTreesRegressor`

**Classificação com Árvores de Decisão:** 
- `tf.estimator.BoostedTreesClassifier​`
