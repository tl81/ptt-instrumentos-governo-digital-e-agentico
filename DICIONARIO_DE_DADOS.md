# 📚 Dicionário de Dados — Base do PTT (27 Colunas LACA)

Este documento detalha a estrutura técnica, os tipos de dados e a função analítica de cada uma das **27 colunas** da base de dados do Produto Técnico Tecnológico (`dataset`), originadas do processamento do método **LACA (LLM-Assisted Content Analysis)**.

---

## 1. Atributos Principais e Classificação Teórica

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `nm_ins` | Texto | Denominação oficial do instrumento, tecnologia, política pública ou prática governamental catalogada. |
| `descr` | Texto | Síntese funcional do instrumento, detalhando seus objetivos e modo de operação. |
| `categ` | Texto | Classificação dedutiva em uma ou mais das 10 macrocategorias do PTT (delimitadas por ponto e vírgula). |
| `territ` | Texto | Jurisdição ou local de implementação reportado (ex: município, estado, país ou modelo teórico). |
| `gr_impl` | Texto | Estágio de prontidão (ex: *proposto*, *protótipo*, *implementado em produção*, *com resultados mensurados*). |
| `res` | Texto | Impactos qualitativos ou quantitativos observados na geração de Valor Público. |

---

## 2. Evidências Textuais Qualitativas (Rastreabilidade)

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `evid_clas_cat` | Texto | Trechos literais extraídos da literatura que fundamentam a categorização temática do instrumento. |
| `evid_territ` | Texto | Fragmentos do texto fonte que comprovam o local ou escopo geográfico de aplicação. |
| `evid_gr_impl` | Texto | Evidências extraídas do documento que atestam o grau de maturação do instrumento. |
| `evid_res` | Texto | Fragmentos do corpus que comprovam os resultados e impactos gerados na gestão ou na sociedade. |

---

## 3. Participação Cidadã e Coprodução de Valor Público

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `evid_part_cid` | Texto | Evidência textual do engajamento de cidadãos na utilização ou controle da solução. |
| `tp_part_cidada` | Texto | Tipologia de participação cidadã (ex: *individual*, *coletiva*, *nenhum*). |
| `evid_coprod` | Texto | Trecho que atesta a ocorrência de coprodução de serviços públicos entre governo e sociedade. |
| `coprod_cid` | Texto | Descrição do mecanismo de colaboração ativa exercido pelos cidadãos na solução. |

---

## 4. Parametrização e Isolamento de IA Agêntica

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `evid_orq_mult_IA` | Texto | **Coluna O:** Mapeamento qualitativo do contexto amplo de Inteligência Artificial e automação (**204 ocorrências**). |
| `uso_evid_orq_mult_IA` | Texto | **Coluna P:** Parametrização 5W2H de isolamento estrito da orquestração multiagente autônoma (**176 instrumentos de Governo Agêntico**). |

---

## 5. Metadados Autorais e Bibliográficos

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `autor` | Texto | Autores do artigo científico ou documento de controle externo fonte. |
| `ano` | Numérico | Ano de publicação da obra fonte. |
| `titulo` | Texto | Título original do trabalho científico ou relatório normativo. |
| `referencia` | Texto | Citação bibliográfica completa formatada em padrão ABNT. |

---

## 6. Logs de Processamento e Auditoria Algorítmica (LACA)

| Nome da Coluna | Tipo | Descrição Técnica e Função Analítica |
| :--- | :--- | :--- |
| `_timestamp` | Numérico | Marca temporal (*timestamp*) da execução da extração via API do LLM. |
| `input_prompt` | Texto | Identificador da versão do prompt sistêmico aplicado no *Prompt Blender*. |
| `input_document_text` | Texto | Nome do arquivo e trecho do documento processado no lote de extração (*chunk*). |
| `input_document_size` | Numérico | Tamanho em *tokens* do bloco de texto enviado para análise do modelo de linguagem (ex: 12.000 tokens). |
| `_run` | Texto | Modelo de linguagem de grande escala (LLM) utilizado na extração (`gemini-3.1-flash-lite-preview`). |
| `_error` | Texto | Registro de eventuais falhas ou exceções ocorridas durante o processamento (nulo quando bem-sucedido). |
| `_raw` | Texto | Resposta em formato JSON bruto gerada pela API do modelo de IA (para auditoria técnica). |
