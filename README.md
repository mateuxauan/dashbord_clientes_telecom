# 📊 Dashboard de Análise de Crédito e Perfil de Clientes (Telecom)


## 🖼️ Visão Geral do Projeto
Este projeto consiste em um painel interativo de Business Intelligence desenvolvido para analisar a base de dados de uma **empresa do setor de Telecomunicações** (ramo de telefonia). O objetivo principal é monitorar o perfil dos consumidores, o risco de crédito concedido em planos/aparelhos e a distribuição de renda em território nacional.

![Dashboard Preview](dashboard_print.png)
*(Visão geral do painel com tema escuro, focado em legibilidade e contraste)*

---

## 📂 Contexto dos Dados
A base de dados utilizada neste projeto foi extraída de uma operação real do ramo de telecomunicações (similar a empresas como a Algar Telecom). O dataset contém registros de mais de **21 mil clientes**, abrangendo:
* **Dados Cadastrais:** Idade, Gênero, Estado Civil e Escolaridade.
* **Dados Financeiros:** Renda Comprovada e Limite de Crédito (para planos ou compras).
* **Histórico de Consumo:** Valores de compras/faturas e frequência de utilização.

O desafio foi transformar esses dados brutos em inteligência para entender quem são os clientes que consomem os serviços da operadora e qual o risco financeiro envolvido na carteira.

---

## 🛠️ Solução Implementada
O dashboard foi estruturado para fornecer visualizações estratégicas divididas em seções lógicas:

### 1. KPIs e Métricas Principais
* **Total de Clientes:** Monitoramento da base ativa (21.9k).
* **Média de Renda:** Acompanhamento do poder aquisitivo médio dos assinantes (R$ 860,54).
* **Limite Total:** Visibilidade sobre a exposição total de crédito concedido pela operadora (7.54 Mi).

### 2. Análises Demográficas e Geográficas
* **Distribuição Etária:** Histograma calculado via DAX mostrando a concentração de clientes por idade.
* **Mapa de Renda:** Visualização geoespacial identificando estados com maior soma de Renda Comprovada.
* **Escolaridade e Gênero:** Gráfico de barras clusterizado cruzando o Grau de Instrução com o Sexo.
* **Estado Civil:** Gráfico de rosca para identificação rápida do perfil familiar (Solteiros, Casados, etc.).

### 3. Análise de Crédito
* **Ocupação do Limite:** Histograma que analisa a distribuição do percentual de uso do limite, facilitando a identificação de perfis tomadores de risco.

---

## 💡 Potencial de Análise e Tomada de Decisão
O diferencial deste dashboard é a interatividade. Ele foi projetado para permitir que o analista descubra padrões ocultos através do cruzamento dinâmico de filtros (**Cross-Filtering**).

Abaixo estão exemplos de análises possíveis ao combinar as variáveis:

### 1. 🌍 Inteligência Geoespacial e Renda (Região + Renda)
Ao cruzar o Mapa Interativo com os indicadores financeiros, o usuário pode:
* **Identificar Clusters de Riqueza:** Descobrir se existem estados ou regiões específicas que, apesar de terem menos clientes, concentram a maior parte da renda comprovada.
* **Planejamento de Infraestrutura:** Entender onde estão os clientes mais valiosos para priorizar investimentos em cobertura ou lojas físicas.

### 2. ⚠️ Análise de Risco e Uso de Crédito (Idade + Ocupação do Limite)
Combinando o histograma de **Idade** com o gráfico de **Ocupação de Limite**, é possível analisar:
* **Perfil de Risco Etário:** Verificar se clientes mais jovens tendem a utilizar uma porcentagem maior do seu limite (risco de inadimplência na fatura) comparado a clientes mais seniores.
* **Upsell de Planos:** Identificar clientes com limites altos e baixa utilização para ofertar upgrades de plano ou novos aparelhos.

### 3. 🎯 Segmentação Sócio-Demográfica
A filtragem cruzada entre **Grau de Instrução**, **Estado Civil** e **Sexo** permite:
* **Definição de Personas:** Entender qual é o perfil predominante (ex: Casados com Ensino Superior vs. Solteiros com Ensino Médio) para criar campanhas de marketing direcionadas.

---

## ⚙️ Ferramentas e Técnicas
* **Microsoft Power BI:** Ferramenta principal de desenvolvimento.
* **Limpeza e Transformação de Dados (ETL):**
    * Processo rigoroso de higienização da base de dados.
    * Verificação e remoção de valores nulos e dados faltantes (missing values).
    * Padronização de inconsistências nas colunas de Gênero e Geolocalização.
* **Fórmulas DAX:**
    * **Cálculo de Idade:** `Idade = DATEDIFF(Clientes[DataNascimento], TODAY(), YEAR)`
    * **Geolocalização Precisa:** `Localizacao Mapa = [UF] & ", Brasil"` (para garantir plotagem correta no mapa).
    * **Medidas de Agregação:** Somas e médias para compor os KPIs.

---

## 🚀 Como Executar o Projeto
1.  Baixe o arquivo `.pbix` deste repositório.
2.  Tenha o **Power BI Desktop** instalado.
3.  Abra o arquivo e explore os filtros laterais ou clique nos gráficos para interagir com os dados.

---

### 👨‍💻 Autor
Desenvolvido por **Mateu Xauan**
www.linkedin.com/in/mateu-xauan | mateuxauam@gmail.com
