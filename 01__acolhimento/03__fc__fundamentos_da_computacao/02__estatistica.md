# Estatística

## Conceitos Fundamentais

* **Estatística:** Ramo da matemática que coleta, analisa, interpreta e apresenta dados numéricos.
* **Métodos Estatísticos:** Formas organizadas de tratamento de dados.
* **População:** Conjunto total de elementos a serem observados.
* **Amostra:** Subconjunto da população.
* **Medidas de Posição (Tendência Central):** Valores que descrevem o centro dos dados (média, moda, mediana).
* **Medidas de Dispersão:** Valores que indicam a variabilidade dos dados (variância, desvio padrão).

## Média

* **Definição:** Valor que representa a tendência central de um conjunto de dados.
* **Dados não agrupados:**
    * Fórmula: $\overline{X} = (\Sigma x_i) / n$
    * Exemplo: Preço médio de discos rígidos externos.
* **Dados agrupados (Distribuição de Frequência):**
    * Fórmula: $\overline{X} = (\Sigma x_i * f_i) / n$
    * Conhecida como média ponderada.
    * Exemplo: Valor médio do frete de mercadorias.
* **Dados agrupados por classe:**
    * Usa o ponto médio de cada intervalo $pm_i$.
    * Fórmula: $\overline{X} = (\Sigma pm_i * f_i) / n$
    * Exemplo: Tempo médio de uso de um aplicativo.

## Moda

* **Definição:** Valor que aparece com maior frequência em um conjunto de dados.
* Pode haver uma ou mais modas, ou nenhuma (amodal).
* **Exemplo:** Moda dos preços de discos rígidos.
* **Dados agrupados:**
    * Identificar o valor com a maior frequência.
    * Exemplo: Moda dos valores de frete.
* **Dados agrupados por classe:**
    * Fórmula: $Mo = L_i + ((f_{post} * A) / (f_{ant} + f_{post}))$
    * $L_i$: Limite inferior da classe modal.
    * $f_{post}$: Frequência da classe posterior à modal.
    * $f_{ant}$: Frequência da classe anterior à modal.
    * A: Amplitude da classe modal.
    * Exemplo: Moda do tempo de permanência em um aplicativo.

## Mediana

* **Definição:** Valor que ocupa a posição central em um conjunto de dados ordenados (rol).
* Se o número de dados for ímpar, é o valor central.
* Se o número de dados for par, é a média dos dois valores centrais.
* **Exemplo:** Mediana dos preços de discos rígidos.
* **Dados agrupados:**
    * Calcular a frequência acumulada ($fa$).
    * Identificar a posição central ($n/2$).
    * Exemplo: Mediana dos valores de frete.
* **Dados agrupados por classe:**
    * Fórmula: $Md = L_i + (((n/2 - \Sigma f_{ant}) * A) / f_{Md})$
    * $L_i$: Limite inferior da classe mediana.
    * n: Número total de elementos.
    * $\Sigma f_{ant}$: Frequência acumulada da classe anterior à mediana.
    * $f_{Md}$: Frequência da classe mediana.
    * A: Amplitude da classe mediana.
    * Exemplo: Mediana do tempo de permanência em um aplicativo.

## Variância

* **Definição:** Média dos quadrados dos desvios em relação à média.
* **Dados não agrupados:**
    * População: $\sigma^2 = \Sigma(x_i - \overline{X})^2 / n$
    * Amostra: $\sigma^2 = \Sigma(x_i - \overline{X})^2 / (n - 1)$
    * Exemplo: Variância dos preços de discos rígidos.
* **Dados agrupados:**
    * População: $\sigma^2 = (\Sigma(x_i - \overline{X})^2 * f_i) / n$
    * Amostra: $\sigma^2 = (\Sigma(x_i - \overline{X})^2 * f_i) / (n - 1)$
    * Exemplo: Variância dos valores de frete.
* **Dados agrupados por classe:**
    * População: $\sigma^2 = (\Sigma(pm_i - \overline{X})^2 * f_i) / n$
    * Amostra: $\sigma^2 = (\Sigma(pm_i - \overline{X})^2 * f_i) / (n - 1)$
    * Exemplo: Variância do tempo de permanência em um aplicativo.

## Desvio Padrão

* **Definição:** Raiz quadrada da variância.
* Indica a dispersão dos dados em relação à média.
* **Dados não agrupados:**
    * População: $\sigma = \sqrt{ (\Sigma(x_i - \overline{X})^2 / n) }$
    * Amostra: $\sigma = \sqrt{ (\Sigma(x_i - \overline{X})^2 / (n - 1)) }$
    * Exemplo: Desvio padrão dos preços de discos rígidos.
* **Dados agrupados:**
    * População: $\sigma = \sqrt{ ((\Sigma(x_i - \overline{X})^2 * f_i) / n) }$
    * Amostra: $\sigma = \sqrt{ ((\Sigma(x_i - \overline{X})^2 * f_i) / (n-1)) }$
    * Exemplo: Desvio padrão dos valores de frete.
* **Dados agrupados por classe:**
    * População: $\sigma = \sqrt{ ( ( \Sigma(pm_i - \overline{X})^2 * f_i ) / n ) }$
    * Amostra: $\sigma = \sqrt{ ( ( \Sigma(pm_i - \overline{X})^2 * f_i ) / (n - 1) ) }$
    * Exemplo: Desvio padrão do tempo de permanência em um aplicativo.