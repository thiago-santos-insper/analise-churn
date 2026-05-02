# Análise de Churn: Identificação de Padrões e Simulação de Ações Corretivas

Análise exploratória de dados de cancelamento de clientes com o objetivo de identificar os principais fatores associados ao churn e quantificar o impacto potencial de ações corretivas.

---

## Contexto do Problema

Uma empresa com mais de **800 mil clientes** identificou que a maioria de sua base era composta por clientes **inativos**, ou seja, que já haviam cancelado o serviço.

O problema central: **por que tantos clientes estão cancelando?**

Este projeto busca responder essa pergunta com dados, identificando padrões concretos e traduzindo-os em recomendações acionáveis.

---

## Objetivos

1. Entender **quais fatores estão mais associados ao cancelamento**
2. Identificar **ações corretivas concretas** com potencial de reduzir o churn
3. **Quantificar o impacto** dessas ações com base nos dados

---

## Dataset

| Atributo | Detalhe |
|---|---|
| Registros analisados | 49.996 clientes |
| Variável-alvo | `cancelou` (0 = ativo, 1 = cancelou) |
| Fonte | Hashtag Treinamentos |

**Variáveis disponíveis:** `idade`, `sexo`, `tempo_como_cliente`, `frequencia_uso`, `ligacoes_callcenter`, `dias_atraso`, `assinatura`, `duracao_contrato`, `total_gasto`, `meses_ultima_interacao`

---

## Ferramentas e Tecnologias

- **Python**: linguagem principal
- **pandas**: manipulação e análise dos dados
- **Plotly**: visualizações interativas

---

## Etapas da Análise

```
Passo 1 → Importação de bibliotecas
Passo 2 → Carregamento e inspeção inicial dos dados
Passo 3 → Limpeza e tratamento (remoção de IDs e valores ausentes)
Passo 4 → Taxa de cancelamento atual
Passo 5 → Análise exploratória por variável (histogramas segmentados)
Passo 6 → Identificação dos 3 principais fatores de churn
Passo 7 → Simulação de impacto das ações corretivas
```

---

## Principais Insights

<img width="688" height="450" alt="analise-churn - imagem 1" src="https://github.com/user-attachments/assets/3e5ac9ae-62fe-4e08-9cae-24cd2a7c52de" />

A taxa de churn inicial era de **56.8%**, mais da metade dos clientes havia cancelado. A análise exploratória revelou três padrões com forte associação ao cancelamento:

---

### Insight 1: Excesso de contatos com o Call Center

<img width="688" height="450" alt="analise-churn - imagem 2" src="https://github.com/user-attachments/assets/386fb3b7-60eb-4a47-a0ae-a3e3ed1e44dd" />

Clientes que ligaram **mais de 4 vezes** para o suporte apresentaram taxa de churn próxima a **100%**.

Cada ligação adicional é um sinal de insatisfação acumulada: o problema não está sendo resolvido. O call center opera como um sintoma, não como uma solução.

> **Ação sugerida:** Implementar protocolo de resolução até o 2º ou 3º contato. Mapear os motivos mais frequentes e criar soluções de autoatendimento (FAQ, chatbot, portal do cliente).

---

### Insight 2: Atrasos prolongados no pagamento

<img width="688" height="450" alt="analise-churn - imagem 3" src="https://github.com/user-attachments/assets/a33a6cc7-e1ce-4716-9622-54adeb8f284a" />

Clientes com **mais de 20 dias de atraso** apresentaram altíssima probabilidade de cancelamento.

Atrasos prolongados indicam dificuldade financeira ou baixo engajamento, duas situações que exigem intervenção antes que o cliente cancele.

> **Ação sugerida:** Criar régua de cobrança proativa antes dos 20 dias, com oferta de parcelamento ou renegociação como alternativa ao cancelamento.

---

### Insight 3: Contratos mensais

<img width="688" height="450" alt="analise-churn - imagem 4" src="https://github.com/user-attachments/assets/ac60258d-ff59-451e-841c-7e6249c848e3" />

Clientes com **contrato mensal** cancelam em taxa muito superior à de clientes com contratos anuais ou trimestrais.

Contratos curtos geram baixo custo de saída: o cliente pode cancelar a qualquer momento, sem perda. Isso reduz o comprometimento e aumenta a sensibilidade a qualquer insatisfação pontual.

> **Ação sugerida:** Criar incentivos para migração para contratos mais longos (desconto, benefícios exclusivos, período gratuito). Priorizar essa migração nos primeiros meses, quando o engajamento ainda é alto.

---

## Simulação de Impacto

Aplicando os três filtros simultaneamente, como se a empresa tivesse resolvido esses problemas, a simulação projeta a seguinte redução no churn:

| Cenário | Taxa de Churn |
|---|---|
| Antes das ações | 56.8% |
| Após as ações (simulado) | 18.4% |
| **Redução absoluta** | **38.4 p.p.** |
| **Redução relativa** | **67.7%** |

<img width="1094" height="450" alt="analise-churn - imagem 5" src="https://github.com/user-attachments/assets/87bad3f6-11b6-42ee-a6a3-11fae0c5f723" />

> **Nota metodológica:** Esta simulação assume que as condições identificadas podem ser eliminadas por ação da empresa. Na prática, parte dos casos pode ser estrutural. Os resultados reais dependerão da eficácia de execução de cada iniciativa.

---

## Estrutura do Repositório

```
analise-churn/
 ├── images/
 │   ├── percentual_ativos_e_cancelados.png
 │   ├── insight_callcenter.png
 │   ├── insight_atraso.png
 │   ├── insight_contrato.png
 │   └── simulacao_impacto.png
 ├── analise_churn.ipynb             ← notebook com a análise completa
 ├── cancelamentos.csv               ← base de dados utilizada
 ├── requirements.txt                ← dependências do projeto
 └── README.md
```

---

## Como Executar

**1. Clone o repositório**
```bash
git clone https://github.com/thiago-santos-insper/analise-churn.git
cd analise-churn
```

**2. Instale as dependências**
```bash
pip install -r requirements.txt
```

**3. Abra o notebook**
```bash
jupyter notebook analise_churn.ipynb
```

---

## Autor

**Thiago Henrique Reis dos Santos**  
Estudante de Engenharia da Computação — Insper  
[LinkedIn](https://linkedin.com/in/thiago-santos-insper/) · [GitHub](https://github.com/thiago-santos-insper/)

---

*Projeto desenvolvido de forma independente para praticar análise exploratória de dados com Python.*
