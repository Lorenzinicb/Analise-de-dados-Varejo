# Análise Exploratória de Dados - Mercado de Varejo

**Aluna:** Cristina Bertelle Lorenzini  
**Turma:** T8  

Este repositório contém o desenvolvimento do Mini Projeto de Análise de Dados utilizando Python, focado no comportamento de consumo e perfil demográfico de uma rede de varejo física.

---

## 📌 Contexto e Objetivo do Projeto

A rede de supermercados em análise possui uma base de **1.000 clientes únicos**. Embora o público masculino seja a maioria absoluta tanto em número de clientes cadastrados quanto em volume total de compras, esta análise estratégica foca no **público feminino**. Por comprarem menos proporcionalmente no consolidado global, as mulheres representam o maior potencial de crescimento para o faturamento da empresa.

O principal objetivo é mapear o comportamento desse grupo para direcionar campanhas de marketing assertivas, otimizando o número de itens por carrinho.

---

## 📊 Origem da Base e Unidade de Análise

O projeto utiliza a base "Varejo.csv", que é um recorte de 50.000 compras realizadas entre 2010 e 2022. A unidade de análise da base é o **item de compra** (cada linha representa um produto registrado numa nota fiscal).

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3.x
- **Bibliotecas:**
  * `pandas` (Manipulação e análise estruturada de dados)
  * `numpy` (Tratamento estatístico de valores ausentes)
  * `pypdf` (Extração de informações de dicionários de dados em formato PDF)
- **Ambiente:** Google Colab / Jupyter Notebook

---

## 🔄 Fluxo de Desenvolvimento

### 1. Ler & Diagnosticar
- Importação automática de arquivos `.csv` e `.pdf` contendo as notas fiscais brutas de compras e a descrição técnica das colunas.
- Renomeação e adequação das siglas originais da tabela para nomes descritivos e legíveis.
- Mapeamento de valores ausentes, dados inconsistentes (textos como `#N/D`) e duplicatas causadas por redundâncias no banco de dados original.

### 2. Decidir & Limpar
- **Colunas Fantasmas:** Remoção de 4 colunas residuais vazias (`Unnamed: 10` a `Unnamed: 13`).
- **Tratamento de Inconsistências:** Conversão de valores textuais nulos (`#N/D`) para `NaN` e preenchimento padronizado como `"Não Informado"` para preservar os registros.
- **Duplicatas Exatas:** Eliminação de linhas idênticas para evitar inflar artificialmente as vendas da operação.

### 3. Resultados & Insights de Negócio
- **Oportunidade de Mercado:** O público masculino lidera em compras gerais (451.020 produtos vs 382.427 das mulheres). Focar no público que compra menos é a melhor estratégia de crescimento de receita.
- **Domínio Feminino na Classe C:** Apesar de comprarem menos no geral, as mulheres dominam as vendas da **Classe C**, levando **119.885 produtos** contra 85.380 dos homens.
- **Comportamento do Carrinho:** A principal categoria de compras do público feminino é **ALIMENTOS** (200.274 unidades). As categorias secundárias de maior força no carrinho são **HIGIENE** (71.721 unidades) e **LIMPEZA** (67.328 unidades).

### 4. Plano de Ação Estratégico proposto
- Focar ações de marketing no público feminino das classes B e C.
- Criar campanhas de cross-selling (venda casada) e combos unindo produtos de alimentação à linha de Higiene e Limpeza domésticas para aumentar o ticket médio por compra.

---

## 📂 Estrutura do Repositório

- `notebook.ipynb`: Notebook com o código completo documentado e as análises estatísticas.
- `varejo_limpo.csv`: Base de dados resultante após a aplicação da limpeza e transformações de dados.
- `README.md`: Documentação geral do projeto.

---

## 📊 Limitação Técnica da Análise

A análise baseou-se puramente na quantidade de itens comprados (volume de saída). Devido à ausência de preços e custos na base de dados bruta, não foi possível determinar a margem de lucro ou o faturamento gerado pelos respectivos segmentos e categorias de produtos.
