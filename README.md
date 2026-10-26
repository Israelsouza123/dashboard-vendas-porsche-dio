
# 🏎️ Porsche Sales Intelligence — Dashboard Interativa

Projeto desenvolvido como parte do desafio prático da **DIO (Digital Innovation One)** com o expert **Felipe Aguiar (Felipão)**, transformando uma base sanitizada de 100 vendas da Porsche em uma aplicação web analítica de arquivo único (`index.html`), publicada no GitHub Pages.

## 🎯 1. Perguntas de Negócio Escolhidas

Para construir uma dashboard executiva útil — e não apenas um amontoado de gráficos —, defini três perguntas essenciais para a diretoria comercial e financeira:

1. **Qual modelo é o verdadeiro motor de faturamento vs. volume de vendas?**
   - **Visão:** Gráfico combinado (Barras para Receita em R$ Milhões + Linha para Unidades Vendidas).
   - **Justificativa:** No mercado de superesportivos, volume não significa necessariamente maior caixa. Modelos como o *911 Turbo S* possuem ticket muito superior ao *Macan*, exigindo análises conjuntas de receita e quantidade.

2. **Onde estão concentrados os maiores mercados por Estado (UF)?**
   - **Visão:** Gráfico de barras horizontais ordenado por Receita Total por Estado.
   - **Justificativa:** Permite direcionar investimentos de marketing, eventos de test-drive VIP e alocação de estoque nas praças de maior conversão financeira.

3. **Qual a participação dos Métodos de Pagamento na Receita Total?**
   - **Visão:** Gráfico de rosca (Doughnut) detalhando a proporção entre *À Vista*, *Financiamento*, *Leasing* e *Consórcio*.
   - **Justificativa:** Auxilia a área financeira a compreender a liquidez imediata das vendas e a relevância de produtos financeiros na decisão de compra.

---

## 🧹 2. Tratamento e Sanitização da Base

Antes de embutir os dados no código HTML/JS, a planilha passou pelas seguintes etapas de preparação:
- **Exclusão das colunas cruas (raw):** Mantive apenas as colunas já sanitizadas pelo Agente de Tratamento de Dados.
- **Tipagem numérica e limpeza de fórmulas:** As colunas de `Preço` e `Ano` foram convertidas para valores numéricos puros e coladas como *Valores*, evitando erros de referência (`#REF!`, `#VALUE!`) ou strings com formatação de texto quebrada.
- **Remoção de registros inválidos (`INVALID`):** Registros sem correspondência válida foram isolados para não distorcer o cálculo de Ticket Médio e Receita Total.

---

## 🤖 3. Engenharia de Prompt e Evolução

### Prompt Inicial utilizado:
> *"Atue como um Especialista em Data Visualization e Desenvolvedor Front-end. Tenho uma base sanitizada com 100 vendas da Porsche contendo: Modelo, Cidade, Estado (UF), Ano, Preço e Método de Pagamento. Crie uma dashboard interativa em um único arquivo `index.html` usando Tailwind CSS e Chart.js. A dashboard deve ter identidade visual inspirada na Porsche (Dark Mode sofisticado em preto carbono, vermelho #d5001c e dourado #c5a059), 4 KPIs de topo (Receita Total, Volume de Vendas, Ticket Médio e Modelo Líder), filtros dinâmicos (Modelo, Estado, Ano e Pagamento) e responder às 3 perguntas de negócio definidas."*

### O que foi refinado até a versão final:
1. **Troca do filtro geográfico para Estado (UF):** Simplificou a leitura macro regional sem poluir o gráfico, mantendo a Cidade detalhada na tabela inferior.
2. **Gráfico de Eixo Duplo na Pergunta 1:** No primeiro teste, unidades e milhões de reais ficavam na mesma escala, achatando a linha de quantidade. Foi adicionado um eixo secundário (`y1`) no Chart.js para separar R$ Milhões de Unidades.
3. **Importador CSV embutido:** Adicionei um modal que permite colar novos dados em CSV diretamente pela interface para atualizar a dashboard dinamicamente.

---

## 🛠️ 4. Tecnologias Utilizadas

- **HTML5 & JavaScript (ES6+)** — Lógica de filtragem reativa, agregação de dados e manipulação de DOM sem dependências de backend.
- **Tailwind CSS (via CDN)** — Estilização responsiva e tema *Porsche Dark Luxury*.
- **Chart.js (via CDN)** — Gráficos interativos e responsivos.
- **GitHub Pages** — Hospedagem estática gratuita.
