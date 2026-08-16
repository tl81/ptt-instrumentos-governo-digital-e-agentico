# Base de Dados: Instrumentos de Indução da Maturidade de Governo Digital na Educação

[![Mestrado Profissional](https://img.shields.io/badge/Mestrado_Profissional-ISC%2FTCU-003366?style=for-the-badge)](https://portal.tcu.gov.br/instituto-serzedello-correa/)
[![CAPES](https://img.shields.io/badge/Avaliação-CAPES-blue?style=for-the-badge)](https://www.gov.br/capes/pt-br)
[![Metodologia](https://img.shields.io/badge/Metodologia-LACA_(LLM--Assisted)-128C7E?style=for-the-badge)](#-metodologia-laca-llm-assisted-content-analysis-e-agrupamento-computacional)
[![Licença](https://img.shields.io/badge/Licença-CC_BY_4.0-green?style=for-the-badge)](https://creativecommons.org/licenses/by/4.0/deed.pt_BR)

## 📌 Sobre o Produto Técnico Tecnológico (PTT)

Este repositório contém a Base de Dados do **Produto Técnico Tecnológico (PTT)** desenvolvido como requisito parcial para a obtenção do título de Mestre em Controle da Administração Pública pelo Instituto Serzedello Corrêa (ISC/TCU).

O acervo reúne e cataloga instrumentos de indução de políticas públicas, tecnologias digitais, arranjos institucionais e mecanismos de controle voltados à elevação da maturidade em Governo Digital e Agêntico na Educação, com foco na promoção da participação cidadã e na coprodução de valor público.

* **Aluno/Autor:** Tiago Marafante Lins de Souza
* **Orientador:** Prof. Dr. Edans Flávius de Oliveira Sandes
* **Instituição:** Instituto Serzedello Corrêa (ISC) — Escola Superior do Tribunal de Contas da União (TCU)
* **Programa:** Programa de Pós-Graduação *Stricto Sensu* em Controle da Administração Pública (Linha de Pesquisa 2: Tecnologias para a Inovação do Controle Governamental)
* **Ano:** 2026

---

## 🔬 Metodologia: LACA (LLM-Assisted Content Analysis) e Agrupamento Computacional

A identificação e a categorização do acervo não utilizaram métodos manuais tradicionais, os quais seriam inviáveis dada a volumetria textual. Foi empregado o método de fronteira **LACA (LLM-Assisted Content Analysis)**, combinando análise de conteúdo dedutiva e Inteligência Artificial Generativa com pipeline de processamento em Python:

1. **Formação do Corpus:** Triagem e estruturação de 76 documentos refinados (69 artigos científicos extraídos das bases Scopus, Web of Science e Google Scholar, e 7 documentos do acervo de controle externo do TCU e OCDE).
2. **Extração Automatizada (Prompt Blender):** Processamento de blocos de texto no software *Prompt Blender* alimentado pela API do modelo *Gemini* com restrições arquitetônicas 5W2H, resultando no mapeamento inicial de **1.025 instrumentos brutos**.
3. **Supervisão Humana (Ground Truth):** Leitura e codificação manual de amostra estratificada pelo pesquisador para ajustar as instruções do prompt e assegurar o alinhamento ao controle externo.
4. **Deduplicação Computacional em Python:** Aplicação de vetorização textual **TF-IDF** e **Agrupamento Hierárquico Aglomerativo** em ambiente Python, eliminando redundâncias e catalogando com precisão **909 instrumentos únicos de indução**.

---

### 📌 Nota Metodológica sobre a Volumetria do PTT

Para garantir a transparência e a auditabilidade dos dados, esclarece-se a relação entre os números apresentados neste repositório e na dissertação:

* **1.025 Registros Catalogados:** Corresponde ao total de ocorrências tratadas e disponibilizadas na base de dados (na aba `dataset` da planilha `.xlsx` e no arquivo `.csv`).
* **909 Instrumentos Únicos:** Quantidade de identificações únicas obtidas após o processo de deduplicação por agrupamento estatístico em Python (algoritmo TF-IDF).
* **1.029 Extrações LACA:** Total de raspagens brutas geradas pela IA, mantidas na base para fins de auditoria aberta e reprodutibilidade científica.
* **1.875 Frequências (Total):** Reflete a contagem geral da classificação de instrumentos em categorias no Painel Analítico, visto que diversos instrumentos possuem atribuição multicategoria.

---

### 🤖 Isolamento Arquitetônico: Infraestrutura de IA vs. Governo Agêntico

A análise automatizada do corpus científico revelou um estágio claro de transição na literatura sobre transformação digital no setor público:

* **Análise Qualitativa de Contexto (Coluna O / `evid_orq_mult_IA`):** Identificou **204 ocorrências** associadas à infraestrutura geral de Inteligência Artificial, automação básica e digitalização de serviços públicos.
* **Isolamento Arquitetônico Estrito (Coluna P / `uso_evid_orq_mult_IA`):** Mediante parametrização 5W2H, consolidou um núcleo de **176 instrumentos** legitimamente relacionáveis ao paradigma do **Governo Agêntico**.

Esse comportamento dos dados comprova que, embora a discussão sobre IA isolada (como chatbots reativos e algoritmos preditivos simples) seja pulverizada, a verdadeira orquestração autônoma de múltiplos agentes — motor central do **Modelo CoValor** proposto na dissertação — constitui a fronteira emergente da literatura contemporânea (2025–2026).

---

## 📁 Estrutura do Repositório

| Arquivo / Pasta | Descrição |
| :--- | :--- |
| `dataset-ptt-instrumentos-governo-digital-e-agentico.xlsx` | Planilha executiva contendo a aba `dashboard` (Painel Analítico) e a aba `dataset` (Base Estruturada e Auditável). |
| `dataset-ptt-instrumentos-governo-digital-e-agentico.csv` | Matriz em dados abertos (texto puro UTF-8 delimitado por ponto e vírgula) para consumo automatizado em Python, R e Power BI. |
| `README.md` | Documentação completa do repositório, metodologia LACA, métricas de colunas e instruções de reuso. |
| `CITATION.cff` | Arquivo de citação bibliográfica automatizada para uso acadêmico. |
| `LICENSE` | Licença de uso e redistribuição pública (Creative Commons CC BY 4.0). |

---

## 📊 Dicionário de Dados e Mapeamento de Colunas

A matriz principal de dados do repositório (`dataset`) organiza-se em 27 colunas de extração bruta do LACA e metadados analíticos, com destaque para os atributos descritivos e de parametrização avançada:

| Campo / Coluna | Nome na Base (`dataset`) | Descrição Técnica e Função no PTT |
| :--- | :--- | :--- |
| **Identificador / Nome** | `nm_ins` | Nome ou denominação oficial da tecnologia, política pública, norma ou prática governamental. |
| **Descrição Funcional** | `descr` | Síntese do funcionamento e objetivo principal do instrumento. |
| **Categoria Teórica** | `categ` | Enquadramento dedutivo em uma ou mais das 10 macrocategorias de indução. |
| **Território de Aplicação** | `territ` | Jurisdição ou local de implementação (município, estado, país ou modelo teórico). |
| **Grau de Implementação** | `gr_impl` | Estágio de prontidão (proposto, protótipo, em produção ou com resultados mensurados). |
| **Resultados Reportados** | `res` | Impactos qualitativos ou quantitativos observados na geração de Valor Público. |
| **Contexto de IA (Coluna O)** | `evid_orq_mult_IA` | Mapeamento qualitativo da infraestrutura geral de IA e automação em serviços públicos (**204 ocorrências**). |
| **Governo Agêntico 5W2H (Coluna P)** | `uso_evid_orq_mult_IA` | Parametrização estrita de isolamento da orquestração multiagente autônoma do paradigma do Governo Agêntico (**176 instrumentos**). |
| **Participação Cidadã** | `tp_part_cidada` / `coprod_cid` | Tipologia de engajamento social e mecanismos de coprodução de valor público observados. |
| **Metadados Autorais** | `autor` / `ano` / `titulo` / `referencia` | Informações de autoria, ano de publicação e citação ABNT completa da fonte bibliográfica. |

---

## 🚀 Aplicabilidade (Controle Externo e Gestão Pública)

* **Para o Controle Externo (TCU e TCEs):** Funciona como lastro bibliográfico e empírico para o *Checklist de Requisitos* desenvolvido na dissertação. Auditores dispõem de um referencial auditável para avaliar a maturidade e a abertura democrática de sistemas governamentais (como a Plataforma MEC Gestão Presente).
* **Para a Gestão Pública (MEC, Secretarias Estaduais e Municipais):** Atua como um catálogo vivo de "soluções de prateleira". Gestores públicos podem consultar e adotar boas práticas validadas, acelerando a elevação da maturidade digital e agêntica sem custos de redesenho inicial.

---

## 📜 Licenciamento e Citação

Este PTT está licenciado sob a licença [Creative Commons Atribuição 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.pt_BR). É permitida a cópia, redistribuição, alteração e criação derivada para qualquer fim, desde que atribuído o devido crédito autoral ao autor e à instituição.

### Como citar este PTT:
```bibtex
@misc{souza2026ptt,
  author = {Souza, Tiago Marafante Lins de and Sandes, Edans Flávius de Oliveira},
  title = {Base de Dados de Instrumentos de Indução da Maturidade de Governo Digital e Agêntico na Educação},
  year = {2026},
  publisher = {GitHub},
  journal = {Repositório do Produto Técnico Tecnológico do Mestrado Profissional em Controle da Administração Pública (ISC/TCU)},
  howpublished = {\url{[https://github.com/tl81/ptt-instrumentos-governo-digital-e-agentico](https://github.com/tl81/ptt-instrumentos-governo-digital-e-agentico)}}
}
