# IA e ML

## Fundamentos de Inteligência Artificial e ML

### Conceito de Inteligência:

* Não há um conceito sedimentado de IA, assim como a definição de inteligência humana é lacunosa.
* Aristóteles buscava definir inteligência como a capacidade de pensar racionalmente, através da disciplina lógica e do silogismo.
* Turing propôs o Teste de Turing (1950) para comparar o comportamento inteligente de máquinas com o humano.
* A IA busca reproduzir os "efeitos" da inteligência, focando nas regras lógicas do raciocínio para emular o pensamento lógico computacionalmente.
* Falsa associação do pensamento com a linguagem pelo Teste de Turing.
* O estudo de IA, atualmente, entretanto, “abrange lógica, probabilidade e matemática do contínuo, além de percepção, raciocínio, aprendizado e ação”.
* Ciência Pura: Compreender o comportamento inteligente; Ciência Aplicada: Implementar máquinas inteligentes.

### Histórico da IA:

* Início efetivo durante a Segunda Guerra Mundial, com Alan Turing criando máquina para decodificar mensagens nazistas.
* Primeiras tentativas de sintetizar o neurônio humano (McCulloch e Pitts, 1943), base para as Redes Neurais Artificiais (RNAs).
* Sistemas especialistas (1969) como primeiro sucesso, codificando conhecimento de especialistas em regras computacionais.
* Evolução para agentes com aprendizado durante a operação, sem descaracterizar agentes sem aprendizado como não inteligentes.

### Machine Learning (ML):

* ML são algoritmos que permitem aos computadores tomar decisões a partir da análise de dados, ao invés de serem programados explicitamente.
* Supera a limitação do paradigma de Samuel, onde o computador só faz o que foi programado, permitindo certa liberdade de evolução.

## Principais Linhas de Pesquisa em IA

### IA Simbólica:

* Modelação matemática de problemas com sistemas especialistas, utilizando "motores de inferência" e regras "se-então".
* Agentes inteligentes simbólicos interagem com o meio através de sensores e atuadores, seguindo o paradigma de Samuel (ações pré-definidas).

### IA Conexionista:

* Simulação computacional do raciocínio humano através de Redes Neurais Artificiais (RNAs), inspiradas nas conexões entre neurônios (sinapses).
* Aprendizado ocorre pela alteração dos pesos sinápticos.

### IA Evolucionária:

* Baseada na evolução natural, utiliza algoritmos genéticos (AGs) para buscar soluções otimizadas em problemas complexos.
* AGs são algoritmos estocásticos que exploram o espaço de soluções utilizando operadores probabilísticos e informações de "fitness".

### IA Difusa:

* Aborda problemas de alta complexidade e incerteza, onde a lógica determinística falha.
* Utiliza lógica Fuzzi (grau de incerteza) e computação quântica (conceitos estocásticos da mecânica quântica).

## IA Simbólica e Heurística

### Princípios da IA Simbólica:

* Sistemas especialistas com mecanismo de inferência e base de conhecimento (ou banco de dados).
* Interação com o meio por sensores e atuadores.
* Uso do paradigma de programação declarativo (ex: Prolog) para criar árvores de decisão, em contraste com o paradigma imperativo (ex: Java, C++, Python).

### Heurística:

* Técnicas para encontrar soluções aproximadas em problemas complexos, onde a busca exaustiva é inviável.
* Exemplo: Quebra-cabeça de blocos deslizantes, onde o objetivo é ordenar os blocos numerados movendo-os dentro da caixa.
* Árvores de busca representam todas as opções de solução, com buscas exaustivas (cegas) ou informadas (heurísticas).

## IA Conexionista e Treinamento Neural

### Neurônio e Perceptron:

* Inspirado no neurônio biológico, o neurônio artificial (Perceptron) recebe entradas, aplica pesos e uma função de ativação para gerar uma saída.
* Equações do Perceptron: Campo induzido = $\Sigma (x_i * w_{ji}) + \theta_j$; Função de ativação degrau: Saída = +1 se $d \ge 0$, -1 se $d < 0$.

### Redes Neurais Artificiais (RNAs):

* Conjunto de neurônios interconectados em camadas (entrada, escondidas, saída).
* Aprendizado por ajuste dos pesos sinápticos através de algoritmos de treinamento.

### Treinamento Neural:

* O objetivo da aula prática é apresentar os fundamentos de treinamento neural e uma prática de treinamento de RNA.

### Supervisionado:

* Usa amostras de treinamento e teste para ajustar os pesos da RNA.
* Regra Delta (Widrow-Hoff): Ajuste dos pesos proporcional ao erro entre a saída desejada e a obtida.

### Não Supervisionado:

* Organização dos dados em clusters naturais, sem supervisão externa.

## RNAs Comerciais Disponíveis

### Azure (Microsoft):

* Plataforma como serviço (PaaS) para consumo de serviços de IA.
* Cursos e certificações (ex: AI-100).

### TensorFlow (Google):

* Biblioteca para Machine Learning.
* Recursos e tutoriais disponíveis (ex: YouTube).

### Watson (IBM):

* Plataforma com diversas ferramentas e serviços de IA (Watson Studio, Chatbot, Watson Machine Learning, Deep Learning, Aprendizado por Reforço).

## Considerações Finais

* IA como ferramenta para resolver problemas de forma similar à mente humana (RNAs) ou à natureza (IA evolucionária, difusa).
* Ênfase na importância do aprendizado de máquina e nas diferentes abordagens da IA.