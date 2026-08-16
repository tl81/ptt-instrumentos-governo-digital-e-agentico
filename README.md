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

## 📁 Estrutura do Repositório

| Arquivo / Pasta | Descrição |
| :--- | :--- |
| `dataset-ptt-instrumentos-governo-digital-e-agentico.xlsx` | Planilha executiva contendo a aba `dashboard` (Painel Analítico) e a aba `dataset` (Base Estruturada). |
| `dataset-ptt-instrumentos-governo-digital-e-agentico.csv` | Matriz em dados abertos (texto puro UTF-8 delimitado por ponto e vírgula) para consumo automatizado em Python, R e Power BI. |
| `README.md` | Documentação completa do repositório, metodologia LACA e instruções de reuso. |
| `CITATION.cff` | Arquivo de citação bibliográfica automatizada para uso acadêmico. |
| `LICENSE` | Licença de uso e redistribuição pública (Creative Commons CC BY 4.0). |

---

## 📊 Dicionário de Dados

A matriz de dados do repositório estrutura-se em 11 campos essenciais de atributos analíticos e metadados autorais:

| Coluna | Descrição Técnica e Função no PTT |
| :--- | :--- |
| `ID` | Identificador numérico sequencial único do instrumento na base de dados. |
| `NOME_INSTRUMENTO` | Denominação oficial da tecnologia, política pública, norma ou prática governamental. |
| `CATEGORIA` | Enquadramento dedutivo em uma ou mais das 10 macrocategorias de indução. |
| `DESCRICAO` | Síntese funcional do instrumento, explicitando seus objetivos e modo de atuação. |
| `TERRITORIO_APLICACAO` | Jurisdição ou local de implementação (município, estado, país ou modelo teórico). |
| `EVIDENCIA` | Trechos literais extraídos do corpus bibliográfico que comprovam o funcionamento da prática. |
| `GRAU_IMPLEMENTACAO` | Estágio de prontidão (proposto, protótipo, em produção ou com resultados mensurados). |
| `RESULTADOS_REPORTADOS` | Impactos qualitativos ou quantitativos observados na geração de Valor Público. |
| `AUTOR` | Metadados autorais da publicação científica ou documento fonte. |
| `ANO` | Ano de publicação do documento original. |
| `REFERENCIA` | Citação bibliográfica completa da fonte original formatada em padrão ABNT. |

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
