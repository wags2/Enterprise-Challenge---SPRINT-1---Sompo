# 🌾 AgroRisk Intelligence — Sompo Challenge Sprint 1

> **Solução de análise preditiva de riscos para equipamentos agrícolas**  
> Desenvolvido em parceria com a **Sompo Seguros** | FIAP Challenge Sprint 1

---

## 📋 Sumário

1. [Descrição do Problema](#1-descrição-do-problema)
2. [Solução Proposta](#2-solução-proposta)
3. [Personas e User Stories](#3-personas-e-user-stories)
4. [Estrutura dos Dados](#4-estrutura-dos-dados)
5. [Arquitetura da Solução](#5-arquitetura-da-solução)
6. [Modelo Preditivo](#6-modelo-preditivo)

---

## 1. Descrição do Problema

### Contexto

A **Sompo Seguros** atua no desenvolvimento de soluções que combinam seguros, análise de risco e inovação tecnológica, com foco em **antecipar problemas antes que eles aconteçam**, reduzindo prejuízos e aumentando a eficiência operacional.

### Problema Central

A baixa previsibilidade de riscos operacionais em equipamentos agrícolas é um desafio crítico do setor. Atualmente, muitas decisões ainda são tomadas de forma **reativa** — após a ocorrência de eventos. Isso resulta em:

- ❌ Danos mecânicos graves a equipamentos de alto valor
- ❌ Custos elevados de manutenção emergencial
- ❌ Perda total de equipamentos em situações evitáveis
- ❌ Paralisação da operação agrícola em períodos críticos

### Exemplo Concreto

> Imagine um operador realizando a colheita em uma área próxima a um rio após um período de chuva. Sem uma análise prévia, ele pode não perceber que o solo está instável e que há maior risco de atolamento ou deslizamento do equipamento — o que pode gerar danos mecânicos, altos custos ou até perda total do equipamento.

**Com uma solução baseada em dados**, seria possível cruzar informações de clima, tipo de solo, histórico da região e padrão de operação, gerando um alerta antecipado e recomendando ajustes como mudança de rota ou adiamento da operação.

### Principais Desafios Identificados

| Desafio | Impacto |
|---|---|
| Alta exposição a riscos operacionais (colisões, transporte, ambiente adverso) | Perdas financeiras e acidentes |
| Falta de sistemas inteligentes para previsão de falhas e incidentes | Decisões reativas |
| Baixa capacidade de atuação preventiva baseada em dados | Ineficiência operacional |
| Dificuldade em correlacionar fatores ambientais e operacionais com ocorrências reais | Análise limitada |

---

## 2. Solução Proposta

### Nome do Sistema: **AgroRisk Intelligence**

O **AgroRisk Intelligence** é uma plataforma de análise preditiva de riscos voltada para o setor de seguros de equipamentos agrícolas. O sistema integra dados ambientais, operacionais e históricos para gerar **scores de risco em tempo real**, alertas preventivos e recomendações acionáveis para operadores, gestores e seguradoras.

### O que o sistema faz:

```
Coleta de Dados → Processamento → Modelo Preditivo → Score de Risco → Alertas e Recomendações
```

### Valor Entregue por Perfil

| Perfil | Valor Entregue |
|---|---|
| **Operador** | Alertas em campo sobre riscos iminentes (solo, clima, rota) |
| **Gestor** | Visão consolidada da frota e histórico de incidentes |
| **Seguradora (Sompo)** | Dados precisos para precificação, prevenção de sinistros e tomada de decisão |

### Saídas Esperadas do Sistema

- 🟢 **Score de Risco** (0–100): nível de risco calculado para a operação atual
- 🔔 **Alertas Preventivos**: notificações antes de operações de alto risco
- 📊 **Dashboard Analítico**: visualização dos dados por equipamento, região e tipo de operação
- 📝 **Recomendações Automatizadas**: ações sugeridas para reduzir o risco

---

## 3. Personas e User Stories

### Persona 1 — João, Operador de Colheitadeira

> Homem, 38 anos, trabalha no campo há 15 anos. Possui habilidade prática mas pouco acesso a ferramentas tecnológicas complexas. Opera em diferentes regiões com terrenos variados.

**Necessidades:**
- Saber se o terreno está seguro para operar antes de iniciar
- Receber alertas simples e visuais no celular ou painel do equipamento
- Não perder tempo com interfaces complicadas

**User Stories:**
- `US01` — Como operador, quero receber um alerta de risco antes de iniciar a operação em uma nova área, para que eu possa evitar danos ao equipamento.
- `US02` — Como operador, quero visualizar o nível de risco do solo em tempo real, para ajustar minha rota ou aguardar melhores condições.

---

### Persona 2 — Carla, Gestora de Frota Agrícola

> Mulher, 44 anos, responsável por gerenciar 30+ equipamentos em diferentes fazendas. Usa dashboards e relatórios para tomada de decisão.

**Necessidades:**
- Visão centralizada do status e risco de todos os equipamentos
- Histórico de incidentes por equipamento e região
- Relatórios para embasar decisões operacionais

**User Stories:**
- `US03` — Como gestora, quero visualizar um dashboard com o score de risco de cada equipamento da frota, para priorizar inspeções e manutenções.
- `US04` — Como gestora, quero acessar o histórico de alertas e incidentes por região, para identificar padrões e áreas de maior risco.

---

### Persona 3 — Roberto, Analista de Riscos da Sompo Seguros

> Homem, 50 anos, atua na análise e precificação de apólices de seguros agrícolas. Precisa de dados confiáveis e modelos preditivos para embasar decisões.

**Necessidades:**
- Dados estruturados sobre risco operacional por tipo de equipamento e região
- Correlação entre variáveis ambientais e histórico de sinistros
- Evidências para ajuste dinâmico de apólices

**User Stories:**
- `US05` — Como analista da seguradora, quero acessar relatórios de risco histórico por tipo de equipamento e condição ambiental, para subsidiar a precificação das apólices.
- `US06` — Como analista da seguradora, quero receber alertas quando um equipamento segurado operar em condições de alto risco, para acionar protocolos preventivos.

---

## 4. Estrutura dos Dados

### Variáveis do Dataset

As variáveis foram organizadas em três categorias principais:

#### 📡 Dados Ambientais

| Variável | Tipo | Descrição | Exemplo |
|---|---|---|---|
| `temperatura_c` | Float | Temperatura em graus Celsius | 32.5 |
| `precipitacao_mm` | Float | Precipitação acumulada (últimas 24h) | 45.0 |
| `umidade_relativa_pct` | Float | Umidade relativa do ar (%) | 78.0 |
| `velocidade_vento_kmh` | Float | Velocidade do vento em km/h | 22.0 |
| `tipo_solo` | String | Classificação do solo | "argiloso", "arenoso", "misto" |
| `distancia_corpos_agua_m` | Integer | Distância de rios/lagos em metros | 150 |
| `declividade_graus` | Float | Inclinação do terreno em graus | 8.5 |

#### 🚜 Dados Operacionais

| Variável | Tipo | Descrição | Exemplo |
|---|---|---|---|
| `tipo_operacao` | String | Tipo de atividade do equipamento | "colheita", "transporte", "plantio" |
| `tipo_equipamento` | String | Modelo/categoria do equipamento | "colheitadeira", "trator", "caminhão" |
| `horas_uso_acumuladas` | Integer | Horas de uso do equipamento | 4520 |
| `ultima_manutencao_dias` | Integer | Dias desde a última manutenção | 30 |
| `velocidade_operacao_kmh` | Float | Velocidade média durante a operação | 12.0 |
| `carga_kg` | Float | Peso transportado/operado em kg | 8000.0 |
| `regiao_id` | String | Identificador da região de operação | "MT-001" |

#### 📊 Variável Alvo

| Variável | Tipo | Descrição | Valores |
|---|---|---|---|
| `nivel_risco` | Integer | Classificação de risco calculada | 0=Baixo, 1=Médio, 2=Alto, 3=Crítico |

### Exemplo de Dataset Simulado

```csv
data,tipo_equipamento,tipo_operacao,temperatura_c,precipitacao_mm,tipo_solo,distancia_corpos_agua_m,horas_uso_acumuladas,ultima_manutencao_dias,nivel_risco
2024-03-15,colheitadeira,colheita,28.5,62.0,argiloso,80,5200,45,3
2024-03-15,trator,plantio,25.0,5.0,arenoso,500,2100,10,0
2024-03-16,colheitadeira,transporte,30.0,0.0,misto,300,4800,20,1
2024-03-16,caminhão,transporte,27.5,12.0,argiloso,200,3600,35,2
2024-03-17,trator,colheita,33.0,80.0,argiloso,60,6100,60,3
```

### Justificativa das Variáveis

- **Precipitação + Tipo de Solo**: combinação crítica para prever atolamento e deslizamento
- **Distância de corpos d'água**: solo encharcado próximo a rios amplia risco significativamente
- **Horas de uso + Última manutenção**: indicadores de desgaste mecânico
- **Declividade**: fator determinante para risco de tombamento e deslizamento

---

## 5. Arquitetura da Solução

```
┌─────────────────────────────────────────────────────────────────┐
│                     COLETA DE DADOS                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐  │
│  │  Sensores    │  │  APIs        │  │  Input Manual /      │  │
│  │  IoT (GPS,   │  │  Climáticas  │  │  Sistema de Gestão   │  │
│  │  acelerôm.)  │  │  (INMET etc.)│  │  de Frota            │  │
│  └──────┬───────┘  └──────┬───────┘  └──────────┬───────────┘  │
└─────────┼─────────────────┼────────────────────┼───────────────┘
          │                 │                    │
          ▼                 ▼                    ▼
┌─────────────────────────────────────────────────────────────────┐
│                   PROCESSAMENTO / BACKEND                        │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  Ingestão e Normalização dos Dados (Python / ETL)       │   │
│  └───────────────────────┬─────────────────────────────────┘   │
│  ┌───────────────────────▼─────────────────────────────────┐   │
│  │  Pré-processamento: limpeza, encoding, feature           │   │
│  │  engineering (ex: índice de saturação do solo)           │   │
│  └───────────────────────┬─────────────────────────────────┘   │
└──────────────────────────┼──────────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────────┐
│                    MODELO PREDITIVO (IA)                         │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  Classificador de Risco                                  │  │
│  │  (Random Forest / XGBoost)                               │  │
│  │                                                          │  │
│  │  Entrada: variáveis ambientais + operacionais            │  │
│  │  Saída: Score de Risco (0–100) + Classe (Baixo→Crítico)  │  │
│  └──────────────────────────┬───────────────────────────────┘  │
└─────────────────────────────┼───────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    INTERFACE / SAÍDA                             │
│  ┌─────────────────┐  ┌─────────────────┐  ┌───────────────┐   │
│  │  App Mobile     │  │  Dashboard Web  │  │  API REST     │   │
│  │  (Operador)     │  │  (Gestor /      │  │  (Integração  │   │
│  │  Alertas push   │  │  Seguradora)    │  │  com Sompo)   │   │
│  └─────────────────┘  └─────────────────┘  └───────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

### Componentes Técnicos Planejados

| Componente | Tecnologia Planejada | Justificativa |
|---|---|---|
| Backend / API | Python + FastAPI | Rápido, leve, ótima integração com ML |
| Modelo de ML | Scikit-learn / XGBoost | Excelente performance em dados tabulares |
| Banco de Dados | PostgreSQL | Confiabilidade e suporte a dados geoespaciais |
| Dashboard | React + Recharts | Interface moderna e responsiva |
| API Climática | INMET / OpenMeteo | Dados públicos e gratuitos para o Brasil |
| Deploy | Railway / Render | Simplicidade para MVP |
| Controle de Versão | GitHub | Requisito do Challenge |

### Segurança

- Controle de acesso por perfil de usuário (operador, gestor, seguradora)
- Autenticação via JWT
- Integridade dos dados garantida por validação na camada de ingestão
- Repositório privado no GitHub

---

## 6. Modelo Preditivo

### Abordagem Escolhida: Classificação de Risco

O modelo será treinado para classificar o nível de risco em **4 categorias**:

| Classe | Descrição | Ação Recomendada |
|---|---|---|
| 0 — Baixo | Condições favoráveis para operação | Operar normalmente |
| 1 — Médio | Atenção recomendada | Monitorar de perto |
| 2 — Alto | Risco relevante identificado | Recomendação de ajuste operacional |
| 3 — Crítico | Risco grave de dano ou acidente | Suspender operação |

### Justificativa do Modelo

**Random Forest / XGBoost** foram escolhidos como abordagem inicial pelos seguintes motivos:

- ✅ Alta performance em dados tabulares com variáveis heterogêneas
- ✅ Interpretabilidade (feature importance) — essencial para justificar alertas
- ✅ Resistência a outliers e dados faltantes
- ✅ Não requer grandes volumes de dados para resultados iniciais

### Inputs e Outputs do Modelo

```
INPUTS:
├── temperatura_c
├── precipitacao_mm
├── umidade_relativa_pct
├── tipo_solo (encoded)
├── distancia_corpos_agua_m
├── declividade_graus
├── tipo_operacao (encoded)
├── horas_uso_acumuladas
├── ultima_manutencao_dias
└── velocidade_operacao_kmh

OUTPUTS:
├── nivel_risco: [0, 1, 2, 3]
├── score_risco: [0.0 – 100.0]
└── principais_fatores: ["precipitação alta", "solo argiloso", ...]
```

---

## Integrantes do Grupo

| Nome | RM | 
|---|---|
| *Beatriz de Oliveira Ossola Ribeiro* | *rm570190*  
| *Kauan Maciel Forgiarini* | *rm574005* 
| *Willian Kauê Tobias do Carmo* | *rm570038*  
| *Thiago Lucas da Costa Bessa* | *rm570367*  
| *Wagner Adriano de Souza Silva Junior* | *rm569431*  

---

## 📽️ Apresentação em Vídeo

> 🔗 **Link do vídeo:** *(inserir link após gravação)*

O vídeo apresenta:
1. Contextualização do problema (equipamentos agrícolas e riscos)
2. Nossa solução proposta (AgroRisk Intelligence)
3. Como os dados serão utilizados
4. Arquitetura inicial do sistema

---

## 📎 Referências

- Sompo Seguros — [sompo.com.br](https://www.sompo.com.br)
- INMET — Instituto Nacional de Meteorologia — [inmet.gov.br](https://www.inmet.gov.br)
- Embrapa Solos — Mapeamento e classificação de solos brasileiros
- OpenMeteo API — [open-meteo.com](https://open-meteo.com)

*Desenvolvido com 💚 por alunos da FIAP — Turma [1TIAOB]*
