# 📉 Análise de Cancelamento de Clientes

> Projeto desenvolvido na **Jornada Python — Python Insights** (Hashtag Treinamentos)

Análise de uma base de **50 mil clientes** para descobrir por que eles cancelam e quais ações reduzem o cancelamento. Resultado: três causas explicam a maior parte do problema e, atacando-as, a taxa de cancelamento **cai de 56,8% para 18,4%**.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

![Resultado da análise](imagens/resultado.png)

---

## 📌 A pergunta de negócio

Uma empresa com mais de 800 mil clientes percebeu que a maior parte da sua base já cancelou o serviço. **Quais são os principais motivos dos cancelamentos, e quais ações seriam mais eficientes para reduzi-los?**

## 🔄 Etapas da análise

1. **Importação** da base `cancelamentos.csv` com Pandas
2. **Limpeza:** remoção da coluna `CustomerID` (não explica o cancelamento) e das 4 linhas com valores vazios
3. **Análise inicial:** 56,8% dos clientes cancelaram
4. **Análise detalhada:** histograma de cada característica, separando quem cancelou de quem ficou
5. **Simulação:** impacto de resolver cada causa na taxa de cancelamento

## 🔍 Principais descobertas

### 1. Contrato mensal: 100% de cancelamento
![Cancelamento por duração do contrato](imagens/contrato.png)

### 2. Mais de 4 ligações ao call center: cancelamento quase certo
![Cancelamento por ligações ao call center](imagens/ligacoes.png)

### 3. Mais de 20 dias de atraso: 100% de cancelamento
![Cancelamento por dias de atraso](imagens/atraso.png)

Outro ponto de atenção: **todos os clientes acima de 50 anos cancelaram**, o que merece uma investigação específica sobre a experiência desse público.

## ✅ Recomendações

| Causa | Ação proposta |
|---|---|
| Contrato mensal | Oferecer desconto para migrar para os planos trimestral e anual |
| Muitas ligações ao call center | Criar um alerta na 3ª ligação do cliente, para resolver o problema antes que ele desista |
| Atraso no pagamento | Criar um alerta e oferecer negociação quando o atraso chegar a 15 dias |

## 📊 Resultado

| Cenário | Taxa de cancelamento |
|---|:---:|
| Situação atual | 56,8% |
| Sem contrato mensal | 46,1% |
| + até 4 ligações ao call center | 26,4% |
| + até 20 dias de atraso | **18,4%** |

## 📁 Estrutura

```
analise-cancelamento-clientes/
├── analise.ipynb        # notebook com a análise completa
├── cancelamentos.csv    # base com 50 mil clientes
├── imagens/             # gráficos usados neste README
└── requirements.txt
```

## ▶️ Como executar

```bash
git clone https://github.com/AlessandroMaxv10/analise-cancelamento-clientes.git
cd analise-cancelamento-clientes
pip install -r requirements.txt
jupyter notebook analise.ipynb
```

## 🛠️ Tecnologias

- **Python**
- **Pandas** — importação, limpeza e filtragem dos dados
- **Plotly** — gráficos interativos de cada característica
- **Jupyter Notebook**

## 📚 O que aprendi

- Limpar a base antes de analisar: colunas sem valor e linhas vazias distorcem o resultado
- Transformar gráficos em respostas para uma pergunta de negócio
- Quantificar o impacto de cada ação, em vez de só apontar problemas
- Comunicar conclusões de forma que um gestor consiga agir

---

👤 **Alessandro José dos Santos** · [LinkedIn](https://www.linkedin.com/in/alessandro-jos%C3%A9-dos-santos-01b87a127) · [Portfólio](https://alessandromaxv10.github.io)
